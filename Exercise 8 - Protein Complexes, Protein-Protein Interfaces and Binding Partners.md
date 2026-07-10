
## Protein used

For this exercise, as for the previous one, I used **PDB 1CSE**, the protein–protein complex between **Subtilisin Carlsberg** and **Eglin C**.

| Item | Entry |
|---|---|
| PDB entry | 1CSE |
| Complex type | Protein–protein |
| Monomer selected for Multi-VORFFIP | Subtilisin Carlsberg |
| Experimental chain | chain E |
| Binding partner | Eglin C |
| Partner chain in experimental PDB | chain I |
| AF3 chain for Subtilisin Carlsberg | chain A |
| AF3 chain for Eglin C | chain B |
| Multi-VORFFIP output used | pbs |

---

# Part One – Multi-VORFFIP prediction

## 1. Saving the single protein chain

From **1CSE**, I selected only Subtilisin Carlsberg, chain **E**, and saved it as a separate PDB file.

```chimerax
close
open 1cse

select #1/E
save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/1CSE_chainE_subtilisin.pdb selectedOnly true
```

This single-chain PDB file was submitted to Multi-VORFFIP.

Since **1CSE** is a protein–protein complex, I used the `pbs` output file:

```text
/Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/1CSE_CHAINE_SUBTILISIN_1783579741_pbs.pdb
```

The `pbs` file corresponds to predicted protein-binding-site residues.

---

## 2. Multi-VORFFIP predicted residues

I opened the `pbs` file in ChimeraX and selected residues with B-factor score higher than 9.

```chimerax
close
open /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/1CSE_CHAINE_SUBTILISIN_1783579741_pbs.pdb

hide atoms
show cartoons
color white

select #1@@bfactor > 9
color sel red
show sel atoms
style sel stick
label sel residues
view sel

save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/MultiVORFFIP_1CSE_pbs_interface.png width 1600 height 1200
```

Multi-VORFFIP prediction:

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/MultiVORFFIP_1CSE_pbs_interface.png)

Multi-VORFFIP selected **92 residues**:

```text
THR33, ASN43, VAL45, PHE50, VAL51, ALA52, GLY53, GLU54, TYR57, ASN58,
ASP60, GLY61, ASN62, HIS64, LEU96, ASN97, SER98, SER99, GLY100, SER101,
GLY102, SER103, TYR104, SER105, GLY106, ILE107, VAL108, ASN117, SER125,
LEU126, GLY127, GLY128, ALA129, SER130, GLY131, SER132, THR133, ALA134,
LYS136, ASP140, ARG145, ALA152, ALA153, GLY154, ASN155, SER156, GLY157,
ASN158, SER159, GLY160, SER161, THR162, ASN163, THR164, ILE165, GLY166,
TYR167, LYS170, TYR171, ASP181, SER182, ASN183, SER184, ASN185, ARG186,
ALA187, SER188, PHE189, ALA203, GLY204, TYR209, PRO210, THR211, ASN212,
THR213, TYR214, ALA215, THR216, LEU217, ASN218, GLY219, THR220, SER221,
MET222, PRO239, TYR256, GLY258, SER259, SER260, PHE261, TYR262, TYR263
```

This prediction includes the real interface region, but it is broad and contains many extra surface residues.

---

# Part Two – AF3 interface residues

## 3. Interface in the AlphaFold3 predicted complex

I opened the AlphaFold3 complex from Exercise 7 and selected Subtilisin Carlsberg residues within **4 Å** of Eglin C.

```chimerax
close
open /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise7/fold_2026_06_24_15_06_hw7/fold_2026_06_24_15_06_hw7_model_0.cif

select clear
select #1/B
select zone sel 4 residues true
select sel & #1/A
label sel residues
show sel atoms
style sel stick
color sel cyan
view sel

save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/AF3_1CSE_interface_residues.png width 1600 height 1200
```

AF3 interface residues:

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/AF3_1CSE_interface_residues.png)

AF3 selected **26 residues**:

```text
THR33, ASN61, HIS63, LEU95, SER98, GLY99, SER100, GLY101, TYR103, ILE106,
SER124, LEU125, GLY126, GLY127, ALA151, GLY153, ASN154, ASN157, SER158,
SER187, PHE188, TYR208, ASN217, GLY218, THR219, SER220
```

This is a focused interface region.

---

# Part Three – Experimental PDB interface

## 4. Interface in the experimental structure

I selected Subtilisin Carlsberg residues in chain **E** within **4 Å** of Eglin C chain **I**.

```chimerax
close
open 1cse

select clear
select #1/I
select zone sel 4 residues true
select sel & #1/E
label sel residues
show sel atoms
style sel stick
color sel yellow
view sel

save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/PDB_1CSE_interface_residues.png width 1600 height 1200
```

Experimental PDB interface residues:

![](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/Exercise8/PDB_1CSE_interface_residues.png)

The experimental structure selected **26 residues**:

```text
THR33, ASN62, HIS64, LEU96, SER99, GLY100, SER101, GLY102, TYR104, ILE107,
SER125, LEU126, GLY127, GLY128, ALA129, SER130, ALA152, GLY154, ASN155,
PHE189, TYR209, LEU217, ASN218, GLY219, THR220, SER221
```

This was used as the reference interface.

---

# Part Four – Comparison

## 5. Multi-VORFFIP vs AF3 vs experimental interface

| Method | Number of residues selected | Result |
|---|---:|---|
| Experimental PDB interface | 26 | reference |
| AF3 interface | 26 | focused prediction |
| Multi-VORFFIP | 92 | broad prediction |

AF3 predicted a very similar interface to the experimental structure. Several residue numbers are shifted by one, but they match the same structural regions.

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

Multi-VORFFIP included all experimental interface residues, so it detected the real interface. However, it also predicted many additional residues across the protein surface.

In this case:

```text
AF3 = more specific
Multi-VORFFIP = sensitive but less specific
```

---

## 6. Which method was more accurate?

AF3 was more accurate for this case.

AF3 predicted a focused interface and recovered the main contact region with fewer extra residues. Multi-VORFFIP captured the true interface, but overpredicted many surface residues.

Overall, **AF3 gave the better interface prediction** for the 1CSE protein–protein complex.