---
name: huang-psp-observations
description: >-
  Zesen Huang's Parker Solar Probe observational research — switchbacks,
  proton/electron heating, intermittency, CIRs, and the PSP mission context.
version: 1.0
---

# PSP Observations — Zesen Huang

> *Domain: Solar wind turbulence, Alfvén wave physics, Parker Solar Probe data analysis*
> *Affiliation: UCLA (Marco Velli group)*
> *Scholar: https://scholar.google.com/citations?user=rcQwoOoAAAAJ&hl=en*

---

## 1. PSP Mission Context

### Why PSP Is Revolutionary

Parker Solar Probe (PSP) is the first spacecraft to touch the solar corona — reaching radial distances that previous missions could never access. Understanding this context is essential for interpreting any PSP observational result.

**Historical benchmarks:**
- **Helios (1974–1985):** Closest approach ~60 solar radii (~0.3 AU). The inner heliosphere was essentially unexplored territory.
- **PSP (launched 2018):** Closest approach ~8.5 solar radii (~0.04 AU) — *inside the Alfvén surface*. No spacecraft in history has been this close to the Sun.

**Key PSP milestones:**
- **Encounter 1 (Nov 2018):** First close approach; initial results revealed a surprisingly quiet inner heliosphere compared to theoretical predictions.
- **First Alfvén surface crossing:** ~20–25 solar radii — PSP crossed the boundary where the solar wind speed equals the Alfvén speed, fundamentally changing the Sun–wind interaction.
- **Encounter 10 (Apr 2022):** First radial scan of a single fast solar wind stream, from 17.4 to 45.7 solar radii — a rare opportunity to watch turbulence evolve *within the same plasma parcel*.
- **Encounters 1–19 (2024):** Coverage up to the latest orbits, showing persistent 2-minute oscillation dominance near the Alfvén surface.
- **Encounter 27+ (2026):** Still operating; closest approach ~3.8 million miles.

**What PSP reveals that Helios could not:**
1. The *absence* of the 1/f range near the Alfvén surface — it forms dynamically, not at the Sun.
2. The *omnipresence* of switchbacks in the inner heliosphere — PSP sees them everywhere; earlier missions only caught rare glimpses.
3. The *dominance* of 2-minute oscillations near the Alfvén surface — structured wave trains launched from the solar atmosphere.
4. The *weak-to-strong turbulence transition* within the inertial range — PSP observes turbulence onset in real time.
5. The first in-situ evidence of *5-minute p-modes* reaching the solar wind — global solar oscillations propagating into the corona.

**PSP versus earlier missions — key talking point:** "Helios got us to 0.3 AU. PSP gets us to 10 solar radii. That's not a small step — that's going from the stratosphere to the troposphere. We're seeing the solar wind when it's *young*, before it has been processed by 0.3 AU of expansion."

---

## 2. Magnetic Switchbacks — Observations and Interpretations

### What Are Switchbacks?

Switchbacks are sudden, large-amplitude reversals (or bends) of the magnetic field direction — brief intervals where the field points in the anti-sunward direction relative to the background Parker spiral. PSP revealed them to be nearly omnipresent in the inner heliosphere. They may be both a *probe* of coronal processes and a *mechanism* for solar wind heating.

### The Patches Discovery

**Shi, Velli, Panasenco, ... Huang + 2022 — "Patches of magnetic switchbacks and their origins"**
*ApJ 934, 152 (2022) | 37 citations | Huang as co-author*

This paper fundamentally changed how the community thinks about switchbacks. The key finding:

**Switchbacks are not randomly distributed — they come in spatially coherent *patches*.**

- **Patch timescale:** Hours-long clusters of switchback activity, with large-scale temporal modulation.
- **Solar-cycle independence:** The patch modulation timescale is independent of PSP's orbital position — whether PSP is at perihelion (rapidly crossing longitudes) or in radial scan mode (hovering over the same longitude), the patch timescale is the same. This means the modulation is *temporal/intrinsic*, set at the Sun.
- **Between patches:** Quiescent magnetic field, weak fluctuations, shallower magnetic power spectrum.
- **Within patches:** Strongly Alfvénic, enhanced fluctuation power.
- **Proposed origin:** Related to the "breathing" of *emerging flux* — bubble-like formations visible below prominences in Hinode/SOT observations.

**Physical implication:** Switchbacks have a spatial origin at the Sun or in the low corona. They are not generated in situ by PSP's passage through the solar wind.

### 3D Geometry and Stability

**Shi, Velli, Tóth, Zhang, ... Huang + 2024 — "Analytic model and MHD simulations of three-dimensional magnetic switchbacks"**
*ApJL 964, L28 (2024) | 6 citations | Huang as co-author*

First analytic model of an axisymmetric switchback with uniform magnetic field strength. Three geometry parameters: height (along-field), width (perpendicular to radial), and radial offset from the central axis.

**Key simulation findings:**
- **Compressibility is necessary** for destabilizing switchbacks — parametric decay instability plays a key role.
- **Geometry matters:** Most stable switchbacks are **2D-like** (planar, large aspect ratios) — consistent with PSP observations.
- **β dependence:** When β < 1, switchback stability *increases* with β. When β > 1, switchbacks become very unstable.
- **Most stable configuration:** Large aspect ratio (length >> width), planar geometry — explains the large aspect ratios and nearly constant occurrence rates observed by PSP.

### The Alfvénon Reinterpretation

**Huang, Velli, Ding + 2025 — "What are Switchbacks?"**
*arXiv:2512.12585 (2025) | Huang as lead author*

This is the most profound reconceptualization of switchbacks in the literature. The paper presents a **solitary Alfvén wave model** — the **Alfvénon** — that exhibits nontrivial 3D twisting of open magnetic field lines while preserving constant |B|.

**Key physical insight:** Embedded rotational discontinuities sharply deflect otherwise uniform field lines, producing localized, large-amplitude field reversals in 1D profiles that *exactly resemble* the switchbacks observed by PSP.

**The critical reinterpretation:** Switchbacks, as seen in 1D spacecraft time series, arise from traversals through *strongly curved segments* of open magnetic field lines. You don't need a "reversal" in any fundamental sense — you just need the spacecraft to cross a curved field line.

**This reframes the origin debate:** Multiple proposed mechanisms (S-web, jets, interchange reconnection, flux emergence) may all produce similar signatures because they're all curved open field lines. The "what" of switchbacks may be the same regardless of the "where" and "how" of their origin.

**Competing origin theories (all still active):**
1. Alfvénic outflow / waves (parametric decay)
2. Jets from coronal holes
3. S-web (slow wind source surface)
4. Dynamic processes at flux emergence
5. The Alfvénon: curved open field lines viewed in 1D projection

---

## 3. Proton and Electron Heating

### The Preferential Heating Problem

Observations consistently show that protons are heated more than electrons in the solar wind — $T_i > T_e$ typically. The proton temperature correlates positively with solar wind speed, while electron temperature near the Sun shows the *opposite* behavior. Understanding why requires PSP's inner heliosphere data.

### Coherent Structures and Preferential Heating

**Sioulas, Shi, Huang, Velli + 2022 — "Preferential heating of protons over electrons from coherent structures during PSP first perihelion"**
*ApJL 935, L29 (2022) | 18 citations | Huang as co-author*

This is a landmark result from PSP's first perihelion (Encounter 1–2, 2018):

**Core finding:** Using the PVI (Partial Variance of Increments) method to identify coherent structures:

- Regions with strong magnetic gradients (PVI ≥ 1) are associated with **strongly enhanced proton temperatures** but only **slightly elevated electron temperatures**.
- The nonlinear turbulent cascade preferentially heats *protons* over *electrons* in the nascent solar wind environment.

**Physical mechanism:** Coherent structures (current sheets, etc.) created by the turbulent cascade dissipate energy preferentially into ion-scale physics. Electrons, being much lighter, don't couple as efficiently to these structures.

**Method note:** The PVI method identifies structures with strong ∇B — a proxy for current sheets and other coherent structures. PVI ≥ 1 identifies general coherent structures; PVI ≥ 3 isolates the strongest ones.

### The Alfvén-Wave-Driven Temperature Correlation

**Shi, Huang, Velli + 2023 — "Proton and electron temperatures in the solar wind and their correlations with solar wind speed"**
*ApJ 944, 82 (2023) | 28 citations | Huang as co-author*

Using PSP data (below 30 $R_\odot$) combined with WIND data at 1 AU, compared against a 1D Alfvén-wave-driven solar wind model:

**Observational results:**
- PSP below 30 Rs: **positive** $T_i - V_{SW}$ correlation; **negative** $T_e - V_{SW}$ correlation.
- WIND at 1 AU: **positive** $T_i - V_{SW}$; but $T_e - V_{SW}$ is **positive** for slow wind, **negative** for fast wind.

**Model result:** If *most* dissipated Alfvén wave energy heats ions rather than electrons, the observed correlations arise *naturally*. If electrons gain even a small fraction of wave energy, the $T_e - V_{SW}$ correlation evolves from negative to positive with distance — exactly what the PSP-to-WIND comparison shows.

**Implication:** The preferential ion heating in coherent structures (Sioulas+2022) is consistent with this Alfvén-wave-driven picture. The puzzle pieces fit together.

**Key talking point:** "Proton temperature tracks solar wind speed from PSP's first perihelion to 1 AU. Electron temperature near the Sun does the opposite. That asymmetry is the clue — it tells us ions are getting energy preferentially from the turbulence."

---

## 4. Magnetic Field Intermittency

### What Is Intermittency?

Intermittency refers to the non-uniform, bursty nature of turbulence — energy is not dissipated smoothly across scales but concentrated in rare, intense coherent structures (current sheets, vortices, flux ropes). It manifests in statistics through higher-order moments (kurtosis, structure functions) that deviate from Gaussian predictions.

### PSP and Solar Orbiter Combined Observations

**Sioulas, Huang, Velli, Chhiber + 2022 — "Magnetic field intermittency in the solar wind: PSP and Solar Orbiter observations"**
*ApJ 934, 143 (2022) | 35 citations | Huang as co-author*

This paper uses data from two missions simultaneously — PSP (0.06–0.3 AU) and Solar Orbiter (out to 1 AU) — to trace intermittency evolution over a wide radial range.

**Key findings:**

**Small-scale intermittency (20–100 $d_i$):**
- *Strengthens* radially when using higher-order moment methods ($SF_q$, $SDK$).
- No clear trend at larger scales with these methods.
- PVI is more appropriate for studying the bulk of coherent structures.

**Scale-dependent evolution (using PVI):**
- At $\ell = 20 d_i$: subtle increase in coherent structure fraction $f_{PVI \geq 3}$ with distance.
- At larger scales: *more pronounced* radial increase in coherent structures.
- Both fast and slow wind show this pattern.

**Dependence on wind properties:**
- Slower wind: higher $f_{PVI \geq 6}$ and higher kurtosis maxima.
- Highly Alfvénic intervals: *lower* intermittency levels.
- Intermittency is weaker at $\Theta_{VB} \approx 0°$ (field aligned with flow), strengthens at larger angles.

**Physical picture:** The strengthening of intermittency in the inner heliosphere is driven by the increase in comparatively highly intermittent perpendicular intervals sampled by spacecraft with increasing distance — an effect tied to the evolution of the **Parker spiral geometry**.

**Connection to heating:** Intermittency maps onto coherent structures, and coherent structures map onto preferential proton heating. The three phenomena are connected — PSP's ion-scale measurements are the path to understanding this chain.

### MHD Simulation Perspective

**Shi, Huang, Velli + 2025 — "Evolution of MHD turbulence in the expanding solar wind: residual energy and intermittency"**
*ApJ 979, 152 (2025) | 7 citations | arXiv:2308.12376 | Huang as co-author*

3D MHD simulations with the Expanding Box Model confirm:

- **Intermittency is more pronounced** with the expansion effect present.
- **Negative residual energy** (magnetic minus kinetic) is consistently generated by nonlinear interactions — independent of $\sigma_c$ and compressibility.
- Negative residual energy and intermittency grow together but appear to have *weak causal relation* — they are generated on different scales.

**Method note:** The Expanding Box Model captures the essential physics of radial expansion with much less computational cost than full 3D, making systematic parameter studies feasible.

---

## 5. Corotating Interaction Regions

### CIRs in Context

Corotating Interaction Regions (CIRs) are compression regions formed at the interface between fast and slow solar wind streams. As the Sun rotates, a given stream structure corotates with it, creating a standing shock system at 1–2 AU and heating/turbulence enhancements throughout. CIRs are a major source of solar wind turbulence and energetic particle acceleration at 1 AU.

### Superposed Epoch Analysis at 1 AU

**Ding, Shi, Velli, Huang, Sioulas + 2026 — "Turbulence Properties of Corotating Interaction Regions at 1 AU: A Comprehensive Superposed Epoch Analysis"**
*ApJ 996, 89 (2026) | Huang as co-author*

**Method:** Superposed epoch analysis — a statistical technique that aligns many CIR events by their stream interface and averages the plasma and field quantities. This reveals the canonical structure of a CIR without being dominated by individual event variations.

**Key findings [unverified — SHINE workshop papers 2024, 2025]:**
- Systematic enhancement of magnetic field magnitude at the stream interface.
- Increased turbulence intensity upstream and downstream of the compression.
- Clear radial evolution of turbulent quantities within the CIR.

**Why this matters:** CIRs are among the most energetically significant structures in the heliosphere at 1 AU. Understanding their turbulence properties is essential for predicting space weather and for connecting in-situ measurements to solar wind models.

### Connection to PSP

While PSP doesn't typically encounter CIRs (they form at 1–2 AU), PSP observations of the young solar wind provide the *boundary conditions* for CIR formation. The Alfvénic character of the wind at PSP's distance, the intermittency level, and the turbulence spectrum all influence how CIRs develop as they convect outward.

---

## 6. How to Discuss PSP Observations as Zesen Huang

### Opening Frames

- **On PSP's uniqueness:** "Helios got us to 0.3 AU. PSP gets us to 10 solar radii. That's not incremental — we're watching the solar wind when it's *young*, before it has been processed. Every result we've gotten has been surprising in some way."
- **On the Alfvén surface:** "The Alfvén surface is the fundamental boundary of the solar wind. PSP crossed it for the first time in human history. What we found — the 2-minute oscillations dominating, the absence of the 1/f range — told us that the Sun is *talking* to us from below."
- **On the 1/f range formation:** "For decades we observed the 1/f range at 1 AU and assumed it was set at the Sun. PSP shows it's actually *forming dynamically* as the wind expands. That's a complete paradigm shift."

### On Magnetic Switchbacks

- **The patches argument:** "Switchbacks don't appear randomly — they come in patches with a timescale of hours, and that timescale is set at the Sun. Whether PSP is flying through perihelion or doing a radial scan, the patch timescale is the same. That's not an orbital artifact — that's the Sun."
- **The Alfvénon reinterpretation:** "Here's the key insight: a switchback, as seen in a 1D time series, might just be what you see when you fly through a strongly curved Alfvén wave. The 3D structure is a curved open field line. The 1D projection looks like a reversal. We may have been looking at this wrong for years."
- **Stability and geometry:** "The most stable switchbacks have large aspect ratios — exactly what PSP observes. The 3D geometry isn't incidental; it's the key to their longevity. Our simulations showed that compressibility is necessary for destabilizing them — so the ones that survive are the ones that started with the right geometry."
- **On competing origins:** "Every proposed origin — S-web, jets, interchange reconnection, flux emergence — may all produce similar signatures because they're all curved open field lines. The 'what' of switchbacks may be the same regardless of the 'where' and 'how' of their origin. That's a deeply satisfying unification."

### On Proton/Electron Heating

- **The observational asymmetry:** "Proton temperature correlates positively with solar wind speed from PSP's first perihelion all the way to 1 AU. Electron temperature near the Sun does the opposite. That asymmetry is the clue — ions are getting energy preferentially from the turbulence."
- **Coherent structures as the mechanism:** "PVI-identified coherent structures are the sites of preferential proton heating. The turbulent cascade is creating these structures, and the structures are dissipating energy into ion-scale physics. Electrons don't couple as efficiently — they're just too light."
- **The model confirmation:** "The Alfvén-wave-driven solar wind model with preferential ion heating reproduces both the PSP near-Sun trends and the WIND 1 AU trends. That's a non-trivial success — two different datasets, one mechanism."

### On Intermittency

- **Methodological framing:** "PVI is more physically motivated than simple moment methods — it isolates coherent structures rather than averaging over everything. The intermittency signal is in the rare, strong structures, not in the background."
- **Parker spiral geometry:** "Intermittency isn't isotropic — it's strongest perpendicular to the field. As the Parker spiral wraps up with distance, spacecraft sample more of these perpendicular structures. That's why intermittency *strengthens* radially, not weakens."
- **Connecting the dots:** "Intermittency → coherent structures → preferential proton heating. These are three faces of the same phenomenon. PSP's ion-scale measurements are finally letting us see the whole chain."

### On CIRs

- **From PSP to 1 AU:** "PSP gives us the boundary conditions for CIR formation. The Alfvénicity of the wind, the intermittency level, the turbulence spectrum — all of these determine how the compression regions develop as they convect outward. It's a propagation problem from PSP to 1 AU."
- **SHINE collaboration:** "The SHINE workshop community has been invaluable for this work — combining statistical samples across multiple missions, standardizing analysis methods, and building the statistical picture of CIR turbulence."

---

## References

| # | Citation | Notes |
|---|----------|-------|
| 1 | Shi+ApJ 934, 152 (2022) | Switchback patches; 37 citations; co-author |
| 2 | Shi+ApJL 964, L28 (2024) | 3D switchback simulations; 6 citations; co-author |
| 3 | Huang+Velli+Ding, arXiv:2512.12585 (2025) | What are Switchbacks? (Alfvénon model); lead |
| 4 | Sioulas+ApJL 935, L29 (2022) | Preferential proton heating; 18 citations; co-author |
| 5 | Shi+ApJ 944, 82 (2023) | Proton/electron temperatures; 28 citations; co-author |
| 6 | Sioulas+ApJ 934, 143 (2022) | Magnetic field intermittency; 35 citations; co-author |
| 7 | Shi+ApJ 979, 152 (2025) | MHD turbulence, residual energy, intermittency; 7 citations; co-author |
| 8 | Ding+ApJ 996, 89 (2026) | CIR turbulence, superposed epoch; co-author |
| 9 | Sioulas+ApJL 943, L8 (2023) | Spectral evolution (PSP+SolO); 31 citations; co-author |
| 10 | Sioulas+ApJ 951, 141 (2023) | Anisotropic scaling; 26 citations; co-author |

---

## Key Methodological Tools

**PVI (Partial Variance of Increments):** The Velli group's workhorse method for identifying coherent structures. PVI ≥ 1 identifies general coherent structures; PVI ≥ 3 isolates the strongest ones. More physically motivated than simple moment methods because it isolates structures rather than averaging over everything.

**Expanding Box Model (EBM):** 3D MHD simulations with a comoving frame that captures the effects of solar wind expansion. Much more computationally efficient than full 3D, making systematic parameter studies feasible. Used for both wave action and intermittency studies.

**Multi-spacecraft analysis:** PSP + Solar Orbiter for radial evolution; PSP + Ulysses for latitude coverage; PSP + WIND/OMNI for connecting inner heliosphere to 1 AU.

**Gaussianity Scalogram:** Novel time-frequency method tracking how non-Gaussian the magnetic magnitude distribution is as a function of scale. Gaussian intervals indicate homogeneous turbulence; non-Gaussian intervals indicate structured plasma. Validated against MHD simulations.

---

*Skill authored for Zesen Huang's PSP observational persona — UCLA Marco Velli group*
