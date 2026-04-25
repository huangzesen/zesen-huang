# zesen-huang

> **Built with [Lingtai](https://github.com/your-lingtai-link)** — the agent runtime that makes this persona possible. Lingtai runs a network of specialized AI agents that research, cross-validate, and assemble a sourced persona from public academic records. See [impersonate-meta](https://github.com/huangzesen/impersonate-meta) for the open-source methodology behind this recipe.

---

**A sourced persona skill for Zesen Huang** — solar physicist, UCLA (Marco Velli group).

This recipe installs the complete Zesen Huang persona into a Lingtai agent. The agent network researched 18+ papers, extracted 9 research themes, built 11 domain skills, and assembled the four-piece profile (biography, voice, values, relationships) — all with traceable sources.

## How to Impersonate Zesen Huang

1. **Clone and import** this recipe into a Lingtai project:
   ```bash
   git clone https://github.com/huangzesen/zesen-huang.git
   ```
2. **Open** your Lingtai project, run **`/setup`** → pick "Custom recipe" → point at `zesen-huang/`
3. **Say:** `"act as Zesen Huang"` — the agent loads the persona and can answer questions, write abstracts, or discuss research in his voice and style
4. **Be specific:** `"Write a referee report on a paper about switchbacks as curved field lines"` or `"Explain the Alfvénon to a first-year graduate student"`

The agent draws from:
- **Domain skills** — wave action, MHD turbulence, PSP observations, oscillations
- **Method cards** — how he thinks, not just what he knows
- **Profile** — biography, values, relationships
- **Voice** — argumentation structure, metaphors, tone

## What's Included

```
zesen-huang/
├── .recipe/
│   ├── recipe.json
│   ├── greet/greet.md
│   └── comment/comment.md
└── huang-zesen/
    ├── huang-zesen/SKILL.md         # entry point + loading table
    ├── huang.bib                    # 35 BibTeX entries
    ├── profile/                     # biography, voice, values, relationships
    ├── methods/SKILL.md           # 10 method cards (VM001–VM010)
    ├── paper-analysis/            # 18+ papers, 9 research themes
    ├── huang-alfven-physics/      # wave action, Alfvénon, switchbacks
    ├── huang-oscillations/        # 2/3/5-min p-modes
    ├── huang-turbulence-spectrum/  # two types of 1/f range
    ├── huang-psp-observations/     # PSP mission, CIRs, heating
    ├── huang-mhd-turbulence/       # expanding-box model, residual energy
    ├── psp-spectral-analysis/      # Welch PSD, Hilbert phase workflow
    └── voice/SKILL.md            # writing style, argumentation
```

## Research Themes

1. 1/f spectrum — two types (fast/Alfvénic vs. slow/mixed)
2. Wave action conservation in expanding solar wind
3. Alfvénon — exact nonlinear MHD soliton
4. Switchbacks reinterpretation (curved field lines)
5. MHD turbulence in expanding flows
6. Proton/electron heating from coherent structures
7. Coronal oscillations — 2-min, 3-min, 5-min p-modes
8. Gaussianity Scalogram — structure classification
9. 6–7 mHz transition band

## Key Papers

| Paper | Year |
|-------|------|
| Solitary Alfvén Waves (Alfvénon) — arXiv:2512.02292 | 2025 |
| What are Switchbacks? — arXiv:2512.12585 | 2025 |
| 5-min Oscillations from PSP — arXiv:2511.10906 | 2025 |
| Two Types of 1/f Range — ApJL 990:L34 | 2025 |
| 2-min Oscillations — ApJL 977:L12 | 2024 |
| MHD Turbulence: Residual Energy & Intermittency — ApJ 2025 | 2025 |
| Gaussianity Scalogram — ApJL 973:L26 | 2024 |
| Wave Action Conservation — ApJ 935:60 | 2022 |

## Known Limitations

| Item | Status |
|------|--------|
| Oral presentation style | ⚠️ [unverified] — no public video/audio found |
| PhD institution, degree year | ⚠️ [unverified] |
| Citation counts | Slightly stale (April 2026) |

## Source Discipline

Every claim is traceable:
- **Verifiable** → citekey to published source
- **Behavioral** → ⚠️ [unverified] where audio/video not found
- **Fabricated** → NEVER

## License

MIT — use freely, credit appreciated.
