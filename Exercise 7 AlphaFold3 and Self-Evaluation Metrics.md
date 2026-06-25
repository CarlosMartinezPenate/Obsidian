# Exercise 7 – AlphaFold3 and Self-Evaluation Metrics

## Protein used

For this exercise, I used **PDB 1CSE**, a protein–protein complex between **Subtilisin Carlsberg** and **Eglin C**.

| Item | Entry |
|---|---|
| PDB entry | 1CSE |
| Complex type | Protein–protein |
| Protein 1 | Subtilisin Carlsberg |
| Protein 2 | Eglin C |
| Experimental chain for Subtilisin Carlsberg | chain E |
| Experimental chain for Eglin C | chain I |
| AF3 chain for Subtilisin Carlsberg | chain A |
| AF3 chain for Eglin C | chain B |

---

# Part One – AlphaFold3 prediction

## 1. Chains submitted to AlphaFold3

The sequences were downloaded from the PDB entry **1CSE** in FASTA format. I submitted two protein entities to AlphaFold3.

| Entity | Molecule | PDB chain | Author chain ID | Length |
|---|---|---:|---:|---:|
| 1 | Subtilisin Carlsberg | A | E | 274 aa |
| 2 | Eglin C | B | I | 70 aa |

The total submitted sequence length was:

```text
274 + 70 = 344 aa
```

Both entities were submitted as **protein** chains. I did not include duplicated copies because the goal was to predict a heteromeric complex.

The sequences submitted were:

```text
>1CSE_1|Chain A[auth E]|SUBTILISIN CARLSBERG|Bacillus subtilis
AQTVPYGIPLIKADKVQAQGFKGANVKVAVLDTGIQASHPDLNVVGGASFVAGEAYNTDGNGHGTHVAGTVAALDNTTGVLGVAPSVSLYAVKVLNSSGSGSYSGIVSGIEWATTNGMDVINMSLGGASGSTAMKQAVDNAYARGVVVVAAAGNSGNSGSTNTIGYPAKYDSVIAVGAVDSNSNRASFSSVGAELEVMAPGAGVYSTYPTNTYATLNGTSMASPHVAGAAALILSKHPNLSASQVRNRLSSTATYLGSSFYYGKGLINVEAAAQ
```

```text
>1CSE_2|Chain B[auth I]|EGLIN C|Hirudo medicinalis
TEFGSELKSFPEVVGKTVDQAREYFTLHYPQYNVYFLPEGSPVTLDLRYNRVRVFYNPGTNVVNHVPHVG
```

---

## 2. AlphaFold3 self-evaluation metrics

AlphaFold3 reported:

```text
pTM = 0.95
ipTM = 0.94
```

The high **pTM** suggests strong confidence in the overall fold. The high **ipTM** suggests strong confidence in the interface and relative placement of the two chains.

I used model 0 from the AlphaFold3 output folder:

```text
/Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/fold_2026_06_24_15_06_hw7/fold_2026_06_24_15_06_hw7_model_0.cif
```

To color the model by pLDDT in ChimeraX, I used:

```chimerax
close
open /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/fold_2026_06_24_15_06_hw7/fold_2026_06_24_15_06_hw7_model_0.cif

hide atoms
show cartoons
color bfactor palette alphafold
key #ff7d45:"<50" #ffdb13:"50–70" #65cbf3:"70–90" #0053d6:">90" pos 0.10,0.05 size 0.35,0.04
view

save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/AF3_1CSE_plddt.png width 1600 height 1200
```

pLDDT-colored AF3 structure:

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/AF3_1CSE_plddt.png)

PAE map from AlphaFold3:

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/PAE_AP3.png)

Most of the predicted complex is dark blue, indicating high local confidence. I only observed a small lower-confidence region in yellow/orange. This region is local and does not dominate the structure.

I did not observe large unstructured regions. Both chains appear folded and packed together as a clear protein–protein complex.

---

## 3. Interpretation of the self-evaluation metrics

The pLDDT coloring shows high local confidence across most of the structure. The small yellow/orange region likely represents a flexible loop or exposed local segment.

The **pTM = 0.95** is high. This suggests that AF3 is confident in the global fold of the complex.

The **ipTM = 0.94** is also high. This suggests that AF3 is confident in the relative orientation of Subtilisin Carlsberg and Eglin C.

The PAE map shows expected positional error between residues. Dark green indicates low predicted error. Lighter green indicates higher predicted error.

The map is divided by chain borders. Subtilisin Carlsberg covers residues **1–274**. Eglin C covers residues **275–344**. The diagonal blocks show confidence within each chain. The off-diagonal blocks show confidence between the two chains.

Most of the PAE map is dark green, including the off-diagonal regions between the chains. This suggests that AF3 is confident in both the individual folds and the relative placement of the two chains.

There is a lighter horizontal and vertical band near the chain border, suggesting slightly higher uncertainty around local regions near the interface, however the self-evaluation metrics suggest that AF3 is confident in both the overall fold and the interface.

---

## 4. Effect of using PDB-derived sequences instead of full-length proteins

The sequences submitted to AlphaFold3 were taken directly from **1CSE**. PDB structures often contain crystallographic constructs rather than full-length natural proteins. These constructs may be truncated, engineered, or processed.

This can affect the metrics. A shorter construct may be easier to predict because flexible or disordered regions are missing. This can increase pLDDT and reduce PAE.

If I had submitted full-length sequences, extra terminal regions or flexible segments might have appeared. These regions could have lower pLDDT and higher PAE because their positions may be uncertain.

Therefore, using the PDB-derived sequences probably made the prediction cleaner and more confident than a full-length prediction might be.

---

# Part Two – Comparing predicted structure to the experimental PDB structure

## 1. Structural comparison in ChimeraX

I compared the AlphaFold3 model with the experimental PDB structure **1CSE** in ChimeraX.

The experimental structure was opened as model **#1**, and the AF3 prediction was opened as model **#2**.

The chains were:

| Structure | Chain | Molecule |
|---|---:|---|
| Experimental 1CSE | E | Subtilisin Carlsberg |
| Experimental 1CSE | I | Eglin C |
| AF3 model | A | Subtilisin Carlsberg |
| AF3 model | B | Eglin C |

I used:

```chimerax
close
open 1cse
open /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/fold_2026_06_24_15_06_hw7/fold_2026_06_24_15_06_hw7_model_0.cif

matchmaker #2/A,B to #1/E,I showAlignment true

hide atoms
show cartoons
color #1 gray
color #2 blue
view

save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/AF3_1CSE_vs_PDB_matchmaker.png width 1600 height 1200
```

Structural superposition:

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/AF3_1CSE_vs_PDB_matchmaker.png)

The MatchMaker output reported:

```text
AF3 chain A vs experimental chain E
Sequence alignment score: 1354
RMSD between 274 pruned atom pairs: 0.271 Å
RMSD across all 274 atom pairs: 0.271 Å
```

The AF3 model aligned very closely with the experimental structure. The RMSD for Subtilisin Carlsberg was **0.271 Å**, with all **274 atom pairs** included. This is a very low RMSD.

In the image, the gray experimental structure and the blue AF3 model overlap strongly. The helices, beta strands, and most loops follow the same positions. I did not observe major deviations in the main enzyme fold.

---

## 2. Regions with deviation

The RMSD was very low, so there were no major deviations in the main subtilisin fold. Any visible differences were small and local, mainly in loop regions.

This agrees with the pLDDT image. Most of the structure had high pLDDT, and only a small local region showed lower confidence. The possible deviations are therefore local, not in the stable folded core.

The high **pTM = 0.95** also agrees with this result.

---

## 3. Interface residue comparison

To compare the interface, I selected residues in Subtilisin Carlsberg within **4 Å** of Eglin C.

For the experimental structure, I selected chain **I** and identified nearby residues on chain **E**:

```chimerax
select clear
select #1/I
select zone sel 4 residues true
select sel & #1/E
label sel residues
show sel atoms
style sel stick
color sel yellow
view sel

save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/1CSE_PDB_interface_residues.png width 1600 height 1200
```

Experimental interface image:

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/1CSE_PDB_interface_residues.png)

For the AF3 model, I selected chain **B** and identified nearby residues on chain **A**:

```chimerax
select clear
select #2/B
select zone sel 4 residues true
select sel & #2/A
label sel residues
show sel atoms
style sel stick
color sel cyan
view sel

save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/AF3_1CSE_interface_residues.png width 1600 height 1200
```

AF3 interface image:

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/AF3_1CSE_interface_residues.png)

The experimental structure identified these Subtilisin Carlsberg interface residues on chain **E**:

```text
THR33, ASN62, HIS64, LEU96, SER99, GLY100, SER101, GLY102, TYR104, ILE107,
SER125, LEU126, GLY127, GLY128, ALA129, SER130, ALA152, GLY154, ASN155,
PHE189, TYR209, LEU217, ASN218, GLY219, THR220, SER221
```

The AF3 model identified these interface residues on chain **A**:

```text
THR33, ASN61, HIS63, LEU95, SER98, GLY99, SER100, GLY101, TYR103, ILE106,
SER124, LEU125, GLY126, GLY127, ALA151, GLY153, ASN154, ASN157, SER158,
SER187, PHE188, TYR208, ASN217, GLY218, THR219, SER220
```

Most AF3 interface residues correspond closely to the experimental interface residues. Many are shifted by one residue number, but they occur in the same local sequence and structural region.

Examples:

```text
Experimental: LEU96, SER99, GLY100, SER101, GLY102, TYR104, ILE107
AF3 model:    LEU95, SER98, GLY99, SER100, GLY101, TYR103, ILE106
```

Another matching region:

```text
Experimental: ASN218, GLY219, THR220, SER221
AF3 model:    ASN217, GLY218, THR219, SER220
```

This shows that AF3 correctly placed the main interface between Subtilisin Carlsberg and Eglin C. The key contact regions appear in the right positions.

Some exact residue differences are expected because the **4 Å** cutoff is sensitive to small coordinate changes. Overall, the interface prediction agrees well with the experimental structure.

---

## 4. Reliability of the self-evaluation metrics

The self-evaluation metrics were reliable in this case.

The high **pTM = 0.95** suggested confidence in the overall fold. This was supported by the structural comparison with the experimental structure. The subtilisin chain had an RMSD of **0.271 Å**, showing very strong agreement.

The high **ipTM = 0.94** suggested confidence in the interface. This was also supported by the interface analysis. The predicted interface residues largely matched the experimental interface residues, and the chains were placed in the correct relative orientation.

The pLDDT image also agreed with the comparison. Most of the structure had high confidence, and the superposition showed little deviation in the main folded regions.

Therefore, for this 1CSE prediction, the AF3 self-evaluation metrics were good indicators of prediction accuracy. They matched what was observed after comparison with the experimentally solved structure.