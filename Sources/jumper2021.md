# Highly accurate protein structure prediction with AlphaFold
**Citekey:** @jumper2021
**Authors:** John Jumper, Richard Evans, Alexander Pritzel, Tim Green, Michael Figurnov, Olaf Ronneberger, Kathryn Tunyasuvunakool, Russ Bates, Augustin Žídek, Anna Potapenko, Alex Bridgland, Clemens Meyer, Simon A. A. Kohl, Andrew J. Ballard, Andrew Cowie, Bernardino Romera-Paredes, Stanislav Nikolov, Rishub Jain, Jonas Adler, Trevor Back, Stig Petersen, David Reiman, Ellen Clancy, Michal Zielinski, Martin Steinegger, Michalina Pacholska, Tamas Berghammer, Sebastian Bodenstein, David Silver, Oriol Vinyals, Andrew W. Senior, Koray Kavukcuoglu, Pushmeet Kohli, Demis Hassabis

---

## 🖍️ Annotations
%% begin annotations %%
> the structures of around 100,000 unique proteins have been determined [p. 583](zotero://open-pdf/library/items/SM9CCIET?page=583)
**Note:** Relates to Lesk: In 2001 -> 10k proteins had been resolved
**Tags:** #ResolvedStructures

> Predicting the three-dimensional structure that a protein will adopt based solely on its amino acid sequence [p. 583](zotero://open-pdf/library/items/SM9CCIET?page=583)
**Note:** That is the key objective of alphafold
**Tags:** #ProteinFoldingProblem

> Here we provide the first computational method that can regularly predict protein structures with atomic accuracy even in cases in which no similar structure is known. [p. 583](zotero://open-pdf/library/items/SM9CCIET?page=583)

> AlphaFold is a novel machine learning approach that incorporates physical and biological knowledge about protein structure, leveraging multi-sequence alignments, into the design of the deep learning algorithm. [p. 583](zotero://open-pdf/library/items/SM9CCIET?page=583)
**Tags:** #[[Deep-Learning]]

> The neural network AlphaFold [p. 583](zotero://open-pdf/library/items/SM9CCIET?page=583)

> AlphaFold structures had a median backbone accuracy of 0.96 Å r.m.s.d.95 (Cα root-mean-square deviation at 95% residue coverage) (95% confidence interval = 0.85–1.16 Å) whereas the next best performing method had a median backbone accuracy of 2.8 Å r.m.s.d.95 (95% confidence interval = 2.7–4.0 Å) [p. 584](zotero://open-pdf/library/items/SM9CCIET?page=584)
**Note:** What does this mean?To understand why it’s rigorous, we have to look at how protein structures are usually measured. Normally, $RMSD$ (Root-Mean-Square Deviation) measures the average distance between the predicted atoms and the actual atoms. The lower the number, the more accurate the prediction. The "$95$" in $RMSD_{95}$ means AlphaFold is being evaluated on <b>95% of the residues</b>.

> As a comparison point for this accuracy, the width of a carbon atom is approximately 1.4 Å. [p. 584](zotero://open-pdf/library/items/SM9CCIET?page=584)

> AlphaFold is able to produce highly accurate side chains (Fig. 1c) [p. 584](zotero://open-pdf/library/items/SM9CCIET?page=584)
**Note:** A backbone (the main chain) gives you the fold, but the <b>side chains</b> are what determine how a protein binds to a drug or catalyzes a reaction.<b>AlphaFold (1.5 Å all-atom):</b> This is precise enough to see how an enzyme's "teeth" are positioned.<b>Competitors (3.5 Å all-atom):</b> At this level of error, the side chains are often pointing in the wrong direction or clashing, making the model nearly useless for designing new medicines.

> scalable to very long proteins with accurate domains and domain-packing [p. 584](zotero://open-pdf/library/items/SM9CCIET?page=584)
**Note:** AlphaFold proved its architecture is <b>scalable</b>.It can manage "domain-packing," which is the art of making sure two different parts of a giant protein aren't just accurate on their own, but are sitting correctly against each other.

> Finally, the model is able to provide precise, per-residue estimates of its reliability that should enable the confident use of these predictions. [p. 584](zotero://open-pdf/library/items/SM9CCIET?page=584)
**Note:** Per-Residue Reliability (pLDDT)The paper mentions "precise estimates of reliability." This is the <b>[[The predicted local distance difference test]] score</b> (predicted Local Distance Difference Test). Instead of just giving you a structure and saying "trust me," AlphaFold colors the model:<b>Blue (>90):</b> High confidence. You can treat this like an experimental structure.<b>Yellow/Orange (<50):</b> Low confidence. This often suggests the protein is "intrinsically disordered"—meaning it doesn't have a fixed shape in nature until it binds to something else.<b>Why this matters:</b> It prevented scientists from wasting years trying to study "errors" that were actually just flexible parts of the protein.
**Tags:** #[[The predicted local distance difference test]]


%% end annotations %%
---
## 🏷️ Item Tags
#[[AlphaFold]]


%% Import Date: 2026-02-26T17:46:10.744+02:00 %%
