# Exercise 2 – Secondary Structure

I used the protein-structure classification database [CATH](https://cathdb.info/). CATH classifies solved protein structures from the Protein Data Bank (PDB) according to a domain hierarchy: **Class**, **Architecture**, **Topology**, and **Homologous Superfamily**. It is important to note that CATH is organized by protein **domains**, not by protein names.

On the CATH website, I used the option:

**Browse → Browse CATH-Gene3D Hierarchy**

I selected one representative domain from each of the following structural classes:

- Mainly Alpha
- Mainly Beta
- Alpha Beta

For each class, I browsed through the CATH hierarchy, selected a superfamily, and then used the **Functional Families (FunFams)** table to choose a domain with a solved 3D structural representative.

---

## 1. Mainly Alpha

I browsed the CATH hierarchy as follows:

**Browse → 1 Mainly Alpha → 1.10 Orthogonal Bundle → 1.10.490 Globin-like → 1.10.490.10 Globins**

Then I clicked **Go to Superfamily**, which led to the [Globin Superfamily CATH summary page](https://cathdb.info/version/latest/superfamily/1.10.490.10). In the **Functional Families** section, I selected the FunFam with the highest number of total sequences and a solved 3D structural representative.

| ID | Function Family (FunFam) Name | Total Sequences | Enzyme? | Structure? | Structural Representative | PDB Sites? | Alignment Diversity (0–100) |
|---|---|---:|---|---|---|---|---:|
| [1](https://cathdb.info/version/v4_4_0/superfamily/1.10.490.10/funfam/1) | **[Hemoglobin subunit beta](https://cathdb.info/version/v4_4_0/superfamily/1.10.490.10/funfam/1)** | 1324 |  | 3D | [6nbdD00](https://cathdb.info/version/v4_4_0/domain/6nbdD00) | - | 96.9 |

The selected CATH domain was **6nbdD00**, and its CATH classification is:

**1.10.490.10**

This corresponds to:

**Mainly Alpha → Orthogonal Bundle → Globin-like → Globins**

This domain belongs to the **Mainly Alpha** class because globin domains are dominated by α-helices. In hemoglobin, these helices pack around the heme-binding region. Therefore, the overall fold is mostly helical, with little contribution from β-sheet structure.

---

## 2. Mainly Beta

Using the same procedure, I selected the following representative for the **Mainly Beta** class:

| ID                                                                       | Function Family (FunFam) Name                                                                                                  | Total Sequences | Enzyme? | Structure? | Structural Representative                                    | PDB Sites? | Alignment Diversity (0–100) |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | --------------: | ------- | ---------- | ------------------------------------------------------------ | ---------- | --------------------------: |
| [1](https://cathdb.info/version/v4_4_0/superfamily/2.60.120.10/funfam/1) | **[cAMP-activated global transcriptional regulator CRP](https://cathdb.info/version/v4_4_0/superfamily/2.60.120.10/funfam/1)** |            1193 |         | 3D         | [4r8hB01](https://cathdb.info/version/v4_4_0/domain/4r8hB01) | -          |                        79.5 |

The selected CATH domain was **4r8hB01**, and its CATH classification is:

**2.60.120.10**

Because the classification begins with **2**, this domain belongs to the **Mainly Beta** class. This means that the domain fold is dominated by β-strands and β-sheets rather than by α-helices.

---

## 3. Alpha Beta

Using the same procedure, I selected the following representative for the **Alpha Beta** class:

| ID | Function Family (FunFam) Name | Total Sequences | Enzyme? | Structure? | Structural Representative | PDB Sites? | Alignment Diversity (0–100) |
|---|---|---:|---|---|---|---|---:|
| [1](https://cathdb.info/version/v4_4_0/superfamily/3.40.50.720/funfam/1) | **[Glyceraldehyde-3-phosphate dehydrogenase](https://cathdb.info/version/v4_4_0/superfamily/3.40.50.720/funfam/1)** | 3019 |  | 3D | [3rvdQ01](https://cathdb.info/version/v4_4_0/domain/3rvdQ01) | - | 94.9 |

The selected CATH domain was **3rvdQ01**, and its CATH classification is:

**3.40.50.720**

Because the classification begins with **3**, this domain belongs to the **Alpha Beta** class. This means that both α-helices and β-strands are important components of the domain fold.

---

## 4. Ramachandran plots for each representative

For each selected CATH domain, I inspected the corresponding PDBsum Ramachandran plot of the structural representative.

### Mainly Alpha

Selected domain: **6nbdD00**

[Link to Ramachandran plot](https://www.ebi.ac.uk/thornton-srv/databases/cgi-bin/pdbsum/getimg.pl?&source=pdbsum&pdb_code=6nbd&file=ramach.gif)

![[Pasted image 20260520141943.png]]

### Mainly Beta

Selected domain: **4r8hB01**

[Link to Ramachandran plot](https://www.ebi.ac.uk/thornton-srv/databases/cgi-bin/pdbsum/getimg.pl?&source=pdbsum&pdb_code=4r8h&file=ramach.gif)

![[Pasted image 20260520142147.png]]

### Alpha Beta

Selected domain: **3rvdQ01**

[Link to Ramachandran plot](https://www.ebi.ac.uk/thornton-srv/databases/cgi-bin/pdbsum/getimg.pl?&source=pdbsum&pdb_code=3rvd&file=ramach.gif)

![[Pasted image 20260520142549.png|500]]

---

## 5. Analysis of the Ramachandran plots

The three Ramachandran plots reflect the secondary-structure composition of the selected CATH classes. Each point in a Ramachandran plot represents the backbone dihedral angles **φ** and **ψ** of an amino acid residue. Different secondary structures occupy characteristic regions of the plot.

The **Mainly Alpha** representative, **6nbdD00**, is expected to be enriched in the right-handed α-helical region, with approximate φ and ψ values around **−60°** and **−45°**. This matches the globin fold, which is dominated by α-helices.

The **Mainly Beta** representative, **4r8hB01**, is expected to show stronger enrichment in the β-strand or β-sheet region, where **φ is negative** and **ψ is positive**. This reflects the extended backbone conformation typical of β-strands.

The **Alpha Beta** representative, **3rvdQ01**, is expected to contain substantial populations in both the α-helical and β-sheet regions. This is consistent with Alpha Beta domains, where both α-helices and β-strands are major structural elements.

Therefore, the Ramachandran distributions provide a structural explanation for the CATH class assignments: mainly α-helical domains cluster strongly in the α-helical region, mainly β domains are enriched in the β-sheet region, and α/β domains show populations in both regions.