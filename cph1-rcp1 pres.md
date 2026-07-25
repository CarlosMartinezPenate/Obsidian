---
title: Cph1 Structural Bioinformatics Presentation – Carlos (Slides 1–12)
tags:
  - presentation
  - bioinformatics
  - phytochrome
  - cph1
---

# Cph1 Structural Bioinformatics Presentation
## Carlos — Slides 1–12 (~5 min)

---

# Slide 1 — Title

Good morning everyone.

Today, Manu and I will present a structural and functional analysis of the cyanobacterial phytochrome **Cph1** and its interaction with the response regulator **Rcp1**.

Our central question is:

> **How does Cph1 convert light into a biochemical signal?**

To answer this, we combined experimental structural data with computational structural biology tools, including AlphaFold3, evolutionary conservation analysis, and structural modeling.

---

# Slide 2 — Cyanobacteria use light to make biomass and oxygen
Cyanobacteria are **ancient aquatic photosynthetic microorganisms** that have inhabited Earth’s oceans for over **2.5 billion years**. They are found in virtually every aquatic environment, from freshwater lakes to the open ocean, and today contribute roughly **half of global biological oxygen production**.

Because they rely on sunlight for photosynthesis, they must cope with constantly changing light conditions. In the oceans, near the water surface, light is abundant, while at greater depths both its **intensity** and **spectral composition** change.

To adapt, cyanobacteria use large light-harvesting complexes called **phycobilisomes**, which function like solar antennae. These antennae continuously adjust to maximize photosynthesis while preventing damage caused by excess light.

**One of the best-studied model cyanobacteria is Synechocystis sp. PCC 6803, in which the Cph1–Rcp1 light-sensing pathway has been extensively characterized.**

---

# Slide 3 — Cyanobacteria utilize light to trigger an adaptive response

To sense these environmental changes, cyanobacteria use signaling proteins such as **Cph1**.

When the **PCB chromophore** absorbs red or far-red light, it undergoes a small structural change.

This conformational change propagates through Cph1 and activates its **histidine kinase** domain.

The activated kinase then transfers a phosphate group to the response regulator **Rcp1**, which regulates the expression of light-responsive genes.

This leads to our research question:

> **What structural features enable Cph1 to detect light and transmit this signal to its histidine kinase domain?**

---

# Slide 4 — AlphaFold model

To answer this question, we first needed a reliable structural model.

Our first objective was therefore to determine whether **AlphaFold** could accurately predict the structure of Cph1 before using the model for functional interpretation.

---

# Slide 5 — Can AlphaFold recover the experimental structure?

Before comparing the model with the experimental structure, it’s useful to ask:

**How confident is AlphaFold in this prediction?**

The protein is colored according to **pLDDT**, AlphaFold’s confidence score for individual residues.

- **Blue** indicates very high confidence.
- **Light blue** indicates good confidence.
- **Yellow** corresponds to lower confidence, which is mainly found in flexible loops and terminal regions.

On the right is the **Predicted Aligned Error**, or **PAE**, which estimates how confidently AlphaFold predicts the relative positions of different parts of the protein.

The dark green blocks along the diagonal indicate that each domain is predicted with high confidence, while the lighter regions between domains suggest greater uncertainty in their relative orientation.

Overall, the model has a **pTM score of 0.81**, indicating that the overall fold is predicted with good confidence.

To validate this prediction, we compared it with the experimentally determined structure.

Our structural alignment produced an **RMSD of only 0.665 Å**, demonstrating excellent agreement between the AlphaFold model and the crystal structure.

Although only the photosensory module is available experimentally, this gives us confidence to use the full-length model for the remaining analyses.

---

# Slide 6 — Electrostatic surface model

Next, we examined the electrostatic surface of Cph1.

Electrostatic properties influence how proteins recognize ligands and interact with other proteins.

The model reveals distinct positively and negatively charged regions surrounding the photosensory module, suggesting potential interaction surfaces involved in ligand recognition and signal transmission.

---

# Slide 7 — Hydrophobic surface model

We also analyzed the hydrophobic surface.

As expected for a soluble signaling protein, most of the surface is hydrophilic, while localized hydrophobic patches are concentrated within the chromophore-binding pocket.

These hydrophobic residues help stabilize the protein core and create the environment required for PCB binding.

---

# Slide 8 — ConSurf: Functional regions

Next, we asked which regions are most likely to be functionally important.

Using **ConSurf**, we identified residues that are evolutionarily conserved across homologous proteins.

The strongest conservation is concentrated around the chromophore-binding region and along the structural elements responsible for transmitting the light signal.

This suggests that these regions are under strong evolutionary pressure because they are essential for Cph1 function.

---

# Slide 9 — Domain organization

Using UniProt annotations together with our structural model, we identified the major functional domains of Cph1.

- **PAS domain** – sensory support.
- **GAF domain** – binds the PCB chromophore.
- **PHY domain** – stabilizes the light-activated state and propagates the signal.
- **Histidine kinase domain** – transfers the phosphate signal to Rcp1.

Together, the PAS, GAF, and PHY domains form the **photosensory module**, which converts light perception into structural changes that activate the kinase domain.

---

# Slide 10 — Predicted Cph1 dimer

AlphaFold3 also predicts a plausible **Cph1 homodimer**, which is biologically reasonable because many bacterial histidine kinases function as dimers.

Again, we can evaluate the prediction using AlphaFold confidence metrics.

The individual monomers remain mostly blue, indicating that each protein is predicted with high confidence.

The **PAE matrix** now contains four large blocks, representing the two individual proteins and their predicted relationship.

The overall fold has a **pTM score of 0.60**, while the interface has an **ipTM score of 0.52**.

Here, **pTM** reflects confidence in the structure of the complex as a whole, whereas **ipTM** specifically evaluates confidence in the interaction between the two proteins.

An ipTM around **0.5** suggests that the proposed dimer is **plausible**, but should be considered a structural hypothesis rather than definitive evidence.

This means the model is useful for generating biological hypotheses, but experimental validation would still be required.

---

# Slide 11 — Who interacts with Cph1?

After understanding the structure of Cph1 itself, the next question becomes:

> **Who receives the signal?**

The downstream partner is **Rcp1**, a response regulator.

Rcp1 accepts the phosphate transferred by Cph1 and subsequently regulates the expression of genes that allow cyanobacteria to adapt to changing environmental light conditions.

---

# Slide 12 — Transition to Manu

So far, we've shown that:

- AlphaFold accurately predicts the experimentally resolved structure of Cph1.
- The protein contains well-defined functional domains.
- Evolutionary conservation highlights the regions responsible for light sensing and signal transmission.
- AlphaFold also predicts a plausible dimeric organization for kinase activation.

With this structural foundation established, **Manu will now continue by examining how Cph1 interacts with Rcp1 and how computational methods predict chromophore binding and the complete signaling mechanism.**

---

# Key numbers to remember

- **RMSD:** **0.665 Å**
- **Experimental structure:** photosensory module only (2VEA)
- **PAS–GAF–PHY:** photosensory module
- **Histidine kinase:** signaling output
- **Central question:** *How does Cph1 convert light into a biochemical signal?*