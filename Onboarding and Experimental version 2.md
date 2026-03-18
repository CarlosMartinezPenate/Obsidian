# Onboarding and Experimental Plan for **NblB** in _Acaryochloris marina_ MBIC 11017 (March 16 2026)

## Introduction and Current Context

The phycobilisome (PBS) is a large light‑harvesting antenna that can constitute up to half of the soluble protein mass in cyanobacteria. Under nitrogen or light stress the PBS is rapidly dismantled. The non‑bleaching protein **NblA** interacts with phycobiliprotein subunits and recruits the Clp protease to initiate degradation, while **NblB** detaches the bilin chromophores so that the protein core can be further degraded. Your group has already purified **NblA**, performed PBS assays and isothermal titration calorimetry (ITC), and found that the bilin‑lyase‑like protein **NblB** is predicted to crystallize easily. The following plan outlines how to quickly integrate into the laboratory, prepare **NblB** plasmids for expression and isolation, and plan subsequent cross‑linking mass‑spectrometry (XL‑MS) and crystallization work.

### Literature insights on buffer conditions and purification hurdles

Recent literature provides detailed guidance for handling Nbl‑family proteins and intact phycobilisomes. In addition to earlier studies, we considered three papers supplied by Maayan (Karradt et al., 2008; Hu et al., 2019; and Nadel et al., 2025) to refine buffer choices and purification strategies. The key findings are summarized below.

|Study & system|Relevant buffer conditions / hurdles|Notes|
|---|---|---|
|**NblA pull‑down & cross‑linking (Synechococcus 2973)**|Lysis buffer A contained 50 mM Tris (pH 8), 20 mM imidazole, 500 mM NaCl, 10 % glycerol and 1 % Tween‑20; inclusion bodies required **2 M urea** for solubilization. Wash buffer B contained 0.5 % Triton X‑100 and 2 M urea, followed by wash buffer C (no detergent) and gradual removal of urea during refolding on Ni–NTA resin. Elution buffer contained 50 mM Tris (pH 8), 100–500 mM imidazole, 500 mM NaCl and 10 % glycerol.|NblA formed inclusion bodies and required urea to remain soluble. Removing urea gradually on‑column allowed refolding; high salt and glycerol stabilized the protein. These conditions are likely applicable to **NblB** if aggregation is observed.|
|**NblA–ClpC interaction (Karradt et al., 2008)**|Cells expressing GST‑tagged NblA were lysed in **20 mM sodium/potassium phosphate buffer (pH 7.6)** containing **200 mM KCl, 20 mM NaCl, 2–20 mM MgCl₂ and 10 % glycerol**. During pull‑down assays, ClpC carrying an N‑terminal GST tag was bound to Glutathione‑Sepharose in the same buffer supplemented with **5 mM ATP** and washed; bound proteins were eluted using **40 mM reduced glutathione in 50 mM Tris/HCl (pH 8.0)**.|High salt and Mg²⁺ with 5 mM ATP stabilized interactions between NblA and the chaperone ClpC. The elution with glutathione indicates that GST‑tagged proteins can be recovered without imidazole. This suggests that NblB binding partners might require ATP or nucleotide analogues and magnesium for stable interactions.|
|**Role of NblA/B in bilin transfer (Hu et al., 2019)**|His₆‑tagged lyases and biliproteins were extracted in **20 mM potassium phosphate buffer (KPB, pH 7.2) containing 0.5 M NaCl** and purified by Ni²⁺ affinity chromatography; elution used the same buffer with **0.5 M imidazole**, and proteins were dialysed into appropriate KPB. GST‑tagged proteins were extracted in **buffer A (10 mM Na₂HPO₄, 1.8 mM KH₂PO₄, 140 mM NaCl, 2.7 mM KCl, pH 8.0)** and eluted with **50 mM Tris‑HCl (pH 8.0) containing 10 mM reduced glutathione**. Phycobilisomes and cores were isolated on sucrose step gradients prepared in **0.8 M KPB (pH 7.0)**; APC and CPC were separated by DEAE chromatography using a gradient between **20 mM KPB pH 7.1** and **20 mM KPB plus 1 M NaCl**.|The study shows that high concentrations of KPB (0.8 M) maintain PBS integrity during isolation, whereas **20 mM KPB with high NaCl** supports lyase solubility. GST‑tag and His‑tag purifications require different buffer systems (phosphate vs. phosphate‑free) and dialysis into reaction buffers. These conditions are directly relevant to expressing and purifying **NblB** and its interaction partners.|
|**Viral NblA and PBS extraction (Nadel et al., 2025)**|For isolating phycobilisomes from cyanophage‑infected _Synechococcus_ cells, pellets were resuspended in **7.5 M potassium phosphate buffer (pH 7.5)**, homogenized and disrupted; supernatant was loaded onto a **0.25–1.25 M sucrose gradient in 7.5 M potassium phosphate**, and ultracentrifuged for 18 h.|The unusually high phosphate concentration (7.5 M) stabilized phycobilisomes from marine _Synechococcus_ under viral infection. While such concentrations may not be necessary for _Acaryochloris_, the study underscores that very high ionic strength can preserve fragile PBS complexes during extraction and might be considered if standard 0.8–0.9 M phosphate buffers fail.|
|**NblD pull‑down and XL‑MS (Synechocystis 6803)**|FLAG‑tagged proteins were washed with **FLAG buffer** containing 50 mM Hepes‑NaOH (pH 7), 5 mM MgCl₂, 25 mM CaCl₂, 150 mM NaCl, 10 % glycerol and 0.1 % Tween‑20. Membrane proteins were solubilized with 2 % n‑dodecyl β‑D‑maltoside. Elution was performed with 0.2 % RapiGest in 0.1 M Hepes (pH 8) at 95 °C.|The presence of divalent cations and mild detergent aided solubility and binding of small proteins. If NblB associates with membranes or pigments, mild detergents (e.g., DDM) and glycerol may improve solubility.|

These insights suggest that **high salt/glycerol**, **chaotropic agents (urea)** to solubilize inclusion bodies, and **stabilizing potassium‑phosphate buffers** for PBS interactions are critical. High‑phosphate buffers ranging from 0.8 M to 7.5 M maintain intact phycobilisomes. Ni²⁺ affinity purification of lyase proteins benefits from 0.5 M NaCl and imidazole, whereas GST purification uses phosphate‑free buffers with glutathione. ATP and Mg²⁺ may be required for NblA/B interactions with chaperones.

## Week 1 Onboarding Plan (Day‑by‑Day)

### **Day 1 – Lab orientation and safety**

- **Orientation with Maayan:** Meet with Maayan to discuss project goals, current status (e.g., purified NblA, existing PBS assays), and review available constructs for NblB (His‑tagged or untagged). Obtain copies of lab protocols and safety manuals.
    
- **Safety training:** Complete required biosafety and chemical safety training. Familiarize yourself with the location and operation of fume hoods, centrifuges, sonicator, chromatography instruments and cryo‑facilities.
    
- **Review literature:** Read the three key studies (NblA pull‑down, PBS cross‑linking, and NblD pull‑down) to understand buffer conditions, cross‑linkers, and pitfalls. Note that NblA required urea to remain soluble and PBS cross‑linking demanded high phosphate buffer.
    
    - **Additional literature review:** In addition to the earlier NblA pull‑down, PBS cross‑linking and NblD pull‑down studies, read the newly supplied papers—**Karradt et al. (2008)** on NblA–ClpC interactions, **Hu et al. (2019)** on NblA/B roles in bilin transfer, and **Nadel et al. (2025)** on viral NblA. These papers describe specific buffer systems: sodium/potassium phosphate buffer with high KCl, NaCl, Mg²⁺ and ATP for NblA–ClpC interactions; potassium‑phosphate buffer with 0.5 M NaCl and 0.5 M imidazole for His‑tagged lyases; and a phosphate‑free buffer A with glutathione elution for GST‑tagged proteins. Phycobilisomes were preserved in 0.8 M to 7.5 M potassium‑phosphate buffer. Keep these conditions in mind when preparing buffers for NblB work.
        

### **Day 2 – Plasmid identification and planning**

- **Discuss plasmids:** Confirm with Maayan which plasmids carry _Acaryochloris_ **nblB** (wild‑type vs. mutants). Determine if they are in pET, pBAD or other expression vectors and whether the His‑tag is at the N‑ or C‑terminus.
    
- **Sequence verification:** Use SnapGene or Benchling to review the plasmid maps and confirm the nblB coding sequence, tag location and any mutations. Check for presence of TEV cleavage sites and antibiotic resistance markers. Align the sequence to MBIC 11017 genome to ensure no frameshifts or codon discrepancies.
    
- **Stock check:** Inventory reagents (antibiotics, IPTG, Ni–NTA resin, chromatography columns). Ensure availability of urea, Triton X‑100, DDM, BS3 cross‑linker and phosphate buffers for upcoming work.
    

### **Day 3 – Competent cell transformation**

- **Prepare competent cells:** Use E. coli BL21 (DE3) or appropriate expression strain. Chill CaCl₂‑treated cells or acquire electrocompetent cells.
    
- **Transform plasmids:** Transform the nblB plasmid(s) and plate onto antibiotic‑containing agar. Include positive control (e.g., GFP expression plasmid) and negative control. Incubate overnight at 37 °C.
    
- **Plan backup strategies:** If transformation efficiency is low, plan to use alternative host strains or co‑express chaperones (e.g., GroEL/ES) to assist folding.
    

### **Day 4 – Colony screening and starter cultures**

- **Screen colonies:** Perform colony PCR or restriction digest to confirm presence of nblB insert. Sequence positive clones if necessary.
    
- **Start cultures:** Inoculate verified colonies into 5 mL LB medium with antibiotics. Grow overnight at 37 °C with shaking.
    
- **Prepare buffers:** Prepare lysis buffer (50 mM Tris pH 8, 500 mM NaCl, 10 % glycerol, 20 mM imidazole) and inclusion body solubilization buffer (add 2 M urea) based on NblA purification conditions.
    

### **Day 5 – Glycerol stocks and pre‑culture preparation**

- **Glycerol stocks:** Mix overnight cultures with sterile glycerol (final 15–20 %) and freeze at –80 °C as long‑term stocks.
    
- **Pre‑cultures:** Inoculate 50 mL LB + antibiotic from overnight culture for expression the following week. For possible cross‑linking experiments, prepare 0.9 M phosphate buffer (pH 7.5–8) for PBS extraction and cross‑linking.
    
- **Coordinate with Maayan:** Schedule instrument time for next week (sonicator, ÄKTA FPLC, SEC column). Discuss any potential issues or modifications to protocols.
    

### **Day 6 – PBS preparation practice (optional)**

- **Practice PBS extraction:** Under Maayan’s supervision, learn how to isolate intact PBS from _A. marina_ or other cyanobacteria using high‑phosphate buffer (0.9 M, pH 7.5–8), sucrose gradients (0.5–1.3 M) and ultracentrifugation.
    
- **Record yield and stability:** Monitor absorbance spectra (620–650 nm) to confirm intact PBS and note how quickly complexes dissociate in low ionic strength. This practice will support later NblB–PBS interaction assays.
    

### **Day 7 – Plan review and adjustments**

- **Meeting with Dvir and Maayan:** Present progress from week 1, including transformation results, plasmid maps and buffer preparations. Discuss upcoming expression strategy, induction conditions (e.g., IPTG vs. auto‑induction), and purification workflow.
    
- **Adjust plan:** Incorporate feedback on host strains, induction temperatures (e.g., 16 °C vs. 25 °C), and potential co‑expression of chaperones or NblA for interaction studies.
    

## Strategic Outlook for Weeks 2–3

### **Week 2 – Expression and purification of NblB**

1. **Large‑scale expression**
    
    - Inoculate 500 mL (×2) LB or minimal medium containing antibiotic from pre‑cultures. Grow at 37 °C until OD₆₀₀ ≈ 0.6. Cool cultures and induce with IPTG (0.2–0.5 mM). Based on NblA experience, induction at **18 °C** overnight may improve solubility. Sample pre‑ and post‑induction to monitor expression via SDS‑PAGE.
        
    - For comparison, test auto‑induction medium or addition of ethanol to potentially increase soluble yield.
        
2. **Cell lysis and inclusion body management**
    
    - Harvest cells by centrifugation and resuspend pellets in **lysis buffer** (50 mM Tris pH 8, 500 mM NaCl, 10 % glycerol, 20 mM imidazole, protease inhibitors). If cells appear to form inclusion bodies (as observed for NblA), include **2 M urea** and 0.5 % Triton X‑100 to solubilize.
        
    - Lyse cells using sonication or French Press. Centrifuge at 20,000 × g, 4 °C to remove debris. If most protein remains insoluble, subject the pellet to urea washes (similar to NblA purification). Gradually remove urea during Ni–NTA column binding/refolding by mixing wash buffer with and without urea in a gradient.
        
3. **Affinity purification (Ni–NTA or TALON)**
    
    - Bind soluble or urea‑solubilized NblB to Ni–NTA resin. Wash with increasing concentrations of imidazole (20–50 mM) while decreasing urea (if used). Maintain high salt and 10 % glycerol for stability.
        
    - Elute NblB using 200–300 mM imidazole. Collect fractions and monitor by SDS‑PAGE.
        
    - If NblB is untagged or tag removal is required, perform TEV protease digestion and a secondary Ni–NTA step to remove tags.
        
4. **Size‑exclusion chromatography (SEC)**
    
    - Exchange eluted protein into **SEC buffer** (e.g., 20 mM Tris pH 8, 150 mM NaCl, 5–10 % glycerol). Use a Superdex 75 or 200 Increase column depending on NblB size (~7–9 kDa as monomer). Monitor absorption at 280 nm and collect monodisperse fractions.
        
    - Record the **SEC profile**—a monomeric species should elute near the column void corresponding to ~10 kDa; oligomeric peaks may indicate dimerization or aggregation. Save fractions for downstream assays.
        
5. **Quality control**
    
    - Perform SDS‑PAGE and Western blot (anti‑His or anti‑FLAG) to verify purity. Determine concentration via absorbance at 280 nm or BCA assay.
        
    - Optional: perform circular dichroism (CD) or differential scanning fluorimetry (DSF) to assess folding and thermal stability. If protein remains unstable, test alternative buffers (e.g., Hepes pH 7.5 with Mg²⁺/Ca²⁺ and 0.1 % Tween‑20). Include reducing agent (1 mM DTT) if cysteines are present.
        

### **Week 3 – Functional assays, XL‑MS and crystallization trials**

1. **Phycobilisome binding and cross‑linking assays**
    
    - **PBS preparation:** Isolate PBS from _A. marina_ cultures grown under far‑red and white light using 0.9 M phosphate buffer (pH 7.5–8) and sucrose gradients. Validate integrity via absorbance spectra.
        
    - **In vitro binding:** Incubate purified NblB with PBS (varying molar ratios) in high‑phosphate buffer. Include NblA (from Maayan’s stock) as control. After incubation, perform pull‑down assays using Ni–NTA resin or cross‑linker to capture interacting complexes.
        
    - **Chemical cross‑linking:** Use BS3 (water‑soluble, amine‑reactive) at 0.5–1 mM; incubate on ice for ~3 h, then quench with 50 mM Tris. Optionally, test glutaraldehyde (5 mM, 5 min) for more extensive cross‑linking.
        
    - **Sample preparation for MS:** Precipitate cross‑linked complexes (acetone precipitation), digest with LysC/Trypsin following established protocols (e.g., 8 M urea reduction/alkylation then protease digestion). Use high‑resolution LC‑MS/MS to identify cross‑linked peptides. Collaborate with proteomics facility for data acquisition and use software like MassMatrix or pLink for analysis.
        
2. **Interaction studies with NblA**
    
    - Perform **isothermal titration calorimetry (ITC)** or **microscale thermophoresis (MST)** to measure the binding affinity between NblB and NblA or PBS components. Compare results with Maayan’s NblA data to understand if NblB enhances or competes for binding.
        
    - Assess whether NblB promotes bilin detachment by monitoring absorbance/fluorescence of bilins after incubation with NblB.
        
3. **Crystallization trials**
    
    - Concentrate NblB to >10 mg/mL in SEC buffer or alternative buffer (e.g., Hepes pH 7.5, 100 mM NaCl). Filter through 0.22 µm filters.
        
    - Set up **sitting‑drop vapor diffusion** screens using commercial kits (e.g., JCSG+, Crystal Screen, and PACT). Prepare 96‑well plates and test a range of pH (4–9), precipitants (PEG 3350, salts), and additives. Because NblB is predicted to crystallize easily, crystals may appear within days. Use micro‑seeding to improve crystal quality.
        
    - If NblB forms dimers or complexes with bilins or peptides, consider co‑crystallization with truncated phycocyanin fragments or peptides representing the bilin‑binding site. This may mimic native interactions and facilitate crystallization.
        
4. **Data analysis and planning for structural methods**
    
    - Should crystals be obtained, coordinate with X‑ray facility for diffraction experiments. Determine space group and unit cell parameters and plan for structure solution via molecular replacement (using homologous biliprotein lyases as templates).
        
    - If crystallization fails, consider **nuclear magnetic resonance (NMR)** or **AlphaFold‑assisted modeling** integrated with XL‑MS constraints to generate structural models of NblB. The cross‑linking data will guide modelling of interaction surfaces.
        

## Questions to Discuss with **Maayan**

1. **Plasmid details:**
    
    - What is the **location of the His‑tag** on NblB (N‑terminus vs. C‑terminus)? Is there a TEV or other protease site for tag removal?
        
    - Which **expression vector** is used (pET‑series, pCDF, pBAD, etc.), and what antibiotic resistance does it confer? Are there codon optimizations or mutations in the NblB gene?
        
2. **Expression strategy:**
    
    - Which **E. coli strain** has been used previously for NblB? Did it require chaperone co‑expression or lower induction temperatures to obtain soluble protein?
        
    - What **induction conditions** were successful for NblA (IPTG concentration, temperature, duration)? Should we consider auto‑induction medium or additives (ethanol, glycine)?
        
3. **Chromatography details:**
    
    - What type of **affinity resin** (Ni–NTA, Co‑IMAC) and column volumes have been used? What is the typical **SEC column** (Superdex 75 vs. 200, or a Sepax SRT) and running buffer? Are there differences in profiles between wild‑type and mutant NblB?
        
    - Have any **SEC profiles** shown oligomerization or aggregation for NblA; if so, how were they addressed (e.g., by adding salt, glycerol, or detergent)?
        
4. **Interacting partners and assays:**
    
    - What are the **known interaction partners** of NblB in _A. marina_ MBIC 11017? Does NblB interact directly with NblA or only with phycocyanin subunits? Are there known peptides or fragments that enhance binding or solubility?
        
    - For the **PBS assays**, what ratio of NblA:PBS was used (7:1 in NblA study)? Should similar ratios be tested for NblB?
        
5. **Cross‑linking reagents and conditions:**
    
    - Which **cross‑linker** does Maayan recommend (BS3, DSS, glutaraldehyde)? Should we use isotopically labelled cross‑linkers for MS identification?
        
    - Are there preferences for **buffer composition** during cross‑linking (e.g., high phosphate vs. HEPES) to preserve PBS integrity and avoid non‑specific cross‑links?
        
6. **Crystallization experience:**
    
    - Has Maayan previously attempted to crystallize NblB or similar lyase‑like proteins? If so, which conditions yielded preliminary crystals?
        
    - Does she recommend **co‑crystallization** with bilin analogs or peptides? Are there known inhibitors or ligands that stabilize NblB in a defined conformation?
        
7. **Downstream analyses:**
    
    - How does Maayan plan to integrate **XL‑MS** data with **computational modelling** (e.g., AlphaFold or docking)? What software pipelines are available in the lab?
        
    - Should we explore **small‑angle X‑ray scattering (SAXS)** or **cryo‑EM** if crystals are weak? Are there collaborations for these methods?
        

## Summary and Next Steps

By following this step‑by‑step plan, you will quickly integrate into the laboratory, validate the **nblB** plasmids and prepare for expression. The buffer conditions reported for **NblA** and **PBS** reveal that high salt, glycerol and careful management of urea/detergent are critical for soluble expression and refolding. During Weeks 2–3 you will express and purify NblB, assess its oligomeric state and stability by SEC, and begin functional assays and XL‑MS. Concurrently, you will initiate crystallization screens, taking advantage of the predicted ease of crystallization. The “Questions for Maayan” section should help clarify any remaining uncertainties and ensure alignment with existing protocols and equipment.

---
# Onboarding and Experimental Plan for NblB in *Acaryochloris marina* MBIC 11017

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

## Day 2 — Plasmid audit and sequence-level verification

### Main goals
- Confirm exactly what construct I am working with
- Eliminate ambiguity before doing wet work

### Tasks
- Review each NblB plasmid in SnapGene / Benchling
- Record for each construct:
  - vector backbone
  - promoter
  - antibiotic marker
  - tag identity
  - tag position
  - linker sequence
  - cleavage site
  - mutation status
  - expected MW
- Verify:
  - reading frame
  - stop codon placement
  - tag orientation
  - any extra residues after cloning
  - codon usage concerns
- Compare construct sequence to the expected *A. marina* MBIC 11017 NblB sequence
- Generate a small construct table in Obsidian

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

---
# NblB Project — Grounded Experimental Plan (Reality-Based)
## Research Objectives and Experimental Rationale

The primary objective of this experimental phase is to establish a structural and functional anchor for **NblB** within the established **NblA-Phycobilisome (PBS)** degradation framework. While NblA has been successfully expressed, crystallized, and validated via Isothermal Titration Calorimetry (ITC), NblB remains experimentally uncharacterized. This plan transitions from theoretical modeling to empirical validation by prioritizing sample quality and systematic interaction mapping.

### 1. Robust Expression and Solubilization

The initial phase focuses on achieving soluble expression of NblB using a system compatible with existing NblA protocols. By utilizing identical host strains and tagging strategies, we ensure downstream biochemical compatibility for complex reconstitution. The rationale is to avoid exhaustive screening in favor of targeted conditions (e.g., $18^{\circ}\text{C}$ overnight induction), moving to purification only once a stable, soluble protein fraction is confirmed.

### 2. Definitive Characterization of Protein Quality

A "pure" sample is insufficient for structural biology; the objective here is **monodispersity**. Using Size Exclusion Chromatography (SEC) as a mandatory diagnostic tool, the project evaluates the oligomeric state and folding integrity of NblB. This stage acts as a critical "Go/No-Go" decision node: only monodisperse, stable NblB will proceed to interaction testing, preventing the accumulation of false negatives in downstream assays.

### 3. Hierarchical Interaction Mapping

The core scientific aim is to identify the minimal biochemically relevant complex involving NblB. Following the hierarchy established in the project proposal, interactions will be tested in order of increasing complexity:

1. **NblB + Phycobiliprotein (PBP):** Testing the primary hypothesis of NblB–PBP assembly.
    
2. **NblB + NblA:** Exploring potential co-chaperone or synergistic binding.
    
3. **NblB + Intact PBS:** Validating recruitment to the macro-molecular antenna.
    

### 4. Integrative Structural Determination

By employing a combination of **SEC shift assays** and **Thermal Shift Assays (TSA)**, we aim to identify stabilizing ligands or protein partners that facilitate crystallization. The ultimate goal is to transition from Path A (NblB alone) to Path B (NblB-PBP complexes) or Path C (Cross-linking Mass Spectrometry integrated with AlphaFold models) depending on the biochemical behavior of the protein. This strategic flexibility ensures that the project delivers structural insights—whether through traditional X-ray crystallography or hybrid modeling—regardless of the protein's inherent stability.


## Project position

System status:
- PBS: established
- NblA: expressed, crystallized, ITC validated
- Cryo-EM pipeline: functional
- AlphaFold models: available

Gap:
👉 NblB is not experimentally anchored

---

## Phase 0 — Clarify what already exists (CRITICAL)

Before touching wet lab:

### Ask Maayan:
- Has NblB already been:
  - cloned?
  - expressed?
  - purified?
- Any gels?
- Any SEC traces?
- Any failed attempts?

### Decision node:

IF NblB already expressed:
    → reproduce system (NOT redesign)
ELSE:

    → start expression pipeline

---

## Phase 1 — Expression (NOT generic screening)

Goal:
👉 Get **soluble NblB in SAME system as NblA**

### Why:
- You want compatibility with:
  - NblA
  - PBS assays
  - downstream ITC / XL-MS

---

### Expression design (focused)

Do NOT over-screen.

Start with:
- same strain as NblA
- same tag strategy (unless reason not to)

Test ONLY:
- 18°C overnight
- 0.1–0.5 mM IPTG

---

### Decision logic

CASE 1 — soluble band:
    → proceed immediately to purification

CASE 2 — insoluble:
    → lower temp OR change tag
    → DO NOT jump to refolding yet

CASE 3 — no expression:
    → check construct before changing biology

---

## Phase 2 — Purification (THIS is where your thinking matters)

Goal:
👉 Not “pure protein”
👉 **usable, structurally relevant NblB**

---

### Minimal pipeline

1. IMAC
2. SEC (MANDATORY)

---

### What you actually evaluate (NOT generic)

At SEC:

- single peak? → good
- multiple peaks? → oligomer or junk
- early peak? → aggregation
- very late? → maybe unfolded/small fragment

---

### Decision node

IF monodisperse:
    → proceed to interaction testing

IF not:
    → DO NOT continue downstream
    → fix buffer / tag / construct

---

## Phase 3 — FIRST REAL QUESTION (this is where most people fail)

### DO NOT ask:
"Is NblB pure?"

### ASK:
👉 "Does NblB bind ANYTHING relevant?"

---

## Phase 4 — Interaction testing (VERY SPECIFIC)

### Priority order (based on proposal)

1. NblB + PBP (phycocyanin β subunit ideally)
2. NblB + NblA
3. NblB + PBS (only after above)

---

### FIRST experiment (simple and powerful)

SEC shift assay:

- run NblB alone
- run partner alone
- mix → run SEC

LOOK FOR:
- peak shift
- co-elution

---

### Why this matters

Because:

> Proposal explicitly targets NblB–PBP complexes for structure :contentReference[oaicite:2]{index=2}

If this fails → rethink biology early

---

## Phase 5 — Thermal shift (your question)

### WHEN to use it

NOT as default.

Use it ONLY to answer:

👉 "Does something stabilize NblB?"

---

### Use cases

1. Buffer optimization
2. Partner binding
3. Ligand effect (if any)

---

### Example

Test:

- NblB alone
- NblB + NblA
- NblB + PBP

IF ΔTm increases:
→ evidence of interaction

IF nothing changes:
→ weak or no binding

---

### Important

Thermal shift is:
- indirect
- fast
- NOT proof of binding

Use it as:
👉 **screening tool, not final answer**

---

## Phase 6 — XL-MS (DO NOT RUSH)

### Only if:

- SEC shift observed OR
- thermal stabilization OR
- strong hypothesis from AlphaFold

---

### First XL-MS target

👉 NblB + PBP

NOT whole PBS

---

### Why

Because:

> Proposal explicitly mentions PBP–NblB assemblies :contentReference[oaicite:3]{index=3}

---

## Phase 7 — Structural strategy (realistic)

### Path A — Ideal

NblB alone:
- stable
- monodisperse

→ crystallization

---

### Path B — More realistic

NblB only stable with partner

→ crystallize:
- NblB + PBP fragment
- NblB + peptide

---

### Path C — If everything fails

→ pivot early to:
- XL-MS + AlphaFold integration
- NOT blind crystallization

---

## Key strategic rule

👉 DO NOT move forward with bad sample

Bad sample = dead project

---

## Weekly reality check

Every week ask:

- Do I have better NblB than last week?
- Do I know more about what it binds?
- Am I closer to a structural question?

IF not:
→ stop and rethink