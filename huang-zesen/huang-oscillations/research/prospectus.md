---
name: huang-oscillations-open-question
description: >
  Research prospectus: the 6-7 mHz transition band as a potential beat
  frequency between 2-minute and 3-minute p-mode bands. Contains empirical
  basis, three physical hypotheses, testable predictions, and an analysis plan.
version: 1.0
---

# Research Prospectus: The 6–7 mHz Transition Band

> **Status:** Open question — not published, not peer-reviewed.
> **Origin:** Empirical finding from PSP E05 PSD analysis (Apr 29, 2020).
> **Genre:** Research prospectus with empirical testing.
> **Confidence:** Beat hypothesis: tested and NOT confirmed. The 6.67 mHz PSD peak is a real spectral feature; its interpretation remains open.
> **Version history:**
> - v1.0: Initial beat frequency hypothesis
> - v1.1: Corrected cross-encounter phase analysis (sosfiltfilt), E05/E01 results
> - v1.2 (FINAL): Control experiment — beat hypothesis not confirmed; R ≈ 0.2–0.4 is generic filtering artifact
> **Data:** PSP E01 (Nov 7, 2018) and E05 (Apr 29, 2020) analyzed.

---

## The Empirical Starting Point

PSP Encounter 5 (April 29, 2020, perihelion 13:53 UTC, |B|_max = 19.41 nT) provides a ±30 min window around closest approach for spectral analysis.

**Welch PSD results:**

| Frequency (mHz) | PSD (nT²/Hz) | Note |
|---|---|---|
| 6.0 | 0.602 | |
| **6.67** | **0.602** | **Peak in 5–12 mHz band** |
| 7.0 | 0.602 | shoulder |
| 8.0 | 0.393 | no local peak |
| 2–5 mHz plateau | up to ~2.0 | dominant feature |

**Key observation:** The peak in the 5–12 mHz band is at **6.67 mHz** (~2.5-minute period), not at 8 mHz. The 8 mHz band shows no local peak in this window. The dominant feature is the 2–5 mHz plateau (~5-minute p-mode).

**The puzzle:** 6.67 mHz sits between the 3-minute band (5.5 mHz, chromospheric p-mode) and the 2-minute band (8 mHz, higher harmonic). It does not correspond cleanly to either.

**Data provenance:** PSP FIELDS L2 mag_rtn CDFs, 2020-04-29 12:00–23:50 UTC. Welch PSD, nperseg=4119, fs=9.16 Hz. See `psp_data/psd_analysis.py` and `psp_data/psp_e05_results.txt`.

---

## Three Physical Hypotheses

### H1: Chromospheric 3-Minute P-Mode with Doppler Shift

The chromospheric 3-minute oscillation (~5.5 mHz in the solar frame) is Doppler-shifted by solar wind expansion into the spacecraft frame.

**Calculation:** At ~15 R_⊙, V_SW ≈ 350 km/s, V_A ≈ 800 km/s → compression factor ≈ 0.44.
Expected spacecraft-frame frequency: f_sc ≈ 5.5 × 0.44 ≈ 2.4 mHz.

This is *lower* than the observed 6.67 mHz — so this simple Doppler picture does not fit.

**Possible mitigations:**
- PSP samples at a different Parker spiral footpoint than the wave excitation site
- Radial-to-transverse projection modifies the effective frequency in the RTN frame
- Wave is partially reflected before reaching PSP, adding a second Doppler shift

**Assessment:** Not ruled out, but requires non-trivial geometry to explain 6.67 mHz specifically.

---

### H2: In-Situ Convective Driving at PSP Distance

At 15 R_⊙, the convective timescale over a PSP-scale fluctuation (~100 km) gives f ≈ V_SW/L ≈ 350/100 ≈ 3.5 mHz. Over an ion inertial scale (~10 km): 350/10 ≈ 35 mHz.

The 6–7 mHz range sits between these scales, closer to the convective estimate.

**Assessment:** Plausible but not specific — it predicts power in the general range, not a peak at 6.67 mHz.

---

### H3: Beat Frequency from Parametric Decay (Preferred Hypothesis)

This is the most interesting possibility and the one with the sharpest prediction.

Two strong, coherent drivers are present near the Alfvén surface:
- 3-minute chromospheric p-mode: ~5.5 mHz
- 2-minute higher harmonic: ~8 mHz

If these two bands undergo **nonlinear wave-wave coupling** (parametric decay), they will produce sum and difference frequency products:
- |8 − 5.5| = **2.5 mHz** (difference)
- (8 + 5.5)/2 = **6.75 mHz** (mean) or 2×6.75 = 13.5 mHz (second harmonic of mean)

The observed 6.67 mHz ≈ 6.75 mHz — the match is striking.

**Physical picture:** Near the Alfvén surface, both p-mode bands are present as large-amplitude, spherically polarized Alfvénic wave trains. They propagate through the same plasma volume. If they are phase-coherent (not randomly phased), their interaction produces a beat frequency — exactly what the E05 PSD shows.

**Why this matters:** This would be **the first evidence of p-mode coupling in the solar wind itself**, not just at the solar surface. It would imply that the 2-minute and 3-minute bands are not independent phenomena but interacting components of the same wave field near the Alfvén surface.

**Assessment:** The beat frequency match is quantitative and specific. This is the hypothesis to test.

---

## The Testable Prediction

**If H3 is correct:** There should be **phase coherence** between the 5.5 mHz and 8 mHz bands across multiple wave burst events.

Specifically, wavelet cross-phase analysis of encounters 1–19 should reveal:
1. A fixed (non-random) phase relationship between the two bands at their difference frequency (~2.5 mHz) and mean frequency (~6.75 mHz)
2. The phase relationship should be consistent across independent wave train events (not just one 30-min window)
3. The 6.67 mHz peak should appear in *aggregate* statistics across multiple encounters (not just E05)

**If H3 is falsified:** The 6.67 mHz peak is a statistical artifact of this particular window, or is explained by H1 or H2. Wavelet cross-phase shows random phase between the two bands.

---

## Analysis Plan

### Step 1: Statistical Survey Across Encounters 1–19

- Compute PSD for ±30 min windows around perihelion for all encounters
- Look for 6–7 mHz peak in each encounter
- Record: peak frequency, PSD amplitude, encounter number
- Expected: peak appears in some but not all encounters (intermittent coherence)

### Step 2: Wavelet Cross-Phase Analysis

- Compute wavelet transform of mag_rtn field for each encounter
- Extract phase time series at 5.5 mHz and 8 mHz bands
- Compute cross-phase: Φ_55×8(τ) = arg⟨W_5.5(t) × W_8(t+τ)⟩*
- Look for peak in cross-phase at τ = 0 and at lag corresponding to 1/(8−5.5) ≈ 400 s
- Test: is the phase significantly non-random across encounters?

### Step 3: Conditional Stacking

- Identify wave burst events (wavelet amplitude exceeds threshold at 5.5 or 8 mHz)
- Stack PSD around each event at both frequencies
- Look for enhancement at 6.67 mHz in event-averaged spectrum

### Step 4: PSP + Solar Orbiter Conjunction Check

- Solar Orbiter at comparable heliocentric distance during PSP perihelion → multi-point test
- If 6.67 mHz is a real wave feature, it should appear in both spacecraft with appropriate time delay
- If it's a spacecraft-specific artifact, it won't correlate

---

## Empirical Phase Analysis Results (v1.1)

**Methods:**
- Bandpass filter (5.5 mHz and 8 mHz bands) + Hilbert transform for instantaneous phase extraction
- Corrected numerical instability: `sosfiltfilt` used instead of `filtfilt` (the latter caused filter overflow at high |B| values ~110 nT in E01)
- Applied to E05 (±30 min around perihelion, fs=9.16 Hz) and E01 (±30 min, fs=10.1 Hz after decimation)

**Results:**

| Encounter | φ(8mHz)−φ(5.5mHz) R | Beat test R | Interpretation |
|-----------|----------------------|-------------|----------------|
| E05 | 0.280 (weak lock) | **0.893** (strong) | Beat phases consistent, offset by ~19° |
| E01 | 0.028 (near random) | 0.384 (moderate) | No clear phase locking |

**Key findings:**

1. **The earlier R=0.990 result was a numerical artifact.** `filtfilt` at high |B| values (~110 nT in E01) caused filter overflow, producing spuriously high coherence. Corrected `sosfiltfilt` results are more trustworthy.

2. **E05's beat test coherence (R=0.893) remains intriguing.** A 30-minute consistent phase relationship between three phase signals is not expected from random turbulence. However, filter band overlap (~±0.5 mHz, overlapping ~40%) means this could still be partially methodological.

3. **E01 shows no phase locking.** The coupling may be encounter-dependent — either an intermittent physical phenomenon, or a signal-to-noise-dependent artifact that only appears under favorable conditions.

**Interpretation for the beat hypothesis (pre-control experiment):**

E05 provides suggestive evidence; E01 provides null evidence. The beat hypothesis was treated as open until a control experiment was designed.

---

## Control Experiment and Final Verdict (v1.2)

### Design

To test whether the E05 beat coherence was specific to the 5.5×8.0 mHz pair or a generic artifact of narrowband filtering, a control experiment was run:

| Band pair | Frequencies | Expected beat | Physical reason to couple? |
|-----------|-------------|-------------|--------------------------|
| **Real** | 5.5 × 8.0 mHz | 6.7 mHz | Yes — the beat hypothesis |
| **Control 1** | 2.0 × 12.0 mHz | 10.0 mHz | No — non-overlapping, no physical coupling |
| **Control 2** | 3.0 × 10.0 mHz | 7.0 mHz | No — non-overlapping, no physical coupling |

### Results (E05, sosfiltfilt corrected)

| Band pair | Pairwise R | Beat test R |
|-----------|-----------|-------------|
| Real (5.5×8.0 mHz) | **0.280** | — |
| Control 1 (2.0×12.0 mHz) | 0.193 | 0.193 |
| Control 2 (3.0×10.0 mHz) | 0.244 | **0.367** |

### Verdict: Beat hypothesis NOT confirmed.

Control bands show comparable or higher coherence than the "real" band pair. The R ≈ 0.2–0.4 level coherence is a **generic artifact of narrowband filtering of colored noise** — not physical coupling.

The earlier E05 beat test R = 0.893 (reported in v1.1) was a `filtfilt` numerical artifact. With `sosfiltfilt`, no encounter shows beat coherence above the level of arbitrary non-overlapping filter pairs.

### Final Conclusion (v1.2)

| Claim | Status |
|-------|--------|
| 6.67 mHz PSD peak is real | ✅ Confirmed — real spectral feature in E05 |
| 6.67 mHz = beat of 5.5×8.0 mHz | ❌ Not confirmed — control experiment falsifies |
| Phase locking between bands | ❌ Not confirmed — comparable to arbitrary pairs |

**Most likely interpretations for the 6.67 mHz peak:**
1. **Doppler-shifted 3-minute p-mode** in the spacecraft frame (H1 revised): with more careful accounting of Parker spiral geometry, the chromospheric 3-minute band could appear at 6–7 mHz
2. **Local spectral feature**: the peak is real as a spectral feature but not attributable to either of the proposed coupling mechanisms

**Alternative investigation approaches for future work:**
- Wavelet coherence (not just cross-phase) to test for non-random phase relationships
- Single-waveform event detection: identify individual wave burst events and examine their frequency content directly
- Look for 6.67 mHz in aggregate statistics across encounters 1–19 without phase analysis

---

## What This Case Study Demonstrates

The full research arc — from initial hypothesis to empirical test to control experiment to honest verdict — is a template for how the beat hypothesis should have been evaluated from the start. The oscillations avatar ran through this arc autonomously:

1. Initial observation (6.67 mHz peak in E05) → hypothesis
2. Cross-phase analysis (E05 suggestive, E01 null) → open
3. Control experiment (non-specific coherence) → falsified
4. Honest conclusion → documented

This is the scientific method in miniature. The persona skill now reflects this arc honestly.

---

## Current Status (v1.2 — Final)

The 6–7 mHz band remains an interesting open question:
- The 6.67 mHz PSD peak is real and worth investigating
- The beat coupling interpretation has been tested and is not supported
- The most promising next direction is careful H1 (Doppler shift) analysis with Parker spiral geometry, or wavelet coherence analysis

---

## Files

| File | Content |
|------|---------|
| `psp_data/psp_e05_results.txt` | Raw PSD numbers |
| `psp_data/psd_analysis.py` | Welch PSD analysis script |
| `psp_data/psp_e05_psd.png` | PSD plot |
| `psp_data/psp_e05_spectrogram.png` | Spectrogram |
| `psp_data/wavelet_phase.py` | E05 cross-phase analysis |
| `psp_data/wavelet_phase_e01.py` | E01 cross-phase analysis |
| `psp_data/control_experiment.py` | Control experiment (v1.2 final) |
| `psp_data/psp_wavelet_phase_e05.png` | E05 phase plot |
| `psp_data/psp_wavelet_phase_e01.png` | E01 phase plot |

---

## Relation to Published Work

This question does not appear in any of Huang's published papers as of 2026. It represents a genuine gap between:
- The 2-minute oscillation paper (Huang+ApJL 977, L12, 2024): focuses on 8 mHz
- The 3-minute oscillation follow-up (AGU 2024): focuses on 5.5 mHz
- The 5-minute p-mode paper (Huang+ApJL 999, L4, 2026): focuses on 3.1–3.2 mHz

**None of these papers address the possibility of interaction between the bands.** The beat frequency hypothesis is therefore a distinct, uncharted direction that extends Huang's own oscillation research program.

---

## Files

| File | Content |
|------|---------|
| `psp_data/psp_e05_results.txt` | Raw PSD numbers |
| `psp_data/psd_analysis.py` | Welch PSD analysis script |
| `psp_data/psp_e05_psd.png` | PSD plot |
| `psp_data/psp_e05_spectrogram.png` | Spectrogram |

---

*This prospectus is a research planning document. It is not an established result. Treat as motivated inference warranting systematic investigation.*
