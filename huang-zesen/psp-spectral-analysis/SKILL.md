---
name: psp-spectral-analysis
description: >-
  End-to-end workflow for analyzing PSP FIELDS magnetometer data: CDF loading,
  epoch conversion, Welch PSD, bandpass + Hilbert phase extraction, circular
  statistics, and control experiments. Includes numerical stability notes
  (sosfiltfilt vs filtfilt) and encounter comparison methodology.
version: 1.0
---

# PSP Spectral & Phase Analysis Workflow

## Quick Reference

### Data Access
```
URL: https://spdf.gsfc.nasa.gov/pub/data/psp/fields/l2/mag_rtn/<YEAR>/
Files: psp_fld_l2_mag_rtn_<YYYYMMDDHH>_v02.cdf
```

### CDF Loading
```python
import cdflib
c = cdflib.CDF("path/to/file.cdf")
epoch = c.varget("epoch_mag_RTN")        # TT2000 nanoseconds
mag   = c.varget("psp_fld_l2_mag_RTN") # (N, 3) nT

# Convert to datetime
times = cdflib.cdfepoch.to_datetime(epoch)  # returns numpy datetime64

# |B|
bmag = np.sqrt(np.sum(mag**2, axis=1))
```

### Perihelion Identification
```python
imax = np.argmax(bmag)  # PSP: max |B| = closest to Sun
t_peri = cdflib.cdfepoch.to_datetime(epoch[imax])
```

### High-Cadence Data (E01, 293 Hz)
```python
ds_factor = 29           # → ~10 Hz, matches lower-cadence encounters
bmag_ds = bmag[::ds_factor]
epoch_ds = epoch[::ds_factor]
```

### Welch PSD
```python
from scipy.signal import welch
fs = 1.0 / dt_s
freqs, psd = welch(bmag, fs=fs, nperseg=8192, noverlap=4096)
```

### Phase Extraction (STABLE)
```python
from scipy.signal import butter, sosfiltfilt, hilbert

def bandpass_phase(data, fs, f_center, df=0.5e-3):
    # ALWAYS normalize first for numerical stability
    mu, std = np.mean(data), np.std(data)
    x = (data - mu) / std if std > 0 else data - mu

    # sosfiltfilt is more stable than filtfilt for large |B|
    sos = butter(4, [low/nyq, high/nyq], btype='band', output='sos')
    filtered = sosfiltfilt(sos, x)
    analytic = hilbert(filtered)
    return np.angle(analytic)
```

### Circular Statistics
```python
def circ_stats(theta):
    theta = np.asarray(theta, dtype=float)
    valid = ~np.isnan(theta); theta = theta[valid]
    if len(theta) == 0: return np.nan, np.nan
    R = np.sqrt(np.sum(np.cos(theta))**2 + np.sum(np.sin(theta))**2) / len(theta)
    theta_mean = np.arctan2(np.sum(np.sin(theta)), np.sum(np.cos(theta)))
    return theta_mean, R  # R: 0=uniform, 1=perfect alignment
```

## Numerical Stability Notes

### filtfilt vs sosfiltfilt
- `filtfilt` accumulates numerical error for high-order filters and large signals
- At E01 perihelion, |B| reaches 110 nT → `filtfilt` can overflow → spurious high coherence (R > 0.9)
- **Always use `sosfiltfilt`** for phase analysis on PSP data
- **Always normalize** data to zero mean, unit variance before filtering

### Filter Bandwidth
- ±0.5 mHz bandwidth is standard for mHz-scale oscillation studies
- Bands are non-overlapping when |f1 − f2| × 2 > df_sum
- Control experiments must use genuinely non-overlapping bands (not just ±0.5 mHz apart)

## Control Experiment Design

To test whether a phase coherence result is physical or a filter artifact:

1. Identify two "real" bands: e.g., 5.5 mHz and 8.0 mHz
2. Design two "control" bands: e.g., 2.0 mHz and 12.0 mHz (far from real bands, no physical reason to couple)
3. Apply identical Hilbert phase extraction to both
4. Compare beat-test resultant length R
5. If control R ≈ real R → filter artifact; if control R << real R → physical coupling

**Typical result for colored noise:** R ≈ 0.2–0.4 for any narrowband filter pair. True physical coupling should give R > 0.5 AND be robust to different band choices.

## Methodological Hierarchy

| Method | Use Case |
|--------|----------|
| Welch PSD | Broad spectral shape, peak identification |
| Spectrogram | Time-frequency evolution, transient events |
| Bandpass + Hilbert | Instantaneous phase of narrowband signals |
| Wavelet coherence | Phase coherence between two signals vs. time |
| Encounter stacking | Extracting weak intermittent signals (Huang's method) |

**Critical note:** Single-encounter phase analysis is not the right tool for detecting weak intermittent physical coupling. Use encounter-aggregated methods (stacking, wavelet coherence over many encounters) for that purpose.
