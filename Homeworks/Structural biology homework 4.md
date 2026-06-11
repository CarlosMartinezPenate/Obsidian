# Exercise 4 – Using Conservation to Study Function

I used the files provided for the homework and the ConSurf Colab interface to analyze conservation and function.

This exercise had three parts:

- Shannon entropy calculation from a small multiple sequence alignment
- ConSurf analysis of a selected protein structure
- Comparison of ConSurf conservation with catalytic residues from M-CSA

For Part Two and Part Three, I used **Carbonic Anhydrase II.**

---

## Part One – Shannon Entropy

I opened the file `W4_home_assignment_MSA.txt`, which contains a multiple sequence alignment of 10 sequences:

```text
Seq1   MLVGDAKSTWQHAFERLQNP
Seq2   MIVGDAKSIWQHAFDRLQNP
Seq3   MFLGDAKSTWQHAFERLQSP
Seq4   MLLGDAKSVWQHAFDRLQNP
Seq5   MVMGDAKSTWQHAFERLQTP
Seq6   MILGDAKSIWQHAFDRLQNP
Seq7   MFLGDAKSAWQHAFERLQSP
Seq8   MLLGDAKSTWQHAFDRLQNP
Seq9   MVMGDAKSVWQHAFERLQTP
Seq10  MIVGDAKSAWQHAFERLQNP
```

The Shannon entropy was calculated using:

```text
H = -Σ pi log2(pi)
```

where `pi` is the frequency of each amino acid at the selected position.

The requested positions were **2, 5, and 9**.

---

### Position 2

The amino acids at position 2 were:

| Amino acid | Count | Frequency |
|---|---:|---:|
| L | 3 | 0.3 |
| I | 3 | 0.3 |
| F | 2 | 0.2 |
| V | 2 | 0.2 |

The entropy calculation was:

```text
H = -[(0.3 log2 0.3) + (0.3 log2 0.3) + (0.2 log2 0.2) + (0.2 log2 0.2)]
H ≈ 1.97
```

So:

```text
Position 2: H ≈ 1.97
```

---

### Position 5

At position 5, all sequences had **D**.

| Amino acid | Count | Frequency |
|---|---:|---:|
| D | 10 | 1.0 |

The entropy calculation was:

```text
H = -[1.0 log2 1.0]
H = 0
```

So:

```text
Position 5: H = 0
```

---

### Position 9

The amino acids at position 9 were:

| Amino acid | Count | Frequency |
|---|---:|---:|
| T | 4 | 0.4 |
| I | 2 | 0.2 |
| V | 2 | 0.2 |
| A | 2 | 0.2 |

The entropy calculation was:

```text
H = -[(0.4 log2 0.4) + (0.2 log2 0.2) + (0.2 log2 0.2) + (0.2 log2 0.2)]
H ≈ 1.92
```

So:

```text
Position 9: H ≈ 1.92
```

---

### Shannon entropy summary

| Position | Amino acids observed | Shannon entropy | Interpretation |
|---:|---|---:|---|
| 2 | L, I, F, V | **1.97** | Highly variable |
| 5 | D | **0.00** | Fully conserved |
| 9 | T, I, V, A | **1.92** | Highly variable |

Position **2** was the most variable of the three positions, with **H ≈ 1.97**. Position **9** was also highly variable, with **H ≈ 1.92**. Position **5** was fully conserved, with **H = 0**, because all sequences had aspartate (**D**) at this position.

An interesting point is that position 2 is variable, but all observed amino acids are hydrophobic: **L, I, F, and V**. Therefore, although the exact amino acid changes, the chemical character is conserved. This suggests that hydrophobicity may be more important than the exact residue identity at this position.

Position 9 is also variable, but it includes both polar threonine (**T**) and hydrophobic residues (**I, V, A**), so it is chemically more mixed than position 2.

---

## Part Two – ConSurf

For the ConSurf analysis, I selected:

- **Protein:** Carbonic Anhydrase II
- **PDB entry:** 2CBA
- **Chain:** A

I first attempted to use **lysozyme, PDB 1LYZ**, but the ConSurf Colab run failed repeatedly. I also tried other proteins and parameter combinations, but errors still occurred near the final conservation-scoring step. After debugging the Colab pipeline, as described in the next section, I chose **Carbonic Anhydrase II, PDB 2CBA**, which completed successfully.

---

### Debugging the ConSurf Colab run

When I first tried to run ConSurf in Colab, the run failed during the CD-HIT step with this error:

```text
CD-HIT produced no output
```

To understand the problem, I inspected the Colab `/content/` directory and found that the homolog file was being created correctly. For example, for one run (not the one reported) the file:

```text
/content/SBI_HW4_1/query_homolougs.txt
```

contained a valid FASTA file, and:

```bash
!grep -c "^>" /content/SBI_HW4_1/query_homolougs.txt
```

returned:

```text
2247
```

This showed that the homolog sequences were present. The problem was not the homolog search.

I then tested CD-HIT directly:

```bash
!/content/cdhit/cd-hit -i /content/SBI_HW4_1/query_homolougs.txt -o /content/test_cdhit.out -c 0.8 -n 5 -d 0
```

This failed because the executable `/content/cdhit/cd-hit` did not exist. I found that the CD-HIT source files were present, but the program had not been compiled. The source file was present as:

```text
/content/cdhit/cdhit.c++
```

I compiled CD-HIT using:

```bash
!cd /content/cdhit && make
```

After compilation, the executable was created. I verified that CD-HIT worked by running:

```bash
!/content/cdhit/cd-hit -h | head -20
```

Then I tested CD-HIT manually on the homolog file:

```bash
!/content/cdhit/cd-hit -i /content/SBI_HW4_1/query_homolougs.txt -o /content/test_cdhit.out -c 0.8 -n 5 -d 0
```

This time the program completed successfully:

```text
total seq: 2247
2247 finished
996 clusters
program completed
```

Therefore, the first problem was that CD-HIT had to be compiled manually in the Colab environment.

After fixing the CD-HIT issue, I retried ConSurf. The run still failed during the Rate4Site step. I also debugged this step in a similar way, by checking whether the intermediate files were being created and whether the required executables were present. After debuggin, I ran ConSurf with **Carbonic Anhydrase II, PDB 2CBA**, with default settings. 

---

### ConSurf parameters and output

For the successful **2CBA chain A** run, ConSurf reported:

```text
There are 2314 MMseqs2 hits.
2184 of them are unique, including the query.
The calculation was performed on a sample of 150 sequences.
5745 homologues were collected.
The best evolutionary model was selected to be: WAG.
```

The output files included:

```text
SBI_HW4_bis_5_2CBA_A_With_Conservation_Scores.pdb
SBI_HW4_bis_5_consurf_colored_seq.pdf
SBI_HW4_bis_5_consurf_grades.txt
SBI_HW4_bis_5_msa_fasta.aln
SBI_HW4_bis_5_Tree.txt
SBI_HW4_bis_5_model_selection.txt
```

The ConSurf conservation scale is:

| Grade | Meaning |
|---:|---|
| 1 | Variable |
| 5 | Average |
| 9 | Conserved |

In the ConSurf output, exposed residues are marked with `e`, buried residues with `b`, predicted functional residues with `f`, and predicted structural residues with `s`.

---

### ChimeraX visualization of ConSurf output

I opened the ConSurf-modified PDB file in ChimeraX:

```text
/Users/carlosmartinez/Downloads/Consurf_Outputs_SBI_HW4_bis_5/SBI_HW4_bis_5_2CBA_A_With_Conservation_Scores.pdb
```

The commands used were:

```chimerax
open /Users/carlosmartinez/Downloads/Consurf_Outputs_SBI_HW4_bis_5/SBI_HW4_bis_5_2CBA_A_With_Conservation_Scores.pdb
delete solvent
hide atoms
show cartoons
show surface
transparency 50 surface
color bfactor pal maroon:white:cyan range 9,1
view
save /Users/carlosmartinez/Desktop/2CBA_ConSurf_surface_cartoon.png width 1600 height 1200
```

The command:

```chimerax
color bfactor pal maroon:white:cyan range 9,1
```

colors the structure according to the ConSurf conservation grades stored in the B-factor field. In this color scale, **maroon** indicates conserved residues, **white** indicates intermediate conservation, and **cyan** indicates variable residues.

![](file:///Users/carlosmartinez/Desktop/2CBA_ConSurf_surface_cartoon.png)

I also saved a screenshot of the ConSurf PDF sequence output colored by conservation:
![](file:///Users/carlosmartinez/Desktop/2CBA_ConSurf_sequence.png)


---

### Buried residues and conservation

When examining the surface/cartoon representation, buried residues did not appear to be uniformly variable. Many buried residues showed intermediate to high conservation. This is expected because buried residues often contribute to maintaining the protein fold.

However, the most conserved residues were not only buried residues. The ConSurf output also marked some highly conserved exposed residues as predicted functional residues. Therefore, buried residues can be relatively conserved, but conserved exposed residues are more likely to indicate functional regions, such as the active site.

In other words, conservation can reflect both:

- **structural constraints**, such as buried residues needed for folding or stability
- **functional constraints**, such as exposed residues involved in catalysis, metal coordination, or substrate binding

---

## Part Three – M-CSA

I used the same enzyme as in Part Two: **Carbonic Anhydrase II**.

In M-CSA, searching for **2CBA** gave one relevant entry:

| M-CSA ID | Enzyme name | EC | PDB used by M-CSA | Catalytic CATH |
|---:|---|---|---|---:|
| 216 | carbonate dehydratase, alpha class | 4.2.1.1 | 1CA2 | 3.10.200.10 |

Although I used **2CBA** in ConSurf, M-CSA uses **1CA2** as the reference PDB for the catalytic annotation. Both correspond to the same enzyme class, carbonate dehydratase / carbonic anhydrase.

---

### Catalytic residues from M-CSA

M-CSA describes the reaction as occurring in two steps. First, a zinc-bound hydroxide attacks carbon dioxide to form bicarbonate. Then the hydroxide is regenerated by proton transfer involving water and **His64**.

The catalytic and active-site residues listed by M-CSA were:

| Catalytic / active-site residue | Three-letter code | Role |
|---|---|---|
| Thr199 | **THR199** | Helps orient CO₂ and enhances hydroxide nucleophilicity |
| Glu106 | **GLU106** | Hydrogen-bonds to Thr199 and helps activate it |
| His64 | **HIS64** | Proton shuttle; helps regenerate OH⁻ |
| His94 | **HIS94** | Zinc-binding residue |
| His96 | **HIS96** | Zinc-binding residue |
| His119 | **HIS119** | Zinc-binding residue |

M-CSA also reports some residue numbering in a mapped form, for example:

```text
Thr199(197)A
Glu106(105)A
His64(63)A
His94(93)A
His96(95)A
His119(118)A
```

This means that sequence numbering and PDB atom numbering can differ slightly. For comparison with ConSurf, I used the residue labels in the ConSurf output file.

---

### Comparison between M-CSA and ConSurf

I compared the M-CSA catalytic residues with the ConSurf conservation grades.

| M-CSA residue | Expected role | ConSurf interpretation |
|---|---|---|
| HIS64 | Proton shuttle | Exposed |
| HIS94 | Zinc binding | Exposed, Functional |
| HIS96 | Zinc binding | Buried, Functional |
| HIS119 | Zinc binding | Buried, Structural |
| GLU106 | Activates/stabilizes Thr199 network | Exposed, Functional |
| THR199 | Substrate orientation / hydroxide activation | Exposed, Functional |

The ConSurf results were consistent with the M-CSA annotation. The catalytic and active-site residues were generally conserved, which is expected because these residues are involved in catalysis, zinc coordination, proton transfer, and active-site geometry.

However, not all conserved residues were catalytic residues. The ConSurf output also showed highly conserved residues that were not listed as catalytic in M-CSA. These residues may be conserved because they stabilize the fold, maintain the active-site geometry, or support the catalytic environment indirectly. Therefore, catalytic residues are usually conserved, but conservation alone does not prove that a residue is catalytic. Some conserved residues are conserved for structural stability or indirect functional roles.
