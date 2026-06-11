# Exercise 5 – Electrostatic Potential, Hydrophobicity, and Intermolecular Interactions

For this exercise, I used **PDB 1HSG**, HIV protease in complex with an inhibitor. I chose this structure because it contains a clear ligand-binding interface, so it is suitable for analyzing electrostatic potential, hydrophobicity, hydrogen bonds, and contacts.

The interaction partner was identified in ChimeraX using the `ligand` selector. The selected ligand was **MK1**, residue **/B:902**.

---

## Part 1 – Protein background and hypothesis

The protein used in this assignment was **HIV protease**. HIV protease is an aspartyl protease that cleaves viral Gag and Gag-Pol polyproteins during viral maturation. These cleavages produce the mature viral proteins needed to form infectious particles.

The structure **1HSG** contains HIV protease bound to the inhibitor **MK1**, also described as L-735,524 / indinavir-like inhibitor. HIV protease inhibitors bind in the active-site tunnel of the protease dimer.

My hypothesis was that the protein–ligand interface would be **mixed**, but mainly dominated by **hydrophobic and van der Waals interactions**. The ligand is large and carbon-rich, so I expected many nonpolar contacts with the binding pocket. However, because HIV protease is an aspartyl protease and the ligand contains polar groups, I also expected some specific hydrogen bonds near the catalytic site.

---

## Initial structure inspection

I first opened the structure in ChimeraX and made a clean cartoon view.

```chimerax
open 1hsg
delete solvent
hide atoms
show cartoons
color lightgray
view
```

I then displayed the ligand:

```chimerax
show ligand atoms
style ligand ball
color ligand green
view ligand
```

To confirm the ligand identity, I used:

```chimerax
select ligand
info residues sel
```

The ligand was identified as:

```text
residue id /B:902 name MK1
```

![Initial inspection](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/1HSG_MK1_inital_inspection.png)

![Ligand view](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/1HSG_MK1_ligand_view.png)

---

## Part 2 – Interface residues within 4 Å of the ligand

To identify residues within 4 Å of the ligand, I used zone selection in ChimeraX:

```chimerax
select ligand
select zone sel 4 residues true
delete solvent
info residues sel
```

The residues selected within 4 Å of the ligand were:

| Chain | Residue number | Residue |
|---|---:|---|
| A | 8 | ARG |
| A | 23 | LEU |
| A | 25 | ASP |
| A | 27 | GLY |
| A | 28 | ALA |
| A | 32 | VAL |
| A | 47 | ILE |
| A | 48 | GLY |
| A | 49 | GLY |
| A | 81 | PRO |
| A | 82 | VAL |
| A | 84 | ILE |
| B | 8 | ARG |
| B | 25 | ASP |
| B | 27 | GLY |
| B | 28 | ALA |
| B | 29 | ASP |
| B | 30 | ASP |
| B | 32 | VAL |
| B | 47 | ILE |
| B | 48 | GLY |
| B | 49 | GLY |
| B | 50 | ILE |
| B | 81 | PRO |
| B | 82 | VAL |
| B | 84 | ILE |

In total, **26 protein residues** were found within 4 Å of the ligand.

These residues came from both chains of the HIV protease dimer, which is expected because the ligand binds in the central active-site tunnel between the two monomers.

![Interface residues](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/1HSG_ligand_interface_residues.png)

---

## Part 3 – Electrostatic potential surface

To color the protein surface by electrostatic potential, I used the `coulombic` command:

```chimerax
open 1hsg
delete solvent
hide atoms
show surface
show cartoons
transparency 40 surface

show ligand atoms
style ligand ball
color ligand green

coulombic
view ligand
save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/1HSG_ligand_coulombic_surface.png width 1600 height 1200
```

![Coulombic surface](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/1HSG_ligand_coulombic_surface.png)

The Coulombic surface showed a **mixed electrostatic environment** around the ligand-binding pocket. There were red negative regions, blue positive regions, and white/neutral regions.

The binding pocket did not appear to be purely positive or purely negative. Instead, the interface was **mixed**, with negative patches near the active site and more neutral/weakly charged regions around the tunnel. This is consistent with the ligand, which contains both polar groups and large hydrophobic regions.

Therefore, electrostatic interactions probably contribute to binding, but they do not appear to be the only dominant interaction type.

---

## Part 4 – Lipophilic potential / hydrophobicity surface

To color the protein surface by lipophilic potential, I used the `mlp` command:

```chimerax
open 1hsg
delete solvent
hide atoms
show surface
show cartoons
transparency 40 surface

show ligand atoms
style ligand ball
color ligand green

mlp
view ligand
save /Users/carlosmartinez/Documents/Technion/Structural_BioInf/1HSG_ligand_mlp_surface.png width 1600 height 1200
```

![MLP surface](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/1HSG_ligand_mlp_surface.png)

The MLP surface showed hydrophobic patches around the ligand-binding pocket. The interface was not completely hydrophobic, but it contained several hydrophobic regions close to the ligand.

The most hydrophobic parts of the interface appeared near the nonpolar ligand groups, especially around residues such as **LEU, VAL, ILE, PRO, ALA, and GLY** in the 4 Å interface list. These residues are consistent with a hydrophobic binding pocket.

Overall, the interface appeared **mixed but strongly hydrophobic**. The Coulombic surface showed charged and polar regions, while the MLP surface showed that much of the ligand-binding tunnel is hydrophobic. This supports the idea that hydrophobic contacts help shape the binding pocket, while polar and charged regions contribute to specificity and ligand orientation.

---

## Part 5 – Hydrogen bonds and contacts

I used the `hbonds` and `contacts` commands to analyze intermolecular interactions between the ligand and the protein.

```chimerax
hbonds ligand restrict protein reveal true
```

The ChimeraX log reported:

```text
9 hydrogen bonds found
```

Then I ran:

```chimerax
contacts ligand restrict protein distanceOnly 4 reveal true
```

The ChimeraX log reported:

```text
97 distances
```

I interpreted these 97 distances as protein–ligand contact distances within the specified 4 Å cutoff. The contact analysis was consistent with the zone selection, which found **26 protein residues** near the ligand.

![Hydrogen bonds and contacts](file:///Users/carlosmartinez/Documents/Technion/Structural_BioInf/1HSG_ligand_hbonds_contacts.png)

The hydrogen bonds show that polar interactions contribute to the interface. However, the larger number of contact distances and the many nonpolar residues in the interface suggest that hydrophobic and van der Waals contacts are also important.

---

## Part 6 – Connecting the hypothesis with the results

My initial hypothesis was that the HIV protease–MK1 interface would be mixed, but mainly dominated by hydrophobic and van der Waals interactions, with some specific hydrogen bonds near the catalytic site.

The results supported this hypothesis. The 4 Å interface included many nonpolar residues, such as **LEU, VAL, ILE, PRO, ALA, and GLY**, which suggests a strong hydrophobic component. The MLP surface also showed hydrophobic patches around the ligand-binding pocket.

At the same time, the Coulombic surface showed a mixed electrostatic environment, and the `hbonds` command identified **9 hydrogen bonds** between the ligand and the protein. Therefore, polar interactions are also important, especially for positioning the ligand inside the active-site tunnel.

Overall, the interface is best described as **mixed**, but with a major contribution from **hydrophobic and van der Waals contacts**. Hydrogen bonds and electrostatic features appear to provide additional specificity and orientation. This fits what is known about HIV protease inhibitors, which bind in the active-site tunnel using carbon-rich groups while also forming specific polar contacts.