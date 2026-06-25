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
----

# Dino Project — Culture Inspection Update

**Date:** 13/04/2026

## Purpose
Inspect the dinoflagellate cultures in **Daigo’s IMK**, **F/2**, and the retained **parent cultures**, and document visible changes relative to previous observations.

## Observations

### Daigo’s IMK cultures

#### SSA01, SSA02, SSA03
- These cultures appear **okay overall by eye**
- More **whitish suspended “cells” / material** were observed floating in the medium compared with earlier observations

#### SSB01
- Appears **more turbid** by eye than before
- Suspended material / “cells” appear to have organized into **sharp, crystal-like clumps**

#### SSE01
- Appears to be **growing better by eye**
- Culture looks **more optically dense**
- This is consistent with prior expectations, since **SSE01** was the strain noted to perform best under autotrophic IMK conditions

### F/2 cultures

#### SSA01, SSA02, SSA03
- Similarly to the **Daigo’s IMK** cultures, these strains appear to be **growing by eye**

#### SSB01
- Also appears **more optically dense** by eye than before
- Unlike the IMK culture, this strain is **not showing the same crystal-like clumps**

#### SSE01
- Starting to show **brownish coloration**

### Parent cultures

#### A01, A02, A03
- Appear **similar to how they were received**
- Possibly showing **slight growth**, with some **suspended material / suspended growth** now visible

#### B01, E01
- Appear more **precipitated**
- The bottom **pellet / settled material** looks more concentrated
- Less suspended matter is visible compared with the A strains

## Documentation
- **Pictures were taken** for visual record and future comparison

## Preliminary interpretation
- Several cultures now appear to show **some degree of growth or increased optical density by eye**
- **SSE01 in Daigo’s IMK** appears to be one of the clearest cases of apparent improvement
- **SSB01** in Daigo’s IMK shows a distinct **crystal-like clumping pattern** that should be examined microscopically
- **SSE01 in F/2** is beginning to develop **brownish coloration**, which should also be followed closely
- Parent cultures remain useful as a visual reference for comparison with the transferred recovery cultures

## Recommended next steps
- Perform **microscopy** on:
	- **SSB01 in Daigo’s IMK**
	- **SSE01 in Daigo’s IMK**
	- **SSE01 in F/2**
	- at least one representative **SSA** culture in each medium
- Perform **cell counts**
- Continue visual tracking with repeat imaging
- If feasible, proceed later with **flow cytometry**
- Continue contamination screening with plating on Marine Broth
---
# Dino Project — Culture Inspection Update

**Date:** 23/04/2026

## Purpose
Inspect the dinoflagellate cultures on day 23 of incubation and document visible differences among strains and media (**Daigo’s IMK** vs **F/2**) based on macroscopic observation by eye.

## Observation conditions
- Inspection performed **by eye only**
- Cultures were gently stirred during inspection to evaluate turbidity, suspended material, and visible pigmentation

---

## Cultures in Daigo’s IMK

### SSA01
- Faint **brownish-colored supernatant**
- Small amount of **whitish precipitate**
- Became **turbid when gently stirred**

### SSA02
- Overall **clear appearance**
- Almost **turbid when stirred**
- Small amount of **whitish precipitate**

### SSA03
- Overall **clear appearance**
- Almost **turbid when stirred**
- Less precipitate than the other A clades

### SSB01
- Faint **brownish-colored supernatant**, slightly more pronounced than in SSA01
- Still shows **feathery / crystal-like clumps**
- Clumps become apparent when gently stirred

### SSE01
- **Brownish-colored precipitate**
- Became **turbid and colored when stirred**
- Appears to be the **best-growing strain in the IMK set** by eye, based on stronger color and turbidity

---

## Cultures in F/2

### SSA01
- **Brownish color tint**
- Some **white precipitate**
- **Turbid when stirred**

### SSA02
- Overall **clearish appearance**
- Some **white precipitate**
- **Turbid when stirred**

### SSA03
- Some **brownish color** tint
- Fairly larger amount of **precipitate**
- **Turbid when stirred**

### SSB01
- **Stronger brownish color** tint
- More precipitate than the A strains
- **Turbid and almost brown-colored when stirred**

### SSE01
	- **Strongest brownish color** tint
- Largest visible precipitate
- **Turbid and colored when stirred**

---

## Parent cultures
- All parent cultures appear **okay by eye**
- The small pellet at the bottom remains present, similar to previous observations

---

## New cultures (small bottles)
- Additional small-bottle cultures prepared by Maayan were also inspected
- In both **F/2** and **Daigo’s IMK**, most showed a **light brownish tint**
- Exceptions: **A01** and **A03**, which did not show the same brownish glimpse

---

## Preliminary interpretation
- By day 23, several cultures now show more obvious **brownish pigmentation** and **turbidity on stirring**, which is more suggestive of suspended pigmented biomass than in the earlier inspections
- **SSE01** remains the strain that appears most convincingly established, especially in **Daigo’s IMK**, and also shows the strongest visible signal in **F/2**
- **SSB01** continues to show a distinct structural phenotype in **Daigo’s IMK** (feathery / crystal-like clumps), while in **F/2** it appears more strongly pigmented
- **SSA02** still appears comparatively pale / whitish in both media, which may be consistent with weaker performance under standard IMK/F/2 conditions
- Parent cultures remain visually stable and continue to serve as a useful reference

## Recommended next steps
- Perform **microscopy**
	- prioritize **SSB01 in IMK**
	- prioritize **SSE01 in IMK and F/2**
	- include **SSA02** in both media
- Perform **cell counts**
- If feasible, perform **flow cytometry**
- Continue visual documentation with repeat photographs
- Continue contamination screening as needed
  
# NblA - NblB Proyect

## 03/05/2026

On 02/05/2026, Jenia picked colonies from the transformation plates and inoculated overnight cultures at 37 °C. The following day, plasmid extraction was performed using the GenElute PLN70-1KT miniprep protocol.

In parallel, additional preparatory work was carried out in the lab by Maayan and Moran, including locating kanamycin stocks, autoclaving materials, and preparing reagents.

Maya and I prepared the kanamycin stock solution and aliquots for future use.

---

## 05/05/2026

With the assistance of Raneen, I picked colonies corresponding to:
- NblA S26C
- NblB

The colonies were inoculated into LB + kanamycin liquid cultures and incubated overnight at 37 °C.

---

## 06/05/2026

Maayan inoculated large LB cultures using the overnight BL21 cultures containing:
- NblA S26C
- NblB

Glycerol stocks were prepared for both BL21 expression strains:
- NblA S26C BL21
- NblB BL21

The large cultures were induced with IPTG:
- 200 µL IPTG added to each culture

After preparation, the glycerol stocks were flash-frozen in liquid nitrogen and stored in the -80 °C freezer.

# Dino Project — Culture Inspection Update

**Date:** 14/05/2026

## Purpose
Inspect all dinoflagellate cultures by eye, document their current apparent condition, and note relevant project updates.

## Observations
- All Dino cultures were checked **by eye only**
- Overall, the cultures now show **strong coloration** and **obvious growth**
- This pattern is seen in both the main cultures and the small cultures

### Daigo’s IMK / F/2 cultures
- In general, all strains appear to be growing well by eye
- The main exception is **A02 in Daigo**, which appears to be **lagging behind** relative to the other cultures

### Small cultures
- The small cultures appear to follow a **similar pattern** to the main cultures
- Most show clear visible growth and coloration

### Parent cultures
- The parent cultures are **not looking as sharp**
- They are now at **very small volumes**
- They show **less coloration** and **less precipitation / settled biomass** than in the last inspection
- This may indicate that they would benefit from:
	- additional fresh medium
	- transfer to fresh vessels / medium
	- or both

## Additional update
- **Casein shipment was received at the beginning of this week**

## Preliminary interpretation
- By eye, the cultures now appear **substantially more established** than in the earlier inspections
- Most strains show clear signs consistent with **continued growth**
- **A02 in Daigo** remains the main culture of concern in the current inspection
- The parent cultures appear more stressed or depleted than the transferred working cultures, likely due to their smaller remaining volume and lack of refreshment
- With casein now available, strain-specific supplementation can be considered later if needed, especially for cultures that continue to underperform

## Suggested next steps
- Consider **adding fresh medium and/or transferring the parent cultures**
- Continue routine visual monitoring
- If possible, follow up with:
	- **microscopy**
	- **OD / absorbance measurements**
	- **cell counts**
- Keep comparing **A02 in Daigo** to its paired culture in F/2 and to the other A strains
- If A02 continues to lag, consider whether a **casein- and glucose-supplemented condition** should be tested
---
# Dino Project — Culture Inspection Update

**Date:** 09/06/2026

## Purpose
Inspect the refilled **F/2** cultures and the **Daigo recovery cultures**, and record the current visual status together with the latest OD@750 measurements.

## Observations

### Refilled F/2 cultures
- By eye, the **refilled F/2 cultures** appear to be doing fine
- **SSB01_F2** measured **OD@750 = 0.6**
	- previous timepoint: **0.33** on **02/06/2026**
- This suggests a clear increase relative to the previous week

### Daigo recovery cultures
- The **Daigo (_D) recovery cultures** have lost a substantial amount of volume
- Their coloration is now **less intense** than the refilled F/2 cultures
- **SSB01_Dai** measured **OD@750 = 0.8**

## Preliminary interpretation
- The refilled **F/2 cultures** appear visually stable and continue to perform well
- **SSB01_F2** shows an increase in OD@750 from **0.33 to 0.6** over one week
- The **Daigo recovery cultures** appear more depleted by eye at this stage, mainly due to:
	- lower remaining volume
	- weaker visible coloration relative to the refilled F/2 cultures
- Despite that, **SSB01_Dai** still gave a relatively high **OD@750 = 0.8**, which suggests that optical density and visual appearance are not fully aligned and should be interpreted cautiously

## Notes
- Current OD values were measured at **750 nm**
- Since previous discussion suggested that **Cell Cultures mode** and **A600** may be more appropriate for future standardized tracking, these OD@750 values should be treated mainly as **internal comparative readings** within the same workflow

## Suggested next steps
- Continue monitoring both **F/2 refilled** and **Daigo recovery** cultures
- Standardize future absorbance measurements if possible
- Pair OD measurements with:
	- **microscopy**
	- **cell counts**
	- visual inspection
- Consider refreshing or re-feeding the **Daigo recovery cultures** if volume loss continues
----
## **Dino project — F/2 scale-up initiation**

Today I performed a microscopic evaluation of the **F/2 cultures** and verified the presence of **living cells**. Based on that check, I initiated an **F/2 scale-up** following [[Dino F2 Medium Scale-Up Protocol]].

### **Purpose**

Start the first F/2 scale-up step while preserving the current ~100 mL cultures as backup / maintenance lines.

### **Starting point**

- All five strains were in **F/2**
- Current cultures were at approximately **100 mL**
- Scale-up target: **250 mL final volume**
- Scale-up vessel: **500 mL Erlenmeyer**
- Backup strategy: keep original cultures and refill them with the removed volume of fresh F/2

### **Work performed**

- Verified living cells by microscopy before transfer
- Prepared fresh sterile **1× F/2 medium**
- Set up work inside the **BC-11B** using a no-flame sterile workflow
- Labeled original cultures as **backup** and new flasks as **scale-up**
- Gently resuspended each source culture before transfer
- Initiated scale-up according to the protocol parameters in [[Dino F2 Medium Scale-Up Protocol]]
- Covered flasks with **gauze**
- Returned cultures to incubator at **26°C**, **12:12 light:dark**

### **Notes**

- This marks the start of the first F/2 scale-up round
- The backup line for each strain was preserved
- Next follow-up should include visual inspection, OD tracking, and notes on color / clumping / recovery after transfer