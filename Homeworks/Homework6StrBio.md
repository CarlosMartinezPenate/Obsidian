# Exercise 6 – Protein Structure Prediction and Structural Comparison

## Protein used

For this exercise, I used **human carbonic anhydrase II**.

| Item                            | Entry                 |
| ------------------------------- | --------------------- |
| Protein                         | Carbonic anhydrase II |
| UniProt entry                   | P00918                |
| Experimental PDB entry          | 2CBA                  |
| Experimental method             | X-ray crystallography |
| Experimental structure coverage | residues 2–260        |
| SWISS-MODEL selected            | P00918_1-260:6qeb.1.A |
| SWISS-MODEL coverage            | residues 1–260        |
| AlphaFoldDB entry               | P00918                |
| AlphaFold coverage              | residues 1–260        |

The experimental structure **2CBA** represents almost the complete protein sequence, but not the entire sequence exactly, because the UniProt structure table reports coverage of residues **2–260**. Therefore, residue 1 is not represented in the experimental structure.

---

# Part One – Experimental vs predicted structure

## 1. Experimental and predicted structure coverage

The experimental structure **2CBA** is an X-ray structure of human carbonic anhydrase II. It covers residues **2–260**, so it represents nearly the entire protein, but the first residue is missing from the modeled experimental structure.

The AlphaFoldDB model used was:

```text
/Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/AF-P00918-F1-model_v6.cif
```

The SWISS-MODEL structure used was:

```text
/Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/P00918_1_260_6qeb.1.A.cif
```

Both the AlphaFold and SWISS-MODEL structures cover the full **1–260** sequence. Therefore, the predicted/model structures cover slightly more sequence than the experimental 2CBA structure.

---

## 2. AlphaFold predicted structure and confidence

I opened the AlphaFold model in ChimeraX and colored it by AlphaFold confidence using the B-factor field:

```chimerax
open /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/AF-P00918-F1-model_v6.cif
hide atoms
show cartoons
color bfactor palette alphafold
key #ff7d45:"<50" #ffdb13:"50–70" #65cbf3:"70–90" #0053d6:">90" pos 0.10,0.05 size 0.35,0.04
view
save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/P00918_alphafold_confidence.png width 1600 height 1200
```

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/P00918_alphafold_confidence_key.png)
The AlphaFold model of carbonic anhydrase II was colored by prediction confidence using `color bfactor palette alphafold`. Most of the protein is colored dark blue, indicating very high confidence across the main folded structure. This suggests that AlphaFold predicts the carbonic anhydrase II fold with high reliability.

Only a short region appears in yellow/orange, indicating lower confidence. This region is located outside the main compact core and looks like a flexible exposed segment rather than a stable secondary-structure element. I did not observe large unstructured regions across the protein. Overall, the model supports the interpretation that carbonic anhydrase II is a compact, well-folded enzyme with high-confidence prediction over most of its sequence.

---

## 3. MatchMaker comparison: AlphaFold vs experimental 2CBA

To compare the AlphaFold predicted structure with the experimental structure, I opened both structures in ChimeraX and used MatchMaker:

```chimerax
close
open 2cba
open /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/AF-P00918-F1-model_v6.cif

matchmaker #2 to #1

hide atoms
show cartoons
color #1 gray
color #2 blue
view
save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/2CBA_vs_AlphaFold_matchmaker.png width 1600 height 1200
```

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/2CBA_vs_AlphaFold_matchmaker.png)

MatchMaker result:

```text
AlphaFold vs 2CBA RMSD: 0.342 Å after pruning
RMSD across all aligned pairs: 0.533 Å
Number of aligned atom pairs: 258
Number of pruned atom pairs used for final RMSD: 257
Sequence alignment score: 1332.8
```

The AlphaFold model aligned very closely with the experimental 2CBA structure. The final pruned RMSD was **0.342 Å**, and the RMSD across all aligned pairs was **0.533 Å**, which indicates very strong global structural similarity.

In the alignment image, the main fold of carbonic anhydrase II overlaps very well between the two structures. The central beta-sheet region and most of the surrounding helices and loops follow almost the same path in both models. This suggests that AlphaFold reproduced the overall carbonic anhydrase II fold accurately.

The main visible differences are small and local. Therefore, the AlphaFold model agrees very well with the experimental structure of carbonic anhydrase II.

---

## 4. MatchMaker comparison: SWISS-MODEL vs experimental 2CBA

To compare the SWISS-MODEL structure with the experimental structure, I opened both structures in ChimeraX and used MatchMaker:

```chimerax
close
open 2cba
open /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/P00918_1_260_6qeb.1.A.cif

matchmaker #2 to #1

hide atoms
show cartoons
color #1 gray
color #2 orange
view
save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/2CBA_vs_SWISSMODEL_matchmaker.png width 1600 height 1200
```

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/2CBA_vs_SWISSMODEL_matchmaker.png)

MatchMaker result:

```text
SWISS-MODEL vs 2CBA RMSD: 1.340 Å after pruning
RMSD across all aligned pairs: 11.578 Å
Number of pruned atom pairs used for final RMSD: 83
Number of total aligned atom pairs: 258
Sequence alignment score: 1241.6
```

The SWISS-MODEL structure showed weaker agreement with the experimental 2CBA structure than the AlphaFold model. After pruning, MatchMaker reported an RMSD of **1.340 Å** using **83 atom pairs**, which suggests that part of the structure aligns reasonably well. However, the RMSD across all **258 atom pairs** was much higher, **11.578 Å**, indicating large global differences when the full aligned structure is considered.

In the alignment image, some parts of the compact fold overlap, but the SWISS-MODEL structure also contains regions that deviate strongly from 2CBA. This explains why the pruned RMSD is moderate while the all-pairs RMSD is very high.

---

## 5. Does RMSD alone provide enough information?

The RMSD value is useful, but it is not enough by itself. This was clear in the SWISS-MODEL comparison. The pruned RMSD was **1.340 Å**, which might suggest a reasonable alignment, but the RMSD across all aligned atom pairs was **11.578 Å**. The image showed that some regions deviate strongly from the experimental structure. Therefore, RMSD must be interpreted together with the number of atom pairs used, whether pruning was applied, and the visual alignment.

---

# Part Two – Protein conformations and energy

In this part, I calculated the Boltzmann factor for different protein conformations using the formula:

```text
BF = e^(-E/RT)
```

where:

```text
RT = 2.5 kJ/mol
```

The calculated values were:

| Conformation | Energy | Boltzmann factor |
|---|---:|---:|
| A | -20 | 2980.958 |
| B | -18 | 1339.431 |
| C | -16 | 601.845 |
| D | -15 | 403.429 |
| E | -10 | 54.598 |
| F | -5 | 7.389 |
| G | 0 | 1.000 |
| H | 2 | 0.449 |
| I | 4 | 0.202 |
| J | 6 | 0.091 |

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise6/Boltzman.png)

The Boltzmann factor decreased exponentially as energy increased. The most dramatic **absolute** change occurred between conformations **A and B**, where the Boltzmann factor decreased from **2980.958** to **1339.431**. This is a decrease of about **1641.527**.

Large changes were also observed between **B and C** and between **D and E**. Between **D and E**, the energy increased by **5 kJ/mol**, and the Boltzmann factor dropped from **403.429** to **54.598**. This shows a strong decrease in relative probability.

Overall, the largest changes occur among the lower-energy conformations, where the Boltzmann factors are high. As energy increases, the Boltzmann factor becomes very small, so later changes become smaller in absolute size. This result shows that small energy differences can strongly affect the probability of observing a protein conformation. Because the Boltzmann factor depends exponentially on energy, even a small increase in energy can greatly reduce the relative probability of a conformation. Therefore, lower-energy conformations are much more likely to be observed than higher-energy conformations.