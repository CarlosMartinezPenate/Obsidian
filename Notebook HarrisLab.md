# 🧬 [[NbLB]] — [[AlphaFold]]3 Analysis (Monomer)

**Date:** 2026-03-16  
**System:** *Acaryochloris marina* MBIC 11017  
**Target:** [[NbLB]]  
**Constructs analyzed:**
- Protein-only (no tag)
- C-terminal His₆-tagged construct

---

## 🧠 Objective

Evaluate:
- Folding state of [[NbLB]]
- Presence of disorder
- Effect of His-tag
- Implications for expression, purification, and structural work

---

## 📊 Summary of Results

### 🔹 Global Fold

- Predicted structure is **compact and predominantly α-helical**
- No evidence of multi-domain flexibility
- Likely a **single-domain protein**

**Confidence:**
- pTM ≈ 0.89–0.90 → **high confidence global fold**
- Consistent across all 5 model seeds → **high reproducibility**

---

## 📈 Disorder Analysis ([[pLDDT]]-based)

### 🔹 Protein-only construct (220 aa)

**Low-confidence residues (<70):**
- Residue 2 (His)
- Residue 219 (Glu)
- Residue 220 (Pro)

**Very low confidence (<50):**
- None

**Interpretation:**
- Structure is **almost entirely ordered**
- Only minor flexibility at **N- and C-termini**

---

### 🔹 His-tag construct (226 aa)

**Low-confidence residues (<70):**
- Residues 1–2 (N-terminus)
- Residues 219–220 (C-terminal edge)

**Very low confidence (<50):**
- Residues 221–226 → **His₆ tag**

**Interpretation:**
- Core fold unchanged
- His-tag behaves as **flexible tail (expected)**

---

## 🧬 Structural Interpretation

### 🔹 Fold Type

- Predominantly **α-helical bundle**
- Likely:
  - scaffold protein
  - protein–protein interaction module
  - lyase-like fold (consistent with literature)

---

### 🔹 Flexibility

- Minimal intrinsic disorder
- Flexibility limited to:
  - termini
  - short loops
- No large disordered regions

---

## 🔬 Experimental Implications

### ✅ Expression

- Likely to express **solubly**
- No indication of intrinsic instability

---

### ✅ Purification

- His-tag construct should behave normally
- Tag does not disrupt folding
- Expect:
  - soluble fraction
  - clean IMAC purification

---

### ✅ SEC behavior (prediction)

- Likely **monodisperse**
- Possible:
  - monomer
  - weak oligomerization (to be tested)

---

### ⚠️ Crystallization

**Favorable features:**
- compact fold
- low disorder

**Potential caveats:**
- flexible termini
- His-tag tail

**Future optimization options:**
- tag removal (TEV)
- terminal truncations (if needed)

---

## 🧪 Thermal Stability (DSF)

**Conclusion:**
- Not required at this stage

**Use later for:**
- buffer optimization
- ligand binding detection
- construct comparison

---

## 🧠 Biological Interpretation

- [[NbLB]] is likely:
  - **independently folded**
  - not intrinsically disordered
  - structurally stable without partners

- Suggests role as:
  - **interaction scaffold**
  - rather than folding-dependent partner

---

## 🚀 Next Steps (Computational)

Once sequences are available:

- [ ] [[NbLB]] + APCβ
- [ ] [[NbLB]] + CpcA
- [ ] [[NbLB]] + NblA (control)

Focus:
- interface formation
- reproducibility
- interface confidence (PAE)

---

## 🚀 Next Steps (Experimental — future)

1. Expression test
2. Solubility check
3. IMAC purification
4. SEC profiling
5. Decide:
   - apo structure vs complex-driven project

---

## 🧠 Key Takeaway

> [[NbLB]] is a structurally well-behaved protein candidate.  
> The main challenge is likely **function and interactions**, not folding or stability.

---

# 01/04/2026
# Dino Project — Receiving Update
## Arrival and initial handling

The cultures were picked up by Moran and arrived at the lab at **12:30 PM**.

At approximately **5:15 PM**, the package was opened. Inside the bubble-wrap bag were:
- **5 Falcon tubes**, one for each strain
- **1 Falcon tube with Daigo’s 50× solution**

Carlos took photos of the parent cultures before transfer. The tubes were then gently inverted / turned to mix. No OD was taken initially, and the first checks were **visual only**.

## Initial distribution into recovery flasks

Maayan distributed the strains into the prepared flasks:
- **1 set of 5 flasks for Daigo/IMK**
- **1 set of 5 flasks for F/2**

For each flask:
- **98 mL ASW**
- **2 mL of the corresponding strain culture **
- **2 mL of the corresponding medium: 50x Diago or 50x F/2**

The flasks were then transferred to the incubator using the preset prepared by Huichi.

The leftover parent cultures, approximately **1 mL each**, were also kept and placed in the incubator.

## Media and storage notes

- From the original **F/2 bottle**, **10 F/2 aliquots** were prepared and stored at **-20°C** for future use.
- **Daigo’s IMK 50×** was stored at **room temperature** at Moran's bench.

## Immediate observations

- Initial assessment was **visual only**
- No OD was taken at arrival
- No microscopy, cell counts, or cytometry were performed yet

## Planned next steps

- Prepare **Marine Broth plates** for the parent cultures
	- this may also help with a **visual contamination / axenicity screen**
- Measure **OD**
- Perform **cell counts**
- Perform **microscopy**
- Perform **flow cytometry** in the future
---
# Dino Project — Culture Inspection Update

**Date:** 05/04/2026

## Purpose
Inspect the incoming dinoflagellate cultures after transfer into **Daigo/IMK** and **F/2** recovery flasks, document visible changes, and identify priorities for the next round of evaluation.

## Background
The strains had previously been transferred into:
- **5 flasks with Daigo/IMK**
- **5 flasks with F/2**
with the parent cultures retained in the original Falcon tubes.

## Observations

### General observations
- The cultures were inspected in the incubator by eye.
- At this time, **no obvious visible growth** was noted in any strain or flask.
- No clear macroscopic color increase or obvious bloom was observed in either medium.

### F/2 flasks
- Sedimentation of **cell-like / biofilm-like material** was observed in the F/2 flasks.
- Some **dark particulate, sand-like, and fiber-like material** was also present.
- None of the F/2 flasks appeared completely clear by eye.
- In **SSE01 + F/2**, a localized **golden-brown spot** was observed that may represent a small growth-associated aggregate or deposit.

### Daigo/IMK flasks
- Sedimentation of **cell-like / biofilm-like material** was also observed in the Daigo flasks.
- Some **dark particulate / fiber-like material** was present in the Daigo cultures as well.
- None of the Daigo cultures appeared perfectly clear by eye; all showed some degree of **cloudiness / turbidity**.
- In **SSE01 + Daigo**, **suspended whitish cloudiness** was noted.

### Parent cultures
- All parent cultures remained sedimented at the bottom of the original Falcon tubes, similarly to how they appeared upon arrival.
- No obvious discoloration of the parent cultures was noted.

## Preliminary interpretation
At this stage, the observations are still **too early and too qualitative** to distinguish confidently between:
- normal post-transfer settling,
- aggregation of algal cells,
- particulate carryover from the original cultures or media,
- or possible contamination.

The absence of obvious visible growth by eye is **not yet sufficient to interpret as failure**, since changes in these cultures may take longer to become macroscopically apparent.

## Planned next steps
- Perform **microscopy** on selected flasks and parent cultures
- Perform **cell counts**
- Begin a **Marine Broth contamination screen** / preliminary visual screen for possible contamination
- Perform **flow cytometry** later, if feasible
- Continue monitoring visible changes in both **Daigo/IMK** and **F/2** cultures

## Priority for follow-up
The following conditions should be prioritized for microscopy and closer inspection:
- **SSE01 + F/2**
- **SSE01 + Daigo**
- at least one representative parent culture
- one representative flask from another strain in each medium