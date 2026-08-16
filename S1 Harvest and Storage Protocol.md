---
title: S1 Harvest and Storage Protocol
aliases:
  - S1 Harvest
  - Symbiodiniaceae Harvest
  - Cell Harvest for PCP
tags:
  - protocol
  - dinoflagellates
  - harvesting
  - storage
  - PCP
status: Draft
---

# S1 Harvest and Storage Protocol

## Purpose

Harvest S1 Symbiodiniaceae cultures and preserve the biomass for future protein extraction and PCP purification.This protocol **ends with frozen cell pellets**. Cell disruption and extraction are performed later.

---

# Scope

Applicable to:

- [[SSA01]]
- [[SSA02]]
- [[SSA03]]
- [[SSB01]]
- [[SSE01]]

---

# Principle

This protocol is based on the harvesting conditions reported by PCP purification studies, which harvested cells by refrigerated centrifugation before extraction. The published protocols proceed immediately to protein extraction. In this workflow, harvesting is separated from extraction by freezing the pellets for later processing.

---

# Equipment

- Thermo Sorvall RC6 Plus refrigerated centrifuge
- Fiberlite F14-6×250y fixed-angle rotor
- 250 mL centrifuge bottles
- 50 mL Falcon tubes
- Refrigerated pipettes
- Ice bucket
- Labels
- Marker
- -80°C freezer

---

# Reagents

- Sterile filtered artificial seawater (ASW), pre-chilled to 4°C

---

# Before Harvest

Record the final condition of every culture.

| Strain | Volume (mL) | Colour | OD750 | Microscopy | Notes |
| ------ | ----------: | ------ | ----- | ---------- | ----- |
| SSA01  |             |        |       |            |       |
| SSA02  |             |        |       |            |       |
| SSA03  |             |        |       |            |       |
| SSB01  |             |        |       |            |       |
| SSE01  |             |        |       |            |       |

Take photographs if desired.

---

# Procedure

## 1. Chill the centrifuge

Set the centrifuge to **4°C** and allow the rotor to equilibrate before loading samples.

---

## 2. Prepare bottles and recover culture

Label one centrifuge bottle for each strain.

Before harvesting, record the mass of each culture flask:

**Flask + culture mass before harvest**

Gently swirl each culture immediately before pouring so that settled cells are uniformly suspended.

Use a **dedicated clean paintbrush for each strain** to gently dislodge cells attached to the inner glass surface.

Avoid vigorous scraping or excessive foaming.

Transfer the entire recoverable S1 culture into the corresponding centrifuge bottle.

After transfer, reweigh the original culture flask:

**Flask mass after harvest**

Record both values.

| Strain | Flask + culture before (g) | Flask after harvest (g) | Culture mass recovered (g) |
|---|---:|---:|---:|
| SSA01 | | | |
| SSA02 | | | |
| SSA03 | | | |
| SSB01 | | | |
| SSE01 | | | |

Calculate:

$$
m_{\mathrm{culture,recovered}}
=
m_{\mathrm{flask+culture,before}}
-
m_{\mathrm{flask,after}}
$$

Because the culture medium has a density close to seawater, the recovered culture mass can be used as an approximate recovered volume:

$$
V_{\mathrm{recovered}}
\approx
\frac{
m_{\mathrm{culture,recovered}}
}{
\rho_{\mathrm{culture}}
}
$$

If culture density is not measured, use the approximation:

$$
1\ \mathrm{g}
\approx
1\ \mathrm{mL}
$$

for routine harvest tracking.

> [!note]
> This approximation is adequate for comparing harvest recovery between strains and dates, but it is not a true volumetric measurement because artificial seawater is slightly denser than pure water.

---

# Yield Measurements

## A. Culture Recovery Yield

Culture recovery yield estimates how much of the starting culture was successfully recovered from the flask.

If the initial culture volume is known:

$$
\mathrm{Culture\ Recovery\ Yield\ (\%)}
=
\frac{
V_{\mathrm{recovered}}
}{
V_{\mathrm{culture,before\ harvest}}
}
\times 100
$$

Example:

If the flask contained approximately 80 mL before harvest and the mass difference indicates 77 g recovered:

$$
\mathrm{Recovery}
=
\frac{77}{80}
\times 100
=
96.3\%
$$

This measurement captures losses from:

- residual liquid in the flask
- cells attached to glass
- liquid retained by the paintbrush
- spills or transfer losses

---

## B. Wet Biomass Yield

To estimate harvested biomass, weigh the final storage Falcon before use.

Record:

**Empty Falcon mass**

After the second centrifugation and removal of ASW, weigh:

**Falcon + wet pellet mass**

Calculate:

$$
m_{\mathrm{wet\ biomass}}
=
m_{\mathrm{Falcon+pellet}}
-
m_{\mathrm{empty\ Falcon}}
$$

Record:

| Strain | Empty Falcon (g) | Falcon + wet pellet (g) | Wet biomass (g) |
|---|---:|---:|---:|
| SSA01 | | | |
| SSA02 | | | |
| SSA03 | | | |
| SSB01 | | | |
| SSE01 | | | |

---

## C. Wet Biomass Yield per Culture Volume

Calculate:

$$
Y_{\mathrm{wet}}
=
\frac{
m_{\mathrm{wet\ biomass}}
}{
V_{\mathrm{recovered}}
}
$$

Recommended reporting unit:

**mg wet biomass / mL culture**

Therefore:

$$
Y_{\mathrm{wet}}
=
\frac{
m_{\mathrm{wet\ biomass}}\times1000
}{
V_{\mathrm{recovered}}
}
$$

---

## D. Optional Biomass Yield per Cell

If a cell concentration was measured before harvest:

$$
N_{\mathrm{total}}
=
C_{\mathrm{cells}}
\times
V_{\mathrm{recovered}}
$$

where:

- $C_{\mathrm{cells}}$ = cells/mL
- $V_{\mathrm{recovered}}$ = mL

Then:

$$
\mathrm{Wet\ biomass\ per\ }10^6\mathrm{\ cells}
=
\frac{
m_{\mathrm{wet\ biomass}}\times10^9
}{
N_{\mathrm{total}}
}
$$

This can help determine whether strains differ substantially in average cell biomass.

---

# Recommended Yield Record

| Strain | Starting culture (mL) | Culture recovered (g ≈ mL) | Recovery (%) | Wet biomass (g) | Wet biomass yield (mg/mL) |
|---|---:|---:|---:|---:|---:|
| SSA01 | | | | | |
| SSA02 | | | | | |
| SSA03 | | | | | |
| SSB01 | | | | | |
| SSE01 | | | | | |

> [!important]
> For comparisons between strains, **wet pellet mass is only a semi-quantitative biomass measurement** because residual ASW trapped in the pellet contributes to the measured mass.
>
> Use the same centrifugation, aspiration, and weighing procedure for every strain to make the comparison as consistent as possible.

> [!tip]
> If accurate biomass yield becomes important later, determine **dry weight** from a defined aliquot or normalize biomass using cell number, chlorophyll content, or total protein after extraction.

---

## 3. Harvest cells

Centrifuge at **8,000 × g** for **10 minutes** at **4°C**

---

## 4. Inspect pellets

After centrifugation, record:

- pellet colour
- pellet size
- pellet compactness
- supernatant appearance

| Strain | Pellet size | Pellet colour | Supernatant clarity | Notes |
|----------|------------|---------------|--------------------|------|
| SSA01 | | | | |
| SSA02 | | | | |
| SSA03 | | | | |
| SSB01 | | | | |
| SSE01 | | | | |

---

## 5. Remove culture medium

Carefully aspirate the supernatant without disturbing the pellet.

Do **not** wash the pellet with extraction buffer.

---

## 6. Transfer to storage tube

Add only enough **cold sterile filtered ASW** to resuspend the pellet.

Typical volume:

**2–5 mL**

Resuspend gently using a pipette.

Transfer the suspension into a labelled 50 mL Falcon tube.

> [!note]
> The ASW is used only as a transfer medium.
>
> It is **not** intended to begin protein extraction.

---

## 7. Pellet again

Centrifuge:

**8,000 × g**

for

**10 minutes**

at

**4°C**

---

## 8. Remove ASW

Carefully aspirate the ASW.

Leave only enough liquid to avoid disturbing the pellet.

Do not attempt to dry the pellet completely.

---

## 9. Freeze

Immediately place the Falcon tubes at

**−80°C**

Store until extraction.

Avoid repeated freeze–thaw cycles.

---

# Storage Record

| Strain | Tube ID | Frozen | Storage location | Notes |
|----------|---------|---------|-----------------|------|
| SSA01 | | | | |
| SSA02 | | | | |
| SSA03 | | | | |
| SSB01 | | | | |
| SSE01 | | | | |

---

# Next Protocol

The frozen pellets will later be processed using:

1. Resuspension in

   **50 mM Tricine + 20 mM KCl, pH 7.5**

2. High-pressure homogenization
   (EmulsiFlex C3)

3. Clarification

4. Ammonium sulfate fractionation

---

# Notes

## Why use ASW?

This protocol uses a small volume of cold sterile filtered ASW only to facilitate transferring the pellet from the harvest bottle into a storage tube.

The ASW is removed during the second centrifugation and is **not** intended to remain with the pellet during storage.

## Why not use extraction buffer now?

Keeping the pellet intact until the day of extraction has several advantages:

- extraction buffer is prepared fresh
- all strains are processed under identical conditions
- minimizes time that proteins spend in extraction conditions
- avoids storing cells submerged in lysis buffer

---

# References

Jiang J. et al.
*Characterization of the peridinin–chlorophyll a-protein complex in the dinoflagellate Symbiodinium.*
Biochimica et Biophysica Acta (2012). Characterization of the peridinin–chlorophyll a-protein complex in the dinoflagellate Symbiodinium.pdf

Supasri K.M. et al.
*Characterisation and Bioactivity Analysis of Peridinin-Chlorophyll a-Protein (PCP) Isolated from Symbiodinium tridacnidorum CS-73.*
Journal of Marine Science and Engineering (2021). Characterisation and Bioactivity Analysis of Peridinin-Chlorophyll a-Protein (PCP) Isolated from Symbiodinium tridacnidorum CS-73.pdf