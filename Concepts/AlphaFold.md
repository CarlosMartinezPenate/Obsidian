 [[AlphaFold]] is a novel machine learning approach that incorporates physical and biological knowledge about protein structure, leveraging multi-sequence alignments, into the design of the deep learning algorithm [[jumper2021]]

It is a neural network whose key objective is to predict the three-dimensional structure that a protein will adopt based solely on its amino acid sequence, with high accuracy[[jumper2021]]

AlphaFold structures had a median backbone #accuracy of 0.96 Å r.m.s.d.95 ([[Cα root-mean-square deviation at 95% residue coverage]]) (95% confidence interval = 0.85–1.16 Å) whereas the next best performing method had a median backbone accuracy of 2.8 Å r.m.s.d.95 (95% confidence interval = 2.7–4.0 Å)

There are two classes of reasons why AlphaFold2 will assign a low #confidence to a region of a protein.  It may be that that region is naturally highly flexible or intrinsically disordered, in which case it does not have any well-defined structure. Alternatively, the region may have a predictable structure but AlphaFold2 does not have enough information to predict it with confidence. Both scenarios will typically give rise to a [[pLDDT]] (pLDDT) of 50. 

