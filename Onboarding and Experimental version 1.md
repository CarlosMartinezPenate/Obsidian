
Plan for NblB in *Acaryochloris marina* MBIC 11017

**Project date:** 2026-03-16  
**PI:** Dvir Harris  
**Primary lab contact:** Maayan  
**Related collaborator/context:** Manu  
**Organism:** *Acaryochloris marina* MBIC 11017  
**Target protein:** NblB  
**Related proteins:** NblA, PBS subunits, candidate lyases, possible Clp-associated factors  
**Current context:** Maayan has already worked on NblA, PBS assays, and ITC. NblB ownership is now transitioning to you.

---

## Executive overview

This plan is designed to help me onboard efficiently into the NblB project, align with Maayan’s existing workflows, and start generating usable biochemical material within the first 2–3 weeks. The overall goal is to move from **lab integration and plasmid readiness** to **test expression, purification, biophysical quality control, interaction mapping, XL-MS planning, and early crystallization readiness**.

This version is written for Obsidian and uses **reference placeholders** instead of broken export links. I can later replace these placeholders with full formatted references, Zotero citekeys, or a bibliography.

---

## Scientific framing

The phycobilisome (PBS) is a large cyanobacterial light-harvesting complex that can represent a major fraction of soluble cellular protein. Under nutrient or environmental stress, PBS remodeling or degradation allows the cell to rebalance light harvesting, recover nitrogen-rich biomass, and adapt its metabolism. NblA is a well-established small adaptor-like factor involved in PBS degradation, especially through interactions with phycobiliproteins and proteolytic machinery. NblB has been associated with PBS restructuring and chromophore-related steps, but its precise biochemical role can be context-dependent and may extend beyond a simple one-line “bilin removal” model. Recent literature suggests that NblA, NblB, lyases, phycobiliproteins, and chromophore transfer processes may form a more dynamic remodeling network than previously assumed. [REF_KARRADT_2008] [REF_HU_2019] [REF_NADEL_2025]

For this reason, the NblB project should be approached not only as a basic expression-and-purification target, but as a node in a **protein interaction and structural biology problem** involving:

- PBS organization and remodeling
- possible binding to biliproteins or lyases
- possible effects on chromophore transfer or detachment
- potential dependence on protein state, cofactors, salt, oligomerization, or partner proteins

---

## Working hypotheses

### Core biological hypotheses

1. **NblB is likely to be structurally tractable**, possibly easier than larger PBS proteins or fragile complexes.
2. **NblB may require a partner or ligand for its biologically relevant state**, even if it purifies alone.
3. **NblB biochemical activity may not be obvious in a simple standalone assay**, so interaction assays and structural context are important early.
4. **NblB purification conditions may need to preserve either solubility, oligomeric state, or weak partner binding**, not just maximize yield.
5. **XL-MS and crystallization should be planned early**, but only after confirming sample quality and monodispersity.

### Practical experimental hypotheses

1. NblB may express well in *E. coli*, but solubility and folding state remain uncertain.
2. Small proteins can look “clean” on SDS-PAGE while still being misfolded, aggregated, or nonfunctional.
3. Standard Ni-NTA purification alone will not be enough; **SEC and quality control are essential**.
4. If NblB is unstable alone, the project may pivot quickly toward:
   - buffer optimization
   - truncations
   - tag swaps
   - partner co-expression
   - ligand-assisted stabilization
   - complex-based structural studies

---

## Literature-derived practical lessons

Below is a cleaned synthesis of the papers Maayan shared and the related paper you identified. The main purpose here is not to force exact buffer transfer from other systems, but to identify **recurring useful design principles**.

### 1. NblA / related small-protein purification can require stabilization measures
Across the literature on small PBS-related factors, recurring stabilizers include:

- moderate to high salt
- glycerol
- mild detergents in some contexts
- magnesium in ATP-dependent interaction systems
- phosphate-based buffers for PBS-associated material
- in difficult cases, denaturant-assisted solubilization/refolding

**Practical lesson for NblB:** start with a conservative soluble-protein workflow, but be ready to test alternative salts, phosphate vs Tris/Hepes, reducing conditions, and low concentrations of mild detergent if the sample behaves poorly. [REF_KARRADT_2008] [REF_NBLA_PULLDOWN] [REF_NBLD_XLMS]

### 2. PBS integrity is often highly buffer-sensitive
Studies involving PBS isolation or dissociation repeatedly show that **phosphate concentration and ionic strength matter a lot**. Intact PBS and core-associated material are often stabilized in high-phosphate systems, whereas lower ionic strength can favor dissociation or redistribution.

**Practical lesson for NblB:** for any assay involving intact PBS, core fractions, or larger assemblies, do not assume the same buffer used for purified recombinant NblB is suitable for PBS interaction work. Use a separate PBS-preserving workflow. [REF_HU_2019] [REF_PBS_CROSSLINKING] [REF_NADEL_2025]

### 3. NblA/NblB biology may involve partners, not just isolated proteins
The literature supports interactions among Nbl proteins, lyases, biliproteins, and degradation-related factors in ways that may be conditional and state-dependent.

**Practical lesson for NblB:** negative results with isolated recombinant NblB do not necessarily mean “no biology.” They may mean:
- wrong buffer
- wrong oligomeric state
- missing partner
- missing chromophore state
- missing ATP / Mg2+ / cofactor
- wrong substrate state (apo vs holo, trimer vs dissociated component)

[REF_HU_2019] [REF_KARRADT_2008]

### 4. XL-MS should be done on a defined biochemical question
Cross-linking mass spectrometry works best when the question is specific, such as:
- Does NblB bind NblA?
- Does NblB bind a specific PBS component?
- Does NblB bind a lyase?
- Does the interaction change with phosphate, salt, ATP, chromophore state, or pH?

**Practical lesson for NblB:** do not start with “cross-link everything.” First define the best candidate complex and verify that the interaction is at least weakly supported by orthogonal data. [REF_NBLD_XLMS] [REF_HU_2019]

---

## Recommended project logic

The project should progress in this order:

1. **Lab integration and construct clarity**
2. **Expression feasibility**
3. **Purification and sample-quality assessment**
4. **Biophysical stabilization**
5. **Minimal interaction testing**
6. **Focused XL-MS design**
7. **Crystallization screening**
8. **Escalation to more advanced structural routes if needed**

This avoids wasting time on XL-MS or crystallization using poor sample.

---

# Week 1 — Day-by-day onboarding plan

## Day 1 — Orientation, context capture, and project mapping

### Main goals
- Understand the exact state of the NblB project
- Identify all available constructs, strains, plasmids, notebooks, and raw data
- Learn the local purification workflow from Maayan rather than reinventing it

### Tasks
- Meet with Maayan and ask for a **full project handoff walkthrough**
- Review:
  - what has been done for NblA
  - what has already been attempted for NblB
  - what “expected to crystallize easily” is based on
  - whether any NblB construct has already been cloned, transformed, expressed, or purified
- Ask to see:
  - plasmid maps
  - cloning notes
  - gel images
  - chromatography traces
  - ITC results from related systems
  - any previous SEC profiles
  - any SDS-PAGEs for NblB or similar proteins
- Create an Obsidian project note:
  - `NblB_Project_Master_Note`
- Create subnotes:
  - `NblB_Constructs`
  - `NblB_Expression`
  - `NblB_Purification`
  - `NblB_Interactions`
  - `NblB_XLMS`
  - `NblB_Crystallization`
  - `Questions_for_Maayan`

### Deliverables by end of day
- One-page project map
- A list of physical materials and digital files
- A clarified statement of the immediate next experiment

---

# Day 2 — Plasmid audit and sequence-level verification
**Project:** NblB (Acaryochloris marina MBIC 11017)  
**Goal:** Confirm exactly what construct(s) I’m working with and eliminate ambiguity before wet work.  
**Date:** {{date}}  
**Software:** SnapGene / Benchling  
**Reference protein:** *A. marina* MBIC 11017 NblB (expected sequence source: ________)  

---

## Main goals
- [ ] Confirm vector + expression system for each plasmid
- [ ] Confirm tag identity/position + cleavage strategy
- [ ] Confirm ORF is correct (frame, start/stop, fusion junctions)
- [ ] Confirm exact protein sequence expected from THIS plasmid (including extra residues)
- [ ] Generate a clean construct table for later expression screening + purification planning

---

## Inputs
### Files / links
- Plasmid files (SnapGene .dna / GenBank / Benchling links):
  - [ ] Construct 1: ________
  - [ ] Construct 2: ________
  - [ ] Construct 3: ________
- Reference NblB sequence (FASTA / accession / lab-verified):
  - [ ] Source: ________
  - [ ] FASTA stored in: ________

### Assumptions to confirm
- Host system: (E. coli / other) ________
- Intended induction system: (T7 / arabinose / lac / other) ________
- Intended purification: (His / Strep / GST / MBP / none) ________

---

## Construct inventory table (Obsidian)
> Fill one row per plasmid. Keep *notes* short but specific.

| Construct ID | File / link | Backbone | Promoter | Antibiotic | Tag(s) | Tag position | Linker | Cleavage site | Mutation status | Insert length (aa / bp) | Expected MW (kDa) | pI (opt) | Notes |
|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|---|
| NblB-__ |  |  |  |  |  | N / C |  |  | WT / mut |  /  |  |  |  |
| NblB-__ |  |  |  |  |  | N / C |  |  | WT / mut |  /  |  |  |  |

**Legend / conventions**
- **Backbone:** e.g., pET-28a, pET-21, pBAD, pGEX, pMAL, etc.
- **Promoter:** T7, lac, tac, arabinose, etc.
- **Tag(s):** His6, StrepII, GST, MBP, SUMO, AviTag, etc.
- **Linker:** exact AA sequence if present (e.g., GSGS, GGGGSx2)
- **Cleavage:** TEV / 3C / Thrombin / SUMO protease / none
- **Mutation status:** WT; point mutation(s); truncation; codon-optimized; etc.

---

## Per-construct sequence-level verification checklist
> Do this for EACH plasmid and tick boxes only when verified.

### A) Map-level verification (easy wins)
- [ ] Backbone identified (plasmid name + size + origin)
- [ ] Promoter identified (T7/lac/etc.)
- [ ] Antibiotic marker confirmed (Kan/Amp/Cm/etc.)
- [ ] Tag identity confirmed from annotated features (not assumptions)
- [ ] Tag position confirmed (N-terminus vs C-terminus relative to NblB)
- [ ] Cleavage site identified and sequence confirmed (e.g., TEV: ENLYFQ/G)
- [ ] Terminator / stop region present and correct
- [ ] Resistance + promoter consistent with intended host strain (e.g., T7 → BL21(DE3))

### B) ORF integrity (must-pass)
**Goal:** confirm the *actual translated protein* is what I think it is.

- [ ] Correct **start codon** used for fusion (ATG or as designed)
- [ ] Correct **reading frame** from tag → linker → NblB (no frameshift)
- [ ] No premature stop codon in fusion junctions
- [ ] Stop codon placement correct (end of NblB OR end of tag depending on design)
- [ ] Tag orientation correct (e.g., His-tag is in-frame and not reverse-complement)
- [ ] Any extra residues after cloning are identified (common from restriction sites / Gibson scars)

**Record extra residues explicitly**
- N-terminus extra AA (before NblB begins): ________
- C-terminus extra AA (after NblB ends): ________

### C) Compare to expected *A. marina* NblB sequence
- [ ] Align translated NblB region to reference NblB (100% match expected?)
- [ ] Differences recorded (substitution/insertion/deletion):
  - [ ] Position ___: ___ → ___
  - [ ] Position ___: ___ → ___
- [ ] If “codon optimized”: confirm **protein sequence** matches reference even if DNA differs

### D) Codon usage and expression risk flags (quick triage)
> These are not automatic “bad”, just things to note before wet work.

- [ ] Rare codon clusters (Arg/Leu/Ile) noted if visible in DNA
- [ ] Very high GC% regions noted
- [ ] Long N-terminus rich in hydrophobics (signal peptide / TM risk?)
- [ ] Internal repeats / strong secondary structure risk in mRNA noted (if obvious)
- [ ] If problems anticipated: note possible host choices (e.g., Rosetta) or expression temps

**Notes / risk flags**
- Rare codons suspected? yes/no — details: ________
- Solubility concerns (sequence features): ________

---

## How to extract the “true expected protein sequence” (do this once per construct)
> End product: a FASTA sequence that includes tags/linkers/cleavage remnants exactly.

1. **Translate the correct ORF** (tag→NblB fusion)
2. Copy/paste the amino-acid sequence into a FASTA block and label clearly:

```fasta
>ConstructID__|Backbone__|TagPos__|Cleavage__|ExpectedProtein
MHHHHHH... (full AA sequence including tag/linker and any scar residues)

### Deliverables by end of day
- Clean `NblB_Constructs` note
- Final choice of first construct to test
- Ranked backup constructs if the primary one fails

---

## Day 3 — Expression strategy design and transformation setup

### Main goals
- Prepare the first expression attempt rationally
- Avoid committing too early to a single host or condition

### Recommended first-pass design
Use a **small matrix**, not one condition only.

### Suggested variables
- Host:
  - BL21(DE3)
  - one backup strain if available (for example Rosetta, C41/C43, or similar)
- Temperature:
  - 37°C short induction
  - 18°C overnight induction
- IPTG:
  - 0.1 mM
  - 0.5 mM

### Tasks
- Transform the main NblB construct into the chosen expression strain(s)
- Plate with correct antibiotic selection
- Prepare a simple expression decision tree in notes:
  - soluble band
  - insoluble band
  - no expression
  - degradation pattern

### Deliverables by end of day
- Fresh transformed plates
- First expression matrix decided in writing

---

## Day 4 — Colony confirmation and mini-expression planning

### Main goals
- Confirm transformants
- Prepare for efficient expression screening

### Tasks
- Pick colonies
- Set up colony PCR or direct inoculation, depending on local lab practice
- Start overnight starter cultures
- Prepare all basic buffers ahead of time

### Core buffers to prepare
#### Generic lysis buffer A
- 20–50 mM Tris or HEPES, pH 7.5–8.0
- 150–500 mM NaCl
- 5–10% glycerol
- 10–20 mM imidazole
- optional: 1 mM DTT or TCEP
- protease inhibitor cocktail

#### Alternative phosphate test buffer
- 20 mM potassium phosphate, pH ~7.2
- 300–500 mM NaCl
- 5–10% glycerol
- 10–20 mM imidazole

#### Insoluble-protein rescue buffer
- same as lysis buffer
- plus 1–2 M urea if needed for exploratory rescue only

### Important note
I would **not** start NblB directly with harsh denaturation/refolding unless expression clearly shows insolubility and no soluble route works. Small proteins can refold badly but still look fine on gels.

### Deliverables by end of day
- Starter cultures
- Buffers ready
- Sample labels and SDS-PAGE plan ready

---

## Day 5 — Small-scale expression screen

### Main goals
- Determine whether NblB expresses
- Determine whether it is soluble
- Avoid moving to large scale too early

### Tasks
- Run small-scale expression test for the selected matrix
- Collect:
  - uninduced sample
  - induced whole-cell sample
  - soluble fraction
  - insoluble fraction
- Analyze all by SDS-PAGE
- Record:
  - observed molecular weight
  - expression intensity
  - solubility
  - evidence of degradation
  - host-dependent differences

### Decision logic
#### Case A — Soluble expression is visible
Move to larger-scale purification next week.

#### Case B — Expression but mostly insoluble
Try:
- lower temperature
- lower IPTG
- shorter induction
- different host
- different tag orientation if available

#### Case C — No convincing expression
Check:
- plasmid
- antibiotic
- induction conditions
- rare codon issue
- promoter strain compatibility

### Deliverables by end of day
- Expression screen gel
- Ranked best condition
- Go/no-go decision for scale-up

---

## Day 6 — Optional practice on PBS-related material

### Main goals
- Start learning the assay context early
- Understand what a “good PBS prep” looks like

### Tasks
- Shadow Maayan on PBS isolation, if feasible
- Observe:
  - intact PBS workflow
  - buffer dependence
  - fraction appearance
  - absorbance / fluorescence readout
- Create a note:
  - `PBS_Assay_Context_for_NblB`

### Deliverables by end of day
- Practical familiarity with the assay context
- Notes on what material NblB may eventually be tested against

---

## Day 7 — Consolidation and planning review

### Main goals
- Convert week 1 into a structured phase transition
- Make week 2 executable

### Tasks
- Review all week 1 results with Maayan
- Present:
  - construct chosen
  - expression condition selected
  - major risks
  - what support is needed
- Update the roadmap

### Deliverables by end of day
- Week 2 plan agreed
- Calendar of instrument use
- Reagent/order list if needed

---

# Strategic outlook for Weeks 2–3

## Week 2 — Expression, purification, and sample quality

### Objective
Obtain the first biochemically interpretable NblB sample.

---

## Step 1 — Scale-up expression

### Recommended approach
Use the best small-scale condition from week 1.

### Initial scale
- 250 mL to 1 L total culture
- Do not begin with very large scale unless the expression screen is clearly good

### Collect samples for records
- pre-induction
- post-induction
- pellet mass
- soluble vs insoluble fractions

---

## Step 2 — Primary purification

### First purification route
If His-tagged:
- Ni-NTA or Co-IMAC capture
- wash gradient with modest imidazole
- elute in controlled fractions

### Good first wash strategy
- 10–20 mM imidazole in binding buffer
- then 20–40 mM wash if contaminants are high

### Elution
- 150–300 mM imidazole

### Important note for NblB
Because NblB is likely small, monitor:
- resin nonspecific losses
- tag cleavage artifacts
- co-eluting low-MW contaminants
- whether the band is really the target and not a host contaminant

### Essential QC
- SDS-PAGE of all steps
- concentration estimate
- note if sample precipitates after elution

---

## Step 3 — SEC is mandatory, not optional

A small protein can appear “pure” by IMAC but still be:

- aggregated
- oligomeric
- degraded
- tag-dependent
- non-monodisperse

### SEC goals
- determine apparent oligomeric state
- remove aggregates
- assess monodispersity
- identify whether the sample has a single usable peak

### Suggested SEC buffer starting points
#### Buffer set 1
- 20 mM HEPES pH 7.5
- 150 mM NaCl
- 2–5% glycerol
- 1 mM DTT or TCEP

#### Buffer set 2
- 20 mM Tris pH 8.0
- 300 mM NaCl
- 5% glycerol

#### Buffer set 3
- 20 mM potassium phosphate pH 7.2
- 300 mM NaCl
- 5% glycerol

### Record
- retention volume
- peak symmetry
- shoulder formation
- concentration dependence if possible

---

## Step 4 — Minimal biophysical characterization

Before XL-MS or crystallization, do at least some of the following:

- SEC reproducibility
- DLS if available
- thermal shift / nanoDSF if available
- CD if available and practical
- concentration-dependent stability check
- freeze-thaw stability check

### Goal
Identify a buffer where NblB is:
- soluble
- monodisperse
- stable for at least 1–3 days at 4°C
- not highly aggregation-prone

---

## Week 3 — Interaction strategy, focused XL-MS, and crystallization readiness

## Part A — Define the interaction question

Do **not** jump directly into “NblB with whole PBS” unless there is a strong reason.

### Better interaction sequence
1. NblB alone
2. NblB + NblA
3. NblB + candidate lyase(s)
4. NblB + individual PBS component(s)
5. only then more complex assemblies if justified

### Best first interaction readouts
- SEC shift
- pull-down / co-elution
- MST
- BLI or SPR if available
- native gel if suitable
- limited DSF stabilization by partner

---

## Part B — Refined XL-MS strategy

### XL-MS should only be attempted once one of these is true:
- SEC shift suggests a complex
- pull-down is reproducible
- thermal stabilization suggests interaction
- prior literature strongly supports a specific pair

### Recommended first XL-MS targets
Rank these in this order unless Maayan has stronger prior evidence:
1. NblB + NblA
2. NblB + one lyase candidate
3. NblB + one purified PBS subunit or defined core component

### Cross-linker strategy
Use at least one amine-reactive linker first:
- BS3 or DSS class

Then only expand if needed.

### Practical XL-MS workflow
1. Verify both proteins individually by SDS-PAGE and SEC
2. Mix under one defined buffer condition
3. Let the complex equilibrate
4. Run a no-crosslink control
5. Run a low, medium, high cross-linker series
6. Check on SDS-PAGE first
7. Only then submit the best condition for MS prep

### Important variables to test
- salt
- phosphate vs HEPES/Tris
- pH
- ATP/Mg2+ if partner biology suggests it
- presence/absence of glycerol
- chromophore state if relevant

### Major caution
High phosphate can help preserve PBS-related assemblies but may complicate some downstream workflows. Keep the XL-MS buffer compatible with both the biology and the analytical pipeline.

---

## Part C — Crystallization strategy

### When to start
Start crystallization only after you have:
- a single dominant SEC peak
- reasonable concentration behavior
- no obvious heavy aggregation
- enough material to reproduce prep

### Recommended crystallization path
#### Stage 1: apo-NblB screens
Use commercial sparse-matrix screens first.

#### Stage 2: stabilized-NblB screens
If apo sample is unstable, try:
- salt variation
- pH variation
- partner-assisted stabilization
- tag removal vs tag retention
- mild ligand/cofactor conditions
- phosphate vs non-phosphate buffer

#### Stage 3: complex crystallization
Only if apo protein behaves poorly but an interaction is convincing.

### Especially for small proteins
Consider the following if crystals fail:
- fusion construct
- surface entropy reduction mutants
- nanobody/scFv-assisted crystallization later
- co-crystallization with peptide or partner fragment

---

## Structural biology escalation tree

### If apo NblB is stable and monodisperse
Go hard on crystallization.

### If apo NblB is stable but tiny / feature-poor
Consider:
- complex crystallography
- oligomer stabilization
- AlphaFold-guided construct optimization

### If apo NblB is unstable but a partner stabilizes it
Shift project toward **complex structural biology**, not solo protein.

### If crystallization stalls
Escalate to:
- XL-MS-guided modeling
- SAXS if available
- NMR only if realistic for the construct and expertise
- EM only if a larger assembly becomes central

---

# Scientifically improved buffer strategy for NblB

## Starting recommendation
Because NblB sits at the interface of small-protein biochemistry and PBS-associated biology, I would use a **three-track buffer strategy** instead of one buffer for everything.

### Track A — Recombinant soluble protein purification
Use a standard protein-friendly buffer:
- 20 mM HEPES or Tris
- 150–300 mM NaCl
- 5% glycerol
- 1 mM reducing agent

### Track B — PBS-compatible assay buffer
Use phosphate-based conditions suitable for preserving PBS-associated material:
- potassium phosphate system
- matched ionic strength depending on whether intact PBS or subassemblies are needed

### Track C — interaction challenge buffer panel
A small matrix with:
- low vs moderate salt
- Tris/HEPES vs phosphate
- ± Mg2+
- ± ATP if biologically justified
- ± very low detergent if sample sticks or aggregates

This is better than forcing one “universal” buffer across all project stages.

---

# Refined questions for Maayan

## Construct and sequence
- Which exact NblB construct should I start with, and why that one?
- Has any NblB construct already shown expression, solubility, or purification?
- Is the tag N-terminal or C-terminal, and was that design intentional based on prior experience?
- Do we have alternate constructs, truncations, or tag-swapped variants ready?

## Expression
- Which host worked best for related proteins in this project?
- Was NblA soluble or mostly insoluble in your hands?
- Has anyone already tested NblB expression temperatures or induction conditions?

## Purification
- Which resin and SEC column are the lab standard for this size range?
- Did any previous NblB or NblA sample show oligomerization or strange SEC behavior?
- Was phosphate ever clearly better than Tris/HEPES for sample behavior?

## Biology
- What is the strongest current hypothesis for NblB’s partner or substrate?
- Do you expect NblB to bind NblA directly?
- Do you think NblB should be tested against isolated biliproteins, lyases, or intact PBS first?

## XL-MS
- What exact biological question should XL-MS answer first?
- Which complex would be the highest priority to test?
- Which proteomics pipeline and software does the lab trust most?

## Structural work
- Why do you think NblB should crystallize easily: size, prediction, homology, or prior crystals?
- Do we have any AlphaFold or homology models already?
- Should I prioritize apo structure first or partner-stabilized structure first?

---

# Success criteria for the first three weeks

## Minimum success
- one verified construct
- one clear expression condition
- one purified NblB prep
- one SEC trace
- one stable working buffer

## Strong success
- reproducible soluble prep
- monodisperse SEC peak
- preliminary interaction evidence
- defined XL-MS target pair
- crystallization-ready sample

## Excellent success
- all of the above plus:
- first crystallization trial launched
- first SEC-shift or partner-binding evidence
- first rational structural hypothesis for NblB state/function

---

# Immediate next-action checklist

- [ ] Review plasmid map with Maayan
- [ ] Confirm tag position and vector
- [ ] Transform primary construct
- [ ] Prepare expression matrix
- [ ] Prepare lysis and SEC buffers
- [ ] Run small-scale expression test
- [ ] Decide scale-up condition
- [ ] Book FPLC/SEC time
- [ ] Create Obsidian project notes
- [ ] Define first interaction question for Week 3

---

# Placeholder references

[^1]: REF_GENERAL_NBLA_NBLB_FUNCTION  
[^2]: REF_NBLA_PULLDOWN_SYNECHCOCCUS_2973  
[^3]: REF_KARRADT_2008_BUFFER  
[^4]: REF_KARRADT_2008_GST_CLPC  
[^5]: REF_HU_2019_HIS_BUFFER  
[^6]: REF_HU_2019_GST_BUFFER  
[^7]: REF_HU_2019_GLUTATHIONE_ELUTION  
[^8]: REF_HU_2019_PBS_KPB  
[^9]: REF_NADEL_2025_HIGH_PHOSPHATE_PBS  
[^10]: REF_NBLD_XLMS_BUFFER  
[^11]: REF_HU_2019_LYASE_PURIFICATION  
[^12]: REF_PBS_CROSSLINKING_BUFFER  
[^13]: REF_BS3_CROSSLINKING_CONDITION  
[^14]: REF_CROSSLINK_SAMPLE_PREP  
[^15]: REF_NBLA_PBS_RATIO