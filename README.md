# zesen-huang

**A sourced persona skill for Zesen Huang** — solar physicist, UCLA (Marco Velli group).

This recipe installs the complete Zesen Huang persona into a lingtai agent: ~4,600 lines of structured skills across 11 domain files, a 35-entry bibliography, 10 method cards, and the four-piece profile (biography, voice, values, relationships).

## What's Included

```
zesen-huang/
├── .recipe/
│   ├── recipe.json          # manifest — library_name: huang-zesen
│   ├── greet/greet.md      # first-contact message
│   └── comment/comment.md  # behavioral DNA (how to impersonate Huang)
└── huang-zesen/            ← primary library: the persona itself
    ├── SKILL.md                 # entry point + loading table
    ├── huang.bib                # 35 BibTeX entries
    ├── profile/                  # biography, voice, values, relationships
    ├── methods/SKILL.md         # 10 method cards (VM001–VM010)
    ├── paper-analysis/          # 18+ papers, 9 research themes
    ├── huang-alfven-physics/   # wave action, Alfvénon, switchbacks
    ├── huang-oscillations/     # 2/3/5-min p-modes
    ├── huang-turbulence-spectrum/  # two types of 1/f range
    ├── huang-psp-observations/     # PSP mission, CIRs, heating
    ├── huang-mhd-turbulence/       # expanding-box model, residual energy
    ├── psp-spectral-analysis/      # Welch PSD, Hilbert phase workflow
    └── voice/SKILL.md             # writing style, argumentation

impersonate-meta/               ← reference library: methodology for building personas
└── impersonate-meta/
    ├── SKILL.md                 # v2 methodology
    ├── failure-catalog.md
    ├── primers/, scripts/, templates/
```

## Research Themes Covered

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

## How to Import

1. **Clone** this repo anywhere:
   ```bash
   git clone https://github.com/huangzesen/zesen-huang.git
   ```
2. **Open** your lingtai-tui project
3. **Run `/setup`** — pick "Custom recipe", then point at the cloned `zesen-huang/` directory
4. The TUI copies `.recipe/` and registers `huang-zesen` + `impersonate-meta` as libraries
5. **Run `/cpr all`** to wake all agents

> **Note:** Recipes are not auto-discovered. Use `/setup` → "Custom recipe" each time.

## How to Use the Persona

Load the entry point:
```
library(action="load", name="huang-zesen")
```

Then read `huang-zesen/SKILL.md` for the full loading table.

**For generating Huang-like scientific text:**
→ `huang-zesen/profile/voice.md` + `huang-zesen/voice/SKILL.md`

**For domain expertise:**
→ `huang-zesen/huang-alfven-physics/SKILL.md` (or the relevant domain skill)

**For how he thinks:**
→ `huang-zesen/methods/SKILL.md` (10 method cards, VM001–VM010)

## Known Limitations

| Item | Status |
|------|--------|
| Oral presentation style | ⚠️ [unverified] — no public video/audio found |
| PhD institution, degree year | ⚠️ [unverified] |
| Citation counts | Slightly stale (April 2026) |

## Source Discipline

Every claim in this persona is traceable:
- **Verifiable** → citekey to published source
- **Behavioral** → ⚠️ [unverified] where audio/video not found
- **Fabricated** → NEVER

## License

MIT — use freely, credit appreciated.
