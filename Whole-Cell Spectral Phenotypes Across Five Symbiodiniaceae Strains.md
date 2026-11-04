---
title: "Intact-Cell UV–Vis Phenotypes Across Five Symbiodiniaceae Strains"
author: "Carlos Alberto Martínez"
date: "2026-09-23"
geometry: margin=1.2cm
fontsize: 8.5pt
---

## Question

**Do the five Symbiodiniaceae strains show reproducible differences in their
intact-cell UV–Vis spectra, and what generates those differences?**

Intact-cell spectra are treated as **optical phenotypes** containing pigment
absorption together with scattering and effects of cell concentration,
morphology and aggregation. They are **not direct measurements of acpPC
composition**.

---

## Intact-cell spectral phenotype

Each 400–700 nm spectrum was referenced to A750:

$$
A_{\mathrm{rel}}(\lambda)=A(\lambda)-A(750)
$$

Within matched experimental blocks:

$$
D_i(\lambda)=X_i(\lambda)-
\operatorname{mean}\left(X_{\mathrm{other\ 4}}(\lambda)\right)
$$

**51 complete blocks × 5 strains = 255 matched deviation spectra.**

![Matched mean spectral deviation by strain](file:///Users/carlosmartinez/Documents/GitHub/dino-research/results/uvvis/figures/03_matched_mean_deviation_by_strain.png)

**Figure 1.** Mean matched spectral deviation of each strain relative to the
other four strains measured in the same experimental context.

---

## A dominant spectral axis emerges

**PC1 = 93.83% · PC2 = 3.50% · PC3 = 2.05% · PC1–3 = 99.38%**

| PCA | NMDS |
|:--:|:--:|
| ![PCA](file:///Users/carlosmartinez/Documents/GitHub/dino-research/results/uvvis/figures/01_PCA_PC1_PC2_by_strain.png) | ![NMDS](file:///Users/carlosmartinez/Documents/GitHub/dino-research/results/uvvis/figures/11_all_strain_matched_deviation_NMDS.png) |

**Figure 2.** PCA and NMDS of the 255 matched deviation spectra. PCA identifies
a dominant PC1 axis; NMDS independently recovers the distance structure
(stress = **0.024**). SSB01 and SSA03 tend toward opposite ends of this
spectral structure.

---

## Testing the physical origin — S2 terminal sampling

On **23 Sep 2026**, matched S2 samples were collected immediately before
harvest from:

**SSA01 · SSA02 · SSA03 · SSB01 · SSE01**

The same cultures are now being characterized using complementary measurements:

$$
\boxed{
\text{intact cells}
\rightarrow
\text{OD}_{750} + \text{cell count/scatter/autofluorescence}
\rightarrow
\text{methanol pigment extract}
}
$$

For pigment extraction, cells were pelleted at **8,000 × g, 10 min, 4°C**,
the culture supernatant removed, and pigments extracted from the cell pellet
with methanol under reduced light.

### [FIGURE 3 — Methanol pigment spectra: 350–750 nm]

Pigment spectra will be compared both directly and after normalization to
**cell number**, allowing the intact-cell spectral phenotype to be separated
from differences in biomass/cell concentration.

---

## Working interpretation

$$
\boxed{
\text{strain} \times \text{culture state/history}
\rightarrow
\text{cellular + pigment phenotype}
\rightarrow
\text{intact-cell spectrum}
}
$$

The existing data show a **strong, low-dimensional optical phenotype**, but
PC1 cannot yet be assigned to pigment composition, cell concentration,
scattering, morphology, aggregation or acpPC.

**Current test:** determine whether the strain-specific intact-cell spectral
axis persists in **cell-normalized methanol pigment extracts**.

**Next:** intact cells → extracted pigments → membrane/thylakoid fractions →
**acpPC-enriched complexes**.