# Exercise 3 – Introduction to ChimeraX

I used the protein structure selected in the previous exercise from the **Mainly Beta** category:

- **Protein:** cAMP-activated global transcriptional regulator CRP
- **Organism:** *Escherichia coli*
- **PDB entry:** [4R8H](https://www.rcsb.org/structure/4R8H)
- **UniProt entry:** [P0ACJ8 / CRP_ECOLI](https://www.uniprot.org/uniprotkb/P0ACJ8/entry)
- **Chain used:** Chain A
- **Protein length in PDBsum:** 200 residues

I used **CATH**, **PDBsum**, and **ChimeraX** to inspect the structure, secondary-structure elements, surface representation, ligand-binding region, and CATH-classified domains.

---

## Part One

## 1. Secondary structure coloring in ChimeraX

I opened the structure in ChimeraX and visualized it in cartoon/ribbon representation. I used the **command-line approach**, not the sequence viewer, for the initial secondary-structure coloring.

```chimerax
open 4r8h
delete solvent
hide atoms
show cartoons
color gray
color helix red
color strand yellow
color coil lightgray
view
save 4r8h_secondary_structure.png width 1600 height 1200
```

Helices are shown in **red**, beta strands in **yellow**, and coil/loop regions in **gray/white**.

![](file:///Users/carlosmartinez/Desktop/4r8h_secondary_structure.png)

This view shows the overall distribution of secondary-structure elements. The protein contains both helices and beta strands, but the selected CATH domain from the previous exercise, **4r8hB01**, belongs to a **Mainly Beta** class.

---

## 2. Surface representation colored by chain

I switched the structure to surface representation and used `color bychain`.

```chimerax
open 4r8h
delete solvent
hide cartoons
show surface
color bychain
view
save 4r8h_surface_bychain.png width 1600 height 1200
```

![](file:///Users/carlosmartinez/Desktop/4r8h_surface_bychain.png)

The surface representation emphasized the external shape of the protein complex and the interface between chains. However, it did not show secondary-structure elements as clearly as the cartoon view.

---

## 3. Alternative representation: ligand-binding view

For the third representation, I used a combined cartoon/surface view and displayed the ligand more clearly.

```chimerax
open 4r8h
delete solvent
show cartoons
show surface
transparency 50 surface
show ligand
style ligand ball
color ligand green
color byhet
select ligand
view sel
save 4r8h_ligand_binding_view.png width 1600 height 1200
```

![](file:///Users/carlosmartinez/Desktop/4r8h_ligand_binding_view.png)

This representation helped identify the approximate ligand-binding region. The ligand is visible inside or near a pocket formed by the protein. This was less obvious in cartoon-only representation, where helices and beta strands are clear but cavities are not emphasized.

The semi-transparent surface helped show the external protein boundary while keeping the internal cartoon and ligand visible. I also displayed hydrogen bonds/contacts shorter than **2 Å** to show close interactions around the ligand-binding region. These contact lines helped identify which nearby residues may interact directly with the ligand or contribute to the binding pocket. The semi-transparent surface helped show the external protein boundary while keeping the internal cartoon, ligand, and contacts visible ( ```chimerax
hbonds ligand restrict protein distance 2.0 reveal true ```)


---

## 4. Selected helix using the sequence viewer

I used the ChimeraX sequence viewer to select one α-helix. I colored it differently and displayed its sidechains using cartoon-and-stick representation.

```chimerax
show cartoons
color gray
color sel blue
show sel atoms
style sel stick
label sel residues
view sel
save 4r8h_selected_helix_sidechains.png width 1600 height 1200
```

![](file:///Users/carlosmartinez/Desktop/4r8h_selected_helix_sidechains.png)

The selected helix is shown in **blue**, with sidechains as sticks. I used:

```chimerax
info residues sel
```

The selected helix in chain A included:

| Residue no. | Amino acid |
|---:|---|
| 169 | THR |
| 170 | ARG |
| 171 | GLN |
| 172 | GLU |
| 173 | ILE |
| 174 | GLY |
| 175 | GLN |
| 176 | ILE |
| 177 | VAL |
| 178 | GLY |

- **Selected helix:** chain A, residues **169–178**
- **Amino acid sequence:** **T-R-Q-E-I-G-Q-I-V-G**

This helix has mixed sidechains: THR and GLN are polar, ARG and GLU are charged, and ILE and VAL are hydrophobic. Thus, it is not purely hydrophobic or polar. It contains residues that can interact with solvent or polar groups, and residues that may contribute to protein packing.

There are two glycine residues, **GLY174** and **GLY178**. The final residue is glycine, which may be compatible with a turn or transition into another region because glycine is small and flexible. I did not observe proline in this helix.

Some sidechains face inward toward the protein or neighboring structural elements, while others project outward toward solvent. The stick representation made this clearer than cartoon-only representation.

---

## 5. Selected beta strand using the sequence viewer

I repeated the procedure for a **single beta strand**, not a complete beta sheet.

```chimerax
select /A:86-89
```

Then:

```chimerax
show cartoons
color gray
color sel orange
show sel atoms
style sel stick
label sel residues
view sel
save 4r8h_selected_beta_strand_sidechains.png width 1600 height 1200
```

![](file:///Users/carlosmartinez/Desktop/4r8h_selected_beta_strand_sidechains.png)

The selected beta strand in chain A included:

| Residue no. | Amino acid |
|---:|---|
| 86 | TRP |
| 87 | VAL |
| 88 | ARG |
| 89 | ALA |

- **Selected beta strand:** chain A, residues **86–89**
- **Amino acid sequence:** **W-V-R-A**

This beta strand has mixed character. TRP, VAL, and ALA are hydrophobic or mostly hydrophobic, while ARG is positively charged.

I did not observe proline or glycine in this beta strand. This is consistent with a stable beta-strand segment, since proline can disrupt regular backbone hydrogen-bonding patterns and glycine is more flexible.

In beta strands, sidechains usually alternate direction along the strand, pointing to opposite faces of the beta sheet. This differs from α-helices, where sidechains project outward around the helical axis.

---

## Part Two

## 1. CATH classification of the selected protein

The selected protein was CRP from *E. coli*, using **PDB 4R8H** and **UniProt P0ACJ8**. In PDBsum, chain A is classified into **two CATH domains**:

| Domain | Residue range | CATH no. | Class | Architecture |
|---|---:|---:|---|---|
| Domain 1 | A:9–138 | **2.60.120.10** | Mainly Beta | Sandwich |
| Domain 2 | A:139–208 | **1.10.10.10** | Mainly Alpha | Orthogonal Bundle |

This means that chain A contains more than one structural domain. Domain 1 is a **Mainly Beta** sandwich region, while Domain 2 is a **Mainly Alpha** orthogonal-bundle region.

The UniProt **Family & Domains** section should be checked for Gene3D/CATH hits. Here, PDBsum already shows multiple CATH-classified domains, consistent with a multidomain protein.

---

## 2. PDBsum protein page

I opened the PDBsum page for **4R8H** and used the **Protein** tab. For chain A, PDBsum reports:

| Feature | Count |
|---|---:|
| Sheets | 3 |
| Beta hairpins | 3 |
| Beta bulges | 6 |
| Strands | 12 |
| Helices | 7 |
| Helix-helix interactions | 15 |
| Beta turns | 12 |

PDBsum also lists the UniProt code as **P0ACJ8 (CRP_ECOLI)** and gives two CATH domains.

---

## 3. Comparison between PDBsum and ChimeraX sequence viewer

I compared the secondary-structure elements in the PDBsum sequence panel with those in the ChimeraX sequence viewer.

The main helices and beta strands were broadly consistent. Both tools show that chain A contains several helices and beta strands. Small differences may occur at the exact start or end of helices and strands because different tools can assign secondary-structure boundaries slightly differently.

PDBsum is useful for compact sequence-level summaries. ChimeraX is useful because the same residues can be selected and inspected directly in 3D.

---

## 4. Coloring CATH domains in ChimeraX

Using the CATH domain residue ranges from PDBsum, I selected each domain in ChimeraX and colored them differently. For this analysis, I focused only on **chain A**.

```chimerax
open 4r8h
delete solvent

select /A
delete ~sel
sel clear

hide atoms
show cartoons
color gray

select /A:9-138
color sel dodger blue

select /A:139-208
color sel orange

sel clear
view
save 4r8h_chainA_CATH_domains.png width 1600 height 1200
```

![](file:///Users/carlosmartinez/Desktop/4r8h_chainA_CATH_domains.png)

In this image, **Domain 1** is blue and **Domain 2** is orange.

The domain boundary occurs around residues **138–139**. Domain 1 contains the mainly beta sandwich region, while Domain 2 contains the mainly alpha orthogonal-bundle region. The boundary is easier to interpret in cartoon representation than in surface representation because the secondary-structure organization is visible.

---

## Summary

I used CATH, PDBsum, and ChimeraX to examine the CRP structure from **PDB 4R8H**. Chain A contains two CATH-classified domains: a **Mainly Beta** sandwich domain and a **Mainly Alpha** orthogonal-bundle domain.

ChimeraX allowed several complementary views. Cartoon representation was best for helices and beta strands, surface representation was best for external shape and chain interfaces, and combined representations were useful for ligand-binding regions and sidechain orientation.

No single representation showed everything clearly, so switching between cartoon, surface, ligand, and sidechain views was necessary to interpret the protein structure.