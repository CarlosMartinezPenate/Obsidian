---
author: Carlos Alberto Martínez
bibliography: Technion_Era.bib
date: 2026-09-20
institution: Technion -- Israel Institute of Technology
status: Scientific working draft 3.3
supervisor: Prof. Dvir Harris
title: Research Proposal --- Working Draft 3.3
---

# Working title

**Regulated Molecular States of Photosynthetic Antennae: Acclimatory Remodeling of Dinoflagellate acpPC and Controlled Disassembly of the _Acaryochloris marina_ Phycobilisome**

> **Title status:** Working title. Final title to be fixed at submission.

# Abstract

Photosynthetic antennae are usually described by their structures, but their biological function depends on transitions between molecular states. Cryo-EM has recently delivered high-resolution architectures for both antenna systems studied here, yet the transitions that connect those architectures to acclimation and regulated degradation remain incompletely resolved. This proposal treats two evolutionarily independent antenna systems as tractable models of the same general problem: the membrane-associated peridinin--chlorophyll _a/c_-binding complexes (acpPC) of Symbiodiniaceae dinoflagellates, and the phycobilisome (PBS) degradation machinery of _Acaryochloris marina_ MBIC11017.

In Symbiodiniaceae, peridinin-containing antenna systems broaden light harvesting in the marine environment and are physiologically regulated during photoacclimation. In _A. marina_, a horizontally reacquired phycocyanin antenna contributes to light harvesting in spectral regions poorly covered by chlorophyll _d_, and genes involved in both assembly and disassembly of this system were reacquired by horizontal transfer [@ulrich2024; @miller2021]. These systems are not proposed to share an evolutionary or molecular mechanism. Instead, each provides an experimentally tractable context in which a pigment--protein antenna changes molecular state in response to physiological demands.

The dinoflagellate arm uses five Symbiodiniaceae strains derived from the Xiang collection [@xiang2013]: _Symbiodinium linucheae_ SSA01, _S. necroappetens_ SSA02, _S. pilosum_ SSA03, _Breviolum minutum_ SSB01 and _Effrenium voratum_ SSE01. All five are established in culture, with current S3 cultures at approximately 3 L in 5-L Erlenmeyer flasks and whole-culture absorption and fluorescence measurements available. The work will first define baseline biochemical states of membrane-associated acpPC antennae and establish the biomass and isolation requirements for their reproducible characterization. It will then test whether chronic irradiance acclimation produces reproducible changes in acpPC organization, pigment environment and excitation-energy-transfer behavior. Physiological screening will be separated from biochemical production: larger production cultures will be generated only for selected strain × condition contrasts after Aim 1 establishes biomass requirements. Approximately 8-L cultures in transparent rectangular ~9-L vessels are being considered for production, but final working volume and production-cycle duration are currently **N/A**.

Whole-genome sequencing (WGS) is incorporated as an enabling component rather than a separate thesis aim. The minimum objective is to generate strain-specific sequence resources capable of improving acpPC identification by proteomics. Raw FASTQ reads supplied by the sequencing service will require quality control, taxonomic screening/decontamination where necessary, genome assembly, gene prediction and annotation before a predicted protein FASTA can be produced for use as a custom LC-MS/MS search database. Because dinoflagellate genomes are large, divergent and structurally unusual, successful sequencing will not be equated with a high-quality predicted proteome. RNA-seq may be added if required to improve gene models or to address a specific expression-level hypothesis, but it is not currently a committed experiment.

The cyanobacterial arm is explicitly a **cell-free mechanistic reconstitution** using native AmPBS isolated from _A. marina_ MBIC11017 together with recombinant overexpressed AmNblA and recombinant overexpressed AmNblB. Published work establishes NblA as a phycobiliprotein-binding Clp adaptor and implicates NblB in PBP/bilin remodeling in an NblA-dependent manner, yet no direct NblA--NblB interaction was detected in the heterologous system in which it was tested [@baier2014; @levi2018; @hu2020]. The Harris laboratory has native AmPBS and recombinant AmNblA and AmNblB available, together with previous evidence that NblA identity can encode substrate selectivity. The proposed reconstruction will test whether recombinant AmNblA is sufficient to generate reproducible molecular states from native AmPBS, how recombinant AmNblB responds to those states, what structural features underlie AmNblB activity, and what happens to the phycocyanobilin chromophore. Because recombinant overexpressed proteins may differ from their endogenous molecular states, their activity on native AmPBS will be validated experimentally. Results from the purified reconstruction will establish biochemical sufficiency under defined conditions, not automatically the complete _in vivo_ degradation mechanism.

The unifying question is whether antenna behavior can be understood through regulated transitions between experimentally distinguishable pigment--protein molecular states, and how those transitions modify light harvesting or facilitate controlled antenna disassembly.

# 1. Scientific background and rationale

## 1.1 Photosynthetic antennae as dynamic molecular systems

Photosynthetic antenna systems extend the spectral and spatial cross-section for photon capture and direct excitation energy toward reaction centers. Their performance depends on the organization of pigments within protein scaffolds, the association of antenna proteins into higher-order complexes, and the energetic coupling among chromophores. Antenna architecture is therefore not merely structural: changes in protein composition, oligomerization, pigment occupancy, chromophore environment, or interaction with reaction centers can alter excitation-energy transfer, quenching, and photoprotection.

The central premise of this proposal is that antennae should be studied as **dynamic molecular systems**. Two forms of remodeling are particularly informative. First, long-term acclimation to irradiance can alter antenna abundance and composition while photosynthetic cells remain viable and functional. Second, nutrient or environmental stress can trigger controlled disassembly and recycling of antenna material. These processes occur in evolutionarily and structurally distinct systems, but both can be investigated by defining an initial molecular state, imposing a biologically meaningful perturbation, identifying reproducible remodeled states, and determining their functional consequences.

This proposal therefore investigates two complementary systems:

1. **Symbiodiniaceae acpPC-containing membrane antennae**, in which chronic irradiance acclimation provides a route to study adaptive remodeling of pigment--protein organization.
2. **_Acaryochloris marina_ phycobilisomes**, in which cell-free reconstruction with native AmPBS and recombinant AmNblA/AmNblB provides a route to study controlled antenna disassembly and pigment remodeling.

The proposal does **not** assume that these systems share a homologous molecular mechanism. Their connection is conceptual and experimental:

- **Biological.** Both are regulated accessory light-harvesting systems whose organization changes in response to physiological demands.
- **Analytical.** Both are investigated by defining molecular states with complementary biochemical, compositional and spectroscopic measurements.
- **Conceptual.** Both ask whether transitions between defined molecular states provide a more informative explanation of antenna behavior than static architecture alone.

The exact measurement stack need not be identical between the two arms. In particular, methods appropriate for soluble AmPBS assemblies cannot automatically be assumed to transfer to detergent-solubilized membrane antenna complexes.

## 1.2 Symbiodiniaceae light harvesting

Symbiodiniaceae possess unusual photosynthetic antenna systems adapted to marine light environments. Their major light-harvesting pigments include chlorophyll _a_, chlorophyll _c_$_2$, and the carotenoid peridinin. Peridinin-containing antennae occur in at least two major biochemical contexts: soluble peridinin--chlorophyll _a_ protein (PCP) and membrane-associated chlorophyll _a/c_$_2$--peridinin protein complexes (acpPC). PCP has been extensively characterized spectroscopically and structurally, whereas membrane acpPC complexes remain less completely understood in native and acclimation-dependent states [@jiang2012a; @carbonera2014; @jovine1995].

Cryo-EM has substantially advanced structural understanding of dinoflagellate membrane antenna organization. A 2.8 Å structure of a _Symbiodinium_ PSI--AcpPCI supercomplex resolved 13 AcpPCI proteins surrounding a 13-subunit PSI core and mapped predicted energy-transfer routes [@zhao2024]. In parallel, PSI--AcpPCI structures from two dinoflagellates were resolved at 2.70--2.99 Å, including a complex containing 17 assigned AcpPCI subunits [@zhou2024]. Earlier biochemical work demonstrated membrane-bound light-harvesting complexes in dinoflagellates and provided precedents for detergent-based isolation [@jovine1995]. Thus, basic acpPC architecture can no longer be treated as broadly unknown. The unresolved problem is how native acpPC-containing molecular states change with physiological acclimation.

Two features make this system biochemically demanding. First, acpPC proteins are encoded by a diverse multigene family, including polyprotein precursors, making subunit-level identification dependent on adequate sequence resources [@boldt2012]. Second, purification can alter assembly state. Isolation conditions are therefore part of the biological measurement rather than a neutral preliminary step.

Light acclimation provides the primary physiological perturbation. Classical work showed that Symbiodiniaceae alter photosynthetic-unit properties, pigments and chlorophyll--protein complexes in response to photon flux, with substantial species dependence [@iglesiasprieto1997]. High-light studies further indicate that membrane antenna components, including acpPC-associated excitation, participate in non-photochemical quenching [@kanazawa2014]. These findings establish irradiance responsiveness but do not resolve the molecular bridge between chronic acclimation and the biochemical state of native acpPC-containing antennae.

### Knowledge gap 1

> **Does chronic irradiance acclimation produce reproducible changes in the biochemical organization of native membrane-associated acpPC antennae across Symbiodiniaceae; which molecular variables account for those changes; and do the resulting states alter pigment energetics and excitation-energy-transfer behavior?**

The proposal deliberately does not assume that acclimation must change acpPC oligomerization, pigment stoichiometry, subunit composition, photosystem association, or chromophore geometry. These are candidate and potentially non-exclusive mechanisms.

The five-strain panel additionally permits testing whether remodeling responses are shared or strain dependent. It does not, by itself, provide sufficient sampling to establish an evolutionary mechanism.

## 1.3 Genomic resources as an enabling layer for acpPC biochemistry

Subunit-resolved acpPC proteomics depends on an appropriate protein-sequence search space. This is nontrivial in Symbiodiniaceae because available reference genomes and transcriptomes vary substantially among taxa and strains, while acpPC belongs to a diverse multigene family [@boldt2012].

Comparative Symbiodiniaceae genomics demonstrates both the feasibility and the difficulty of generating useful predicted proteomes. Published genome projects have used combinations of genomic sequence, de novo and genome-guided RNA-seq assemblies, full-length transcript evidence, homology and multiple gene-prediction algorithms to construct evidence-supported gene models. Dinoflagellate genome architecture is unusual, and even high-quality genomic sequence does not automatically yield reliable gene annotation. Consequently, the sequence-resource component of this proposal is designed around its biological purpose rather than around production of reference-grade genomes.

The intended enabling workflow is:

\[
\text{strain culture}
\rightarrow
\text{DNA extraction}
\rightarrow
\text{WGS}
\rightarrow
\text{FASTQ}
\rightarrow
\text{read QC and taxonomic screening/decontamination}
\rightarrow
\text{genome assembly}
\rightarrow
\text{gene prediction/annotation}
\rightarrow
\text{predicted protein FASTA}
\rightarrow
\text{custom LC-MS/MS database}
\rightarrow
\text{acpPC identification}
\]

The Technion sequencing service has offered generation of FASTQ sequence files. **FASTQ files are raw sequencing reads and are not the protein FASTA required for proteomic database searching.** Assembly, gene prediction and translation of predicted coding sequences are separate analytical steps.

Axenicity is not treated as a prerequisite for this workflow. Instead, sequence datasets will be subjected to appropriate taxonomic QC so that non-Symbiodiniaceae sequence can be identified and excluded where required. The effectiveness of such filtering will depend on the sequencing data and assembly quality and therefore should not be assumed in advance.

The minimum objective is **a strain-specific sequence resource sufficiently informative for proteomic identification and acpPC-family analysis**, not chromosome-level genome reconstruction. Sequencing platform, depth/coverage, assembly strategy/service, annotation strategy and cost are currently **N/A**.

Published Symbiodiniaceae genome studies also indicate that transcript evidence can materially improve gene prediction. RNA-seq is therefore retained as a possible complementary strategy if WGS-only annotation is inadequate or if a later mechanistic question requires transcriptional information. It is not presently a committed thesis experiment.

If justified, the resulting hierarchy could ultimately connect:

\[
\text{genome repertoire}
\rightarrow
\text{transcription}
\rightarrow
\text{protein composition}
\rightarrow
\text{native complex}
\rightarrow
\text{photophysics}
\]

However, only the genome/protein-resource and protein/native-complex levels are presently required by the core proposal. Expansion into transcriptomics will require an explicit scientific justification and feasibility/cost assessment.

## 1.4 The _Acaryochloris marina_ phycobilisome

Phycobilisomes are large bilin-containing antenna complexes found in cyanobacteria and red algae [@adir2020]. Their modular architecture permits substantial remodeling in response to nutrient availability and environmental conditions.

_A. marina_ MBIC11017 is an informative host for studying this process. The lineage lost phycobiliprotein genes ancestrally, whereas MBIC11017 reacquired a phycocyanin system by horizontal gene transfer, including genes associated with its assembly and disassembly, which subsequently became integrated into an ancestral regulatory network [@miller2021; @ulrich2024]. The reacquired phycocyanin antenna expands the spectral range available to the chlorophyll-_d_-dominated photosynthetic system [@miller2021].

The AmPBS is a compact antenna assembled predominantly from phycocyanin and associated linker proteins, with red-shifted fluorescence and multiple PC isoforms suited to the chlorophyll-_d_ context. Recent physiological and spectroscopic work further indicates that MBIC11017 adjusts PBS abundance and photosystem stoichiometry under different light qualities while retaining strong PBS-to-PSII excitation transfer [@viola2025]. These properties make native AmPBS a well-characterized and experimentally accessible substrate for mechanistic reconstruction of antenna disassembly.

## 1.5 NblA, NblB, and controlled PBS degradation

During nitrogen starvation and other stresses, cyanobacteria degrade PBSs and recycle their nitrogen-rich phycobiliproteins. NblA is a small protein central to this process. Structural, biochemical and genetic work established that NblA binds phycobiliproteins and can act as an adaptor connecting PBS substrates to ATP-dependent Clp proteolysis [@baier2014]. NblA proteins can also exhibit substrate specificity, indicating that PBS degradation need not be a nonspecific collapse of the antenna. Recent cyanophage-NblA work further supports positionally ordered disassembly and provides a methodological precedent for mapping degradation states by proteomic analysis [@zborovsky2025].

NblB is related to bilin-lyase proteins and is also required for normal PBS degradation. Levi and colleagues implicated NblB in degradation of both PC and APC and provided cell-free evidence for involvement in pigment remodeling, with NblB activity dependent on NblA [@levi2018]. Hu and colleagues subsequently showed that the reaction network is more complex: NblA and NblB can influence PBS/PBP dissociation, interact with apo- and holo-PBPs and bilin lyases, and modulate chromophore attachment, detachment and transfer. That study did not detect direct NblA--NblB interaction [@hu2020].

Additional factors, including NblD, demonstrate that PBS degradation is a multi-component process rather than a simple NblA→NblB→protease pathway [@krauspe2021; @krauspe2022]. The present proposal therefore asks what can be reconstructed from a defined minimal biochemical system without claiming that the reconstruction contains the complete cellular pathway.

### Knowledge gap 2

> **How does AmNblA alter the molecular state of native AmPBS, and how does that state determine the recruitment and/or activity of AmNblB?**

Three aspects are particularly unresolved:

- the molecular state of the PBS/PBP substrate recognized by AmNblB;
- the structural determinants by which AmNblB recognizes and remodels that substrate;
- whether apparent NblA dependence arises from substrate-state remodeling, direct association, simultaneous substrate-mediated cooperation, or requirements for additional components.

The experimental system used here is specifically:

\[
\text{native AmPBS}
+
\text{recombinant AmNblA}
+
\text{recombinant AmNblB}
\rightarrow
\text{cell-free mechanistic reconstitution}
\]

Neither AmNblA nor AmNblB in this reconstruction is a purified native protein.

# 2. Overall research objective

The overall objective is to determine how photosynthetic antenna complexes reorganize in response to physiological or degradation-associated perturbations by resolving experimentally distinguishable molecular states in two complementary pigment--protein systems.

Four linked objectives are pursued:

1. **Define and compare the baseline biochemical organization of membrane-associated acpPC antennae across five Symbiodiniaceae strains.**
2. **Determine how chronic irradiance acclimation remodels acpPC organization and associated photophysical behavior.**
3. **Determine whether recombinant AmNblA is sufficient to generate reproducible molecular states from native AmPBS in a defined cell-free system.**
4. **Determine how recombinant AmNblB recognizes and remodels native AmPBS-derived substrate states and establish the structural basis of its activity.**

WGS, culture scale-up, microbial-contamination monitoring and potential RNA-seq are enabling or quality-control components of Chapters I--II and are not separate thesis aims.

# 3. Central hypotheses

## 3.1 Dinoflagellate hypothesis

> **Chronic irradiance acclimation generates reproducible, strain-dependent changes in the molecular composition and/or organization of native membrane-associated acpPC antennae. A subset of these changes alters the energetic environment of bound pigments and thereby modifies excitation-energy-transfer or quenching behavior.**

This formulation does not assume a priori that the dominant remodeling variable is subunit composition, pigment occupancy, xanthophyll composition, oligomerization, photosystem association, higher-order organization, or local pigment environment.

## 3.2 Cyanobacterial hypothesis

> **Recombinant AmNblA is sufficient, under defined cell-free conditions, to generate or enrich native AmPBS-derived substrate states with altered susceptibility to recombinant AmNblB, while the lyase-related architecture of AmNblB enables recognition and remodeling of chromophorylated PBPs in those states.**

The hypothesis is stated as a substrate-state coupling model, but competing mechanisms remain explicit:

- **Sequential substrate remodeling:** recombinant AmNblA generates a state subsequently preferred by recombinant AmNblB.
- **Direct association:** recombinant AmNblA and recombinant AmNblB form a detectable complex.
- **Simultaneous/substrate-mediated cooperation:** the proteins cooperate through a transient PBP-associated assembly.
- **Parallel activity:** AmNblA and AmNblB remodel different properties of the PBS with limited mechanistic dependence in the purified system.
- **Extended system:** full remodeling requires additional factors such as bilin lyases, proteases or other degradation proteins.

Because both remodeling factors are heterologously overexpressed recombinant proteins, successful reconstitution will demonstrate **biochemical sufficiency under the tested conditions**, not by itself prove the complete endogenous pathway.

## 3.3 Operational definition of "reproducible"

Because "reproducible molecular state" is load-bearing throughout, it is defined once here and used consistently.

A remodeled state is treated as **reproducible** when the difference from the reference state:

1. is observed in at least three independent biological preparations;
2. exceeds the pooled within-condition variation of the corresponding control by a pre-specified margin; and
3. is detected by at least two orthogonal readouts, for example a change in molecular/assembly distribution together with a spectral or compositional change.

Effect-size thresholds for individual readouts will be fixed after the variance-estimation experiments in Aims 1 and 3 and recorded before the corresponding comparative datasets are collected.

For the dinoflagellate experiments, the biological experimental unit is the independently maintained culture, not individual cells measured by flow cytometry. Large numbers of cytometric events therefore increase measurement precision but do not substitute for independent biological replicates.

# 4. Research systems and preliminary data

## 4.1 Symbiodiniaceae strains and culture architecture

Five strains derived from the Xiang collection and supplied by Prof. Tingting Xiang (University of California, Riverside) are maintained in culture:

| Strain | Species |
|:--|:--|
| SSA01 | _Symbiodinium linucheae_ |
| SSA02 | _Symbiodinium necroappetens_ |
| SSA03 | _Symbiodinium pilosum_ |
| SSB01 | _Breviolum minutum_ |
| SSE01 | _Effrenium voratum_ |

The originating collection was developed as clonal axenic material [@xiang2013]. The present proposal does **not** treat maintenance of axenicity as a prerequisite for its principal biochemical objectives. The experimental endpoints are isolated and characterized Symbiodiniaceae membrane pigment--protein fractions rather than characterization of the intact culture microbiome.

Culture-associated microorganisms remain a potential analytical consideration where they could affect interpretation, particularly during WGS and proteomic analysis. They will therefore be addressed at the relevant analytical stage rather than used as a routine exclusion criterion for the cultures.

Selective plating, including the currently available KAN-plate assay, can be used as a diagnostic/fallback control when bacterial proliferation or contamination is suspected. Absence of growth on these plates will not, by itself, be interpreted as proof of axenicity because the assay detects only organisms capable of growing under the particular plating conditions.

The working culture architecture is:

\[
\text{strain-controlled culture bank}
\rightarrow
\text{liquid master}
\rightarrow
\text{replicated experimental cultures}
\rightarrow
\text{selected seed culture}
\rightarrow
\text{production-scale culture}
\rightarrow
\text{biochemical harvest}
\]

This architecture separates **physiological replication** from **biochemical biomass production**. Independent experimental cultures are used to establish biological responses. Production-scale cultures are generated only after strain × condition contrasts have been selected and sufficient biomass is required for biochemical isolation.

Current S3 cultures are approximately 3 L in 5-L Erlenmeyer flasks. Approximately 8-L production cultures in transparent rectangular ~9-L vessels are being considered as a practical biomass-production format. This scale is **not yet validated**. The biomass required per acpPC preparation, final production working volume and production-cycle duration are all currently **N/A** and will be established empirically in Aim 1.

### Preliminary observations

- All five strains have been established and maintained in culture.
- Current S3 cultures are approximately 3 L.
- Growth and culture development have been followed using OD$_{750}$ together with visual and microscopic observations.
- Whole-culture absorption and fluorescence spectra have been obtained.
- Direct isolation of thylakoids, membrane antenna fractions or acpPC-enriched complexes has **not yet been demonstrated** and is an early experimental milestone.

**Figure 1. [TO BE INSERTED]** Whole-culture absorption and fluorescence spectra of SSA01, SSA02, SSA03, SSB01 and SSE01.

### Interpretation of whole-cell optical measurements

Whole-cell UV--Vis spectra are treated as intact-cell optical phenotypes, not as purified pigment spectra. The measured signal contains:

\[
\text{pigment absorption}
+
\text{wavelength-dependent scattering}
+
\text{effects of concentration, morphology and aggregation}.
\]

Consequently, spectral components will not be assigned directly to acpPC without biochemical fractionation.

Similarly, OD$_{750}$ is an operational culture measurement rather than an automatic measure of biomass. Its relationship to cell concentration or dry biomass must be calibrated if it is to be used quantitatively for production planning.

Current culture history has also shown that refill history, aggregation and evaporation can affect optical phenotypes. Culture-history variables will therefore be controlled and recorded in comparative acclimation experiments rather than treated as negligible technical detail.

### Microbial-contamination QC

Routine proof of axenicity is not required for Chapters I--II.

Instead, microbial contamination will be investigated when it becomes relevant to interpretation. Available approaches include:

- KAN plating as a diagnostic/fallback assay for detectable cultivable contamination under the established conditions;
- microscopic inspection where informative;
- taxonomic screening of WGS reads and assembled contigs;
- proteomic filtering where non-Symbiodiniaceae proteins materially affect interpretation.

The objective is therefore **analytical control of relevant contamination**, not maintenance of axenicity as a thesis endpoint.

## 4.2 Sequence resources and WGS enabling strategy

Subunit-level identification of acpPC by LC-MS/MS requires an appropriate protein-sequence reference. Published genome/transcriptome coverage differs among the five strains, while the acpPC family is large, divergent and includes polyprotein precursors [@boldt2012].

Whole-genome sequencing of the five experimental strains is therefore being considered as an enabling component of Chapters I--II.

The intended workflow is:

\[
\text{strain culture}
\rightarrow
\text{DNA extraction}
\rightarrow
\text{WGS}
\rightarrow
\text{FASTQ}
\rightarrow
\text{read QC and taxonomic screening/decontamination}
\rightarrow
\text{genome assembly}
\rightarrow
\text{gene prediction/annotation}
\rightarrow
\text{predicted protein FASTA}
\rightarrow
\text{custom LC-MS/MS database}.
\]

The Technion sequencing service has offered delivery of FASTQ files. These files contain raw sequence reads; they are **not** directly usable as a protein search database.

Axenic starting cultures are not required for the WGS component, but culture-associated microbial DNA may be sequenced together with Symbiodiniaceae DNA. Read-level and/or assembly-level taxonomic screening will therefore be incorporated before strain-specific protein databases are generated.

The degree to which microbial sequence can be separated reliably will depend on read properties, assembly quality and available reference information. Taxonomic decontamination will therefore be documented rather than assumed to be complete.

Published Symbiodiniaceae genome studies demonstrate that genome assembly and gene prediction are feasible but nontrivial. Dinoflagellate genomes are structurally unusual and can be large, repetitive and highly divergent. Published annotation workflows have used direct transcript evidence together with multiple ab initio and homology-based predictors rather than assuming that genomic sequence alone yields reliable coding sequences.

Accordingly:

- sequencing platform = **N/A**;
- sequencing depth/coverage = **N/A**;
- assembly strategy/service = **N/A**;
- annotation strategy/service = **N/A**;
- predicted proteome generation = **N/A**;
- expected assembly quality = **N/A**;
- chromosome-level assembly is **not an objective**.

The minimum deliverable is a strain-specific sequence resource sufficiently informative to improve proteomic assignment of acpPC-family proteins.

Where WGS-derived annotation is incomplete, published genomes, transcriptomes and experimentally characterized AcpPC sequences will remain available for homology-supported assignment. Such identifications will be reported at the level supported by the data rather than forcing subunit-level calls.

Strain-specific predicted protein FASTAs will, if technically acceptable, be supplied as custom LC-MS/MS search databases to the Technion Proteomics Center. The center is available, but its exact requirements for database formatting, contaminant sequences, decoy generation, search-space size and downstream reporting remain **N/A/to confirm**.

The resulting genome resources may additionally permit comparative analysis of the acpPC gene repertoire across _Symbiodinium_, _Breviolum_ and _Effrenium_. Such analysis would support interpretation of protein-composition differences but remains subordinate to the biochemical aims.

### Conditional RNA-seq component

RNA-seq is **not currently a committed experiment**.

It may become justified if:

1. WGS-only gene prediction proves insufficient for construction of useful strain-specific predicted proteomes; or
2. a specific result from Chapter II requires testing whether irradiance-dependent changes in protein composition are associated with transcriptional regulation.

In that case, RNA-seq could provide transcript evidence for gene models and potentially support the hierarchy:

\[
\text{genome repertoire}
\rightarrow
\text{transcription}
\rightarrow
\text{protein composition}
\rightarrow
\text{native complex}
\rightarrow
\text{photophysics}.
\]

RNA-seq necessity, design, replication and cost are currently **N/A**. It will not be added solely because transcriptomic data would be generally informative.

## 4.3 Cyanobacterial preliminary system: cell-free reconstruction

The cyanobacterial arm uses a defined combination of:

- **native AmPBS isolated from _A. marina_ MBIC11017;**
- **recombinant overexpressed AmNblA;**
- **recombinant overexpressed AmNblB.**

The core experimental concept is:

\[
\text{native AmPBS}
+
\text{recombinant AmNblA}
+
\text{recombinant AmNblB}
\rightarrow
\text{mechanistic cell-free reconstitution}.
\]

Preliminary and unpublished Harris-laboratory work provides the experimental starting point. Native AmPBS is available, and recombinant AmNblA and AmNblB have been expressed and purified.

Previous work in the laboratory (M. [surname], MSc thesis, Technion, [year] --- formal citation to be inserted) demonstrated that different NblA proteins can produce different PBS-disassembly phenotypes and PBP-interaction profiles. NblA1 showed broad PBP association and extensive disassembly, whereas NblA2 was biased toward peripheral phycoerythrin-containing regions in the marine system examined. This provides preliminary evidence that NblA identity can encode substrate selectivity and extent of remodeling. The molecular basis of AmNblA specificity remains unresolved.

Recombinant AmNblB crystallization has produced crystals in the laboratory. Diffraction, dataset and refinement status remain **N/A** and no experimental structure is assumed in this proposal.

### Limitation of the reconstruction

Recombinant AmNblA and AmNblB are heterologously overexpressed proteins and may differ from their endogenous molecular states in folding, oligomerization, modifications, bound cofactors or associated partners. Purity and apparent folding alone therefore do not establish biological activity.

Activity must be validated against native AmPBS using appropriate biochemical controls. Conversely, failure of a recombinant protein to reproduce an _in vivo_ phenotype cannot immediately be interpreted as evidence that the corresponding endogenous protein lacks that activity.

The reconstruction is designed to establish what molecular transformations are **biochemically sufficient under defined conditions**. Extension of those results to the complete cellular degradation pathway will require appropriate qualification and, where necessary, additional factors or _in vivo_ validation.

# 5. Research plan

## Chapter I --- Comparative biochemical organization of Symbiodiniaceae membrane antennae

### Aim 1. Define the baseline biochemical organization and diversity of acpPC-containing membrane antennae across five Symbiodiniaceae strains

#### Rationale

High-resolution structures show that AcpPC proteins form extensive membrane-associated antenna systems around dinoflagellate photosystems [@zhao2024; @zhou2024]. Biochemical work further establishes that large native PSI--LHC assemblies can be isolated from Symbiodiniaceae. However, comparable biochemical characterization across the five available strains is lacking.

The scientific objective of this chapter is therefore not merely to develop an isolation protocol. It is to determine whether the five strains possess distinguishable baseline acpPC-containing molecular phenotypes under a common reference condition. Method development, biomass production and sequence-resource generation are enabling steps required to make that comparison.

Routine maintenance of axenic cultures is not required for this objective because the endpoint is a biochemically isolated Symbiodiniaceae pigment--protein fraction. Potential microbial contributions will instead be evaluated where they could compromise sequence, proteomic or biochemical interpretation.

#### Culture and biomass strategy

Aim 1 will first establish how much biological material is required to obtain a reproducible acpPC-containing preparation.

The culture hierarchy will be maintained as:

\[
\text{strain-controlled culture bank}
\rightarrow
\text{liquid master}
\rightarrow
\text{experimental replicate}
\rightarrow
\text{selected seed}
\rightarrow
\text{production culture}
\rightarrow
\text{harvest}.
\]

Current ~3-L S3 cultures provide material for method development. Approximately 8-L production cultures are being considered, but the required working volume will be calculated from measured recovery through the isolation workflow rather than fixed in advance.

A biomass/yield accounting chain will be established:

\[
\text{culture volume}
\rightarrow
\text{cell number/biomass}
\rightarrow
\text{membrane yield}
\rightarrow
\text{solubilized pigment--protein yield}
\rightarrow
\text{acpPC-containing fraction yield}.
\]

Biomass required per preparation and production-cycle duration are currently **N/A**.

Large cultures are therefore a **production step for selected material**, not the experimental unit and not a substitute for replicated physiological cultures.

#### Experimental strategy

The biochemical workflow will be developed in the order in which it can fail:

1. **Cell disruption.** Mechanical disruption approaches will be compared, with efficiency assessed microscopically and by recovery of cellular pigment/protein material before downstream optimization.
2. **Membrane/thylakoid enrichment**, using differential and, where useful, density-gradient centrifugation.
3. **Mild detergent solubilization**, informed by published dinoflagellate membrane-complex and PSI--antenna purification [@jovine1995; @kato2020; @zhao2024].
4. **Separation of major pigment--protein populations**, using approaches such as density gradients, native electrophoresis and chromatography.
5. **Identification of acpPC-containing fractions** using complementary biochemical, proteomic, pigment and spectroscopic evidence.

Sucrose-density separation, native electrophoresis, SDS-PAGE, absorption/fluorescence spectroscopy, HPLC pigment analysis, proteomics and ÄKTA/FPLC are candidate tools. Their exact order and conditions will be determined empirically.

Mass photometry may be evaluated for sufficiently large, compatible acpPC-containing particles, but compatibility with detergent-solubilized membrane complexes is not assumed and mass photometry is not required for Chapter I success.

#### Sequence-supported proteomics

Where available, strain-specific predicted protein FASTAs derived from the WGS enabling workflow will be used as custom LC-MS/MS search databases.

This provides the intended analytical connection:

\[
\text{strain genome}
\rightarrow
\text{predicted protein search space}
\rightarrow
\text{LC-MS/MS peptide assignments}
\rightarrow
\text{acpPC-family composition}.
\]

If annotation quality is insufficient, published Symbiodiniaceae proteomes/transcriptomes and characterized acpPC sequences will provide a fallback search space. Identification confidence and resolution will be stated explicitly.

Where culture-associated microbial sequences or proteins are detected, they will be filtered or reported according to their relevance to the biochemical fraction. Their presence alone will not invalidate the experiment.

#### Internal control

Soluble PCP is recoverable from the same biological material and has well-characterized spectroscopic properties. Where experimentally practical, PCP recovery will provide a positive control for parts of the extraction, pigment-analysis and spectroscopy pipeline. Successful PCP recovery will not, however, demonstrate successful membrane extraction because the biochemical behavior of soluble PCP and membrane-associated acpPC differs fundamentally.

#### Identification criteria

A fraction will not be designated "acpPC" on the basis of color, absorption or fluorescence alone.

Identification will combine, where feasible:

- protein composition by LC-MS/MS;
- pigment composition;
- spectral properties;
- apparent molecular/assembly state;
- membrane/fractionation behavior;
- comparison with published acpPC and PSI--AcpPCI information.

#### Expected outcome

The primary outcome will be a comparative molecular phenotype for each strain, integrating membrane pigment--protein fraction distributions, protein composition, pigment composition, spectroscopy and apparent assembly state.

A second outcome will be quantitative information on biomass and recovery sufficient to design production cultures for Chapter II.

#### Alternative outcomes

If intact acpPC-containing complexes cannot be maintained during isolation, failure of extraction will be distinguished from biological absence by varying disruption, membrane preparation, detergent conditions, ionic strength and separation strategy.

If photosystem-bound and free antenna populations cannot be separated cleanly, an acpPC-enriched membrane fraction will be retained as the comparative unit rather than forcing purification to homogeneity.

If strain-specific WGS does not yield annotation adequate for subunit-resolved proteomics, family-level identification using published sequence resources will remain acceptable, with the corresponding resolution limitation stated explicitly.

If unexpected microbial material complicates WGS or proteomic interpretation, diagnostic KAN plating and sequence/proteomic taxonomic filtering are available as troubleshooting approaches. Routine conversion of the cultures to a demonstrably axenic state is not required unless evidence shows that microbial contamination materially prevents interpretation of a specific experiment.

#### Decision criterion for Chapter II

A strain/condition advances to detailed biochemical comparison when an acpPC-containing preparation can be generated from at least three independent biological preparations and compared using at least two orthogonal readouts according to §3.3.

The biomass requirement and production-scale working volume must also be sufficiently defined before large-scale harvesting is undertaken.

## Chapter II --- Irradiance-dependent remodeling of acpPC

### Aim 2. Determine how chronic irradiance acclimation changes acpPC biochemical and photophysical states

#### Rationale

Symbiodiniaceae photoacclimation itself is established background rather than the novelty claim. Irradiance-dependent changes in photosynthetic-unit properties, pigments and chlorophyll--protein complexes have been demonstrated previously, with substantial species dependence [@iglesiasprieto1997]. Acute high-light studies further implicate membrane antennae, including acpPC-associated components, in photoprotective quenching [@kanazawa2014].

The unresolved problem is the molecular bridge between **chronic acclimation** and **native acpPC-containing antenna state**. This aim therefore asks which components of the baseline molecular phenotype established in Aim 1 are remodeled by irradiance and whether those changes predict altered antenna photophysics.

#### Experimental architecture

Physiological screening and biochemical production are separated deliberately.

For each strain:

\[
\text{controlled master}
\rightarrow
\text{independent experimental cultures}
\rightarrow
\text{irradiance treatment}
\rightarrow
\text{physiological acclimation screen}
\]

followed, only for selected contrasts, by:

\[
\text{selected acclimated seed}
\rightarrow
\text{production-scale culture}
\rightarrow
\text{biochemical harvest}
\rightarrow
\text{acpPC analysis}.
\]

This avoids generating production-scale cultures for every replicate and every treatment while preserving biological replication at the physiological-screening stage.

#### Primary perturbation: irradiance

The primary Chapter II perturbation is irradiance.

Final photon flux densities are **N/A** and will be fixed by a pilot that identifies a useful growth-permissive range across the strains. Published irradiance regimes provide context but will not be transferred directly to all five strains without validation.

A deliberate change in irradiance will be followed by a **minimum acclimation period of three weeks** before material is treated as a candidate acclimated state. Three weeks is an operational minimum, not evidence that acclimation is complete.

Biological stability must also be assessed. Candidate indicators include:

- stability of growth/cell-density trajectory;
- stability of selected whole-cell optical properties;
- stability of flow-cytometric phenotype;
- absence of progressive stress or culture collapse.

The final operational stability criterion remains **N/A/pilot-dependent**.

Where photoperiod or spectral recipe is deliberately changed in a future experiment, the same minimum three-week rule and biological-stability requirement will apply.

#### Replication

A minimum of three independent biological cultures per strain × irradiance condition is the provisional design for physiological screening. Final replicate number will be revisited using pilot variance and feasibility.

Large production cultures are not treated as independent biological replication unless they were independently established and maintained as such.

#### Physiological screen

Candidate readouts include:

- cell concentration where validated;
- OD$_{750}$ as a recorded optical parameter, with interpretation calibrated against cell concentration/biomass rather than assumed;
- flow-cytometric scatter and red autofluorescence;
- microscopy;
- whole-culture absorption and fluorescence spectroscopy.

Flow cytometry provides a high-throughput phenotype rather than direct evidence of acpPC molecular state.

Culture volume, refill history, evaporation, aggregation and sampling history will be recorded because these factors can influence optical measurements.

Routine axenicity testing is not required for the physiological screen. If an abnormal phenotype is accompanied by evidence suggesting bacterial proliferation, the available KAN plating assay may be used diagnostically. Such results will be interpreted as evidence concerning detectable cultivable contamination under the assay conditions, not as a binary proof of axenic/non-axenic status.

#### Selection for biochemical production

Only strain × irradiance contrasts meeting pre-defined selection criteria will proceed to production-scale biochemical analysis.

Selection will prioritize:

1. reproducibility across biological cultures;
2. a stable physiological phenotype rather than transient stress;
3. sufficient effect size to motivate molecular analysis;
4. feasibility of generating the biomass required by Aim 1.

Approximately 8-L production cultures may be used if Aim 1 yield measurements support that scale. Neither 8 L nor any specific production-cycle duration is currently assumed.

#### Biochemical analysis

Selected acclimated cultures will be processed using the Aim 1 workflow.

Comparative analysis will test candidate remodeling variables including:

- acpPC abundance;
- acpPC-family/subunit composition;
- pigment composition and occupancy;
- oligomeric or higher-order state;
- association with larger photosynthetic complexes;
- absorption and fluorescence properties;
- excitation-energy-transfer behavior.

Where strain-specific predicted protein FASTAs are available and accepted by the Proteomics Center workflow, they will be used for LC-MS/MS searches.

The working mechanistic model is:

\[
\text{chronic irradiance}
\rightarrow
\text{stable physiological acclimation}
\rightarrow
\text{change in native acpPC-containing molecular state}
\rightarrow
\text{change in pigment energetic environment}
\rightarrow
\text{change in EET/quenching phenotype}.
\]

Every arrow is testable; none is assumed.

#### Conditional spectral-quality experiments

Spectral-quality/LED-recipe experiments are secondary to the primary irradiance experiment.

They will be considered only if:

1. the irradiance experiment identifies a reproducible acpPC phenotype requiring further mechanistic separation of photon quantity from spectral composition; and
2. the spectral characteristics of the programmable light system can be adequately defined.

Exact LED channels, emission spectra and programmable recipes are currently **N/A**.

Spectral-quality experiments will therefore not become an independent thesis aim unless the irradiance results provide a specific mechanistic justification.

#### Conditional RNA-seq

RNA-seq may be introduced if protein-composition changes require discrimination between genomic repertoire and transcriptional regulation, or if transcript evidence is needed to improve strain-specific gene models.

No RNA-seq experiment is currently assumed.

#### Mechanistic follow-up and EET go/no-go

Selected contrasts will be investigated using available proteomics, pigment HPLC, chromatography and fluorescence spectroscopy, with structural methods where justified.

A direct claim about excitation-energy-transfer kinetics requires an appropriate time-resolved method such as TCSPC and/or ultrafast transient spectroscopy. Confirming access to such capability is therefore a **go/no-go item**.

If suitable access cannot be established, options in priority order are:

1. Technion collaboration;
2. external collaboration with an appropriate spectroscopy laboratory;
3. restriction of Chapter II claims to steady-state biochemical and spectral phenotypes, with altered EET retained as an untested mechanistic prediction.

The third option preserves the biochemical chapter but weakens its mechanistic reach and is therefore not the preferred outcome.

#### Falsification and alternative interpretation

The central remodeling hypothesis is weakened if validated chronic acclimation produces reproducible physiological changes but no reproducible difference in acpPC composition, organization or photophysics under validated isolation conditions.

Such a result remains informative. Acclimation could instead be dominated by changes in antenna abundance, photosystem stoichiometry, xanthophyll-cycle activity, reaction-center regulation or other cellular processes without major remodeling of intrinsic acpPC molecular state.

# Chapter III --- Generation of degradation-associated AmPBS states by recombinant AmNblA

## Aim 3. Determine whether recombinant AmNblA is sufficient to generate reproducible molecular states from native AmPBS in a cell-free reconstruction

### Rationale

NblA is established as a central PBS-degradation factor that binds PBP substrates and participates in recruitment of Clp machinery [@baier2014]. Recent phage-NblA work further demonstrates that PBS disassembly can proceed in a positionally ordered fashion [@zborovsky2025]. Preliminary Harris-laboratory work supports differential substrate/disassembly behavior among NblA proteins.

The present experiment does not use endogenous purified AmNblA. It asks whether **recombinant overexpressed AmNblA**, when added to **native AmPBS**, is sufficient to produce a reproducible molecular change in a defined cell-free system.

### Validation of recombinant AmNblA activity

Before mechanistic interpretation, recombinant AmNblA activity will be established experimentally.

Purity and apparent folding are necessary quality controls but are not sufficient evidence of biological activity. Validation will therefore require a reproducible AmNblA-dependent effect on native AmPBS and/or independently validated PBP binding under defined conditions.

If recombinant AmNblA shows no activity, protein preparation, folding/oligomeric state and assay conditions will be reassessed before concluding that AmNblA cannot remodel AmPBS.

### Operational definition of AmPBS*

AmPBS* is defined as a **reproducible recombinant-AmNblA-dependent change, according to §3.3, in the molecular and/or spectroscopic state of native AmPBS that is distinguishable from untreated native AmPBS and can subsequently be tested as a substrate for recombinant AmNblB**.

Its molecular identity is an experimental outcome, not an assumption.

### Initial reconstruction

\[
\text{native AmPBS}
\quad \text{vs.} \quad
\text{native AmPBS} + \text{recombinant AmNblA}
\]

followed, where informative, by concentration- and time-dependent experiments.

A sample-budget calculation based on the available native AmPBS stock will precede assay expansion because available native substrate constrains the number of conditions and replicates that can be tested.

### Readouts

**Mass photometry (Refeyn TwoMP).**  
Mass photometry will test whether addition of recombinant AmNblA redistributes sufficiently large AmPBS-derived particle populations. The objective is not detection of free AmNblA itself but identification of changes in native antenna assemblies and candidate intermediates.

**Fluorescence spectroscopy (Jobin Yvon Fluorolog-3).**  
Steady-state excitation/emission spectroscopy will determine whether AmNblA-dependent structural changes are accompanied by changes in PCB/PBP photophysical state.

**Biochemical separation and composition.**  
Native separation, density gradients, electrophoresis, chromatography and proteomics will be used where required to establish the composition of reproducible states. Where a state appears positionally ordered, proteomic composition or cleavage mapping may be used to test that interpretation directly, informed by recent NblA degradation studies [@zborovsky2025].

### Possible outcomes

**A --- discrete molecular intermediates.**  
Reproducible particle populations emerge after recombinant AmNblA treatment. These become candidate substrates for Aim 4.

**B --- heterogeneous disassembly.**  
Recombinant AmNblA produces broad fragmentation without a stable intermediate. Aim 4 then addresses substrate distributions rather than a single AmPBS* species.

**C --- local remodeling without major mass change.**  
Spectral or biochemical changes occur without a large mass-photometry shift, suggesting altered interfaces, pigment coupling or accessibility rather than extensive disassembly.

**D --- no reproducible effect despite validated recombinant protein quality.**  
The hypothesis that recombinant AmNblA alone is sufficient to generate a measurable AmPBS state is weakened. Simultaneous action, additional factors, endogenous modifications or other missing cellular components become higher-priority explanations.

### Interpretive limit

Even a successful reconstruction establishes that recombinant AmNblA is **sufficient under the defined assay conditions** to produce the observed transformation. It does not establish that the same isolated reaction is the sole or complete mechanism operating in the cell.

# Chapter IV --- Structural and biochemical mechanism of recombinant AmNblB

## Aim 4. Determine how recombinant AmNblB recognizes and remodels native AmPBS-derived substrate states in the cell-free system

### Rationale

NblB is required for normal PBS degradation and is implicated in PBP/bilin remodeling [@levi2018]. Its relationship to bilin lyases suggests a connection to chromophore chemistry, but available biochemical data do not support a simple autonomous reverse-lyase model. NblA and NblB influence multiple PBP/lyase reactions, while direct NblA--NblB binding was not detected in the Hu et al. system [@hu2020].

The central mechanistic question is therefore:

> **What native AmPBS-derived substrate state does recombinant AmNblB recognize, and what molecular transformation does it promote in the reconstructed system?**

As in Aim 3, the AmNblB used here is recombinant and heterologously overexpressed. Its biochemical activity must be demonstrated rather than inferred from purity or structure.

## Aim 4A. Test substrate-state dependence of recombinant AmNblB activity

The core experimental matrix is:

\[
\begin{array}{ll}
A & \text{native AmPBS} \\
B & \text{native AmPBS} + \text{recombinant AmNblA} \\
C & \text{native AmPBS} + \text{recombinant AmNblB} \\
D & \text{native AmPBS} + \text{recombinant AmNblA} + \text{recombinant AmNblB} \\
E & \text{native AmPBS} \xrightarrow{\text{recombinant AmNblA pretreatment}} \text{AmPBS}^* + \text{recombinant AmNblB}
\end{array}
\]

Concentrations, stoichiometries, incubation times and temperatures will follow from Aim 3 optimization and the native-AmPBS sample budget.

### Validation of recombinant AmNblB

A recombinant AmNblB-dependent change in a defined native AmPBS/PBP substrate must be demonstrated before mechanistic conclusions are drawn.

If no activity is detected, the initial alternatives include:

- inappropriate substrate state;
- incorrect assay conditions;
- recombinant protein differing from its endogenous active state;
- requirement for AmNblA simultaneously;
- requirement for a bilin lyase or another component;
- incorrect mechanistic assumption about the measurable output.

### Direct interaction test

AmNblA--AmNblB association will be tested directly using the recombinant _A. marina_ proteins.

Candidate approaches include pull-down/co-elution, crosslinking followed by MS identification, and other solution-state interaction methods compatible with the molecular sizes involved. Mass photometry may contribute if the resulting complex falls within a reliable detection range, but it will not be relied upon as the sole interaction assay.

A negative result will be interpreted within the detection limits of the methods rather than as proof that no transient or substrate-mediated interaction can occur.

### Separation-of-function AmNblA control

A separation-of-function recombinant AmNblA mutant would strengthen discrimination between substrate remodeling and downstream adaptor functions.

Residues implicated in ClpC recruitment are a candidate starting point, but no AmNblA mutant phenotype is assumed in advance. Candidate substitutions will require validation that the recombinant mutant retains relevant AmPBS/PBP interaction while selectively losing the function under investigation.

### Competing models

**Model 1 --- sequential substrate remodeling**

\[
\text{native AmPBS}
\xrightarrow{\text{recombinant AmNblA}}
\text{AmPBS}^*
\xrightarrow{\text{recombinant AmNblB}}
\text{AmPBS}^{**}
\]

**Prediction:** NblA-pretreated native AmPBS responds differently to recombinant AmNblB than untreated native AmPBS (E ≠ C).

**Model 2 --- direct association**

**Prediction:** a detectable recombinant AmNblA--AmNblB species is observed and the simultaneous D condition produces behavior consistent with that association.

**Model 3 --- simultaneous/substrate-mediated cooperation**

**Prediction:** simultaneous recombinant AmNblA + AmNblB produces a state not reproduced by sequential pretreatment, without requiring a stable detectable binary complex.

**Model 4 --- parallel activity**

**Prediction:** recombinant AmNblB effects are largely independent of prior recombinant AmNblA treatment under the reconstructed conditions (C ≈ E).

**Model 5 --- missing-component dependence**

**Prediction:** the minimal native-AmPBS + recombinant-AmNblA + recombinant-AmNblB system fails to reproduce the relevant remodeling despite validated individual components, indicating requirement for lyases or additional degradation machinery.

Mass photometry, fluorescence and biochemical/compositional measurements will provide orthogonal readouts where technically appropriate.

## Aim 4B. Determine the structural organization of recombinant AmNblB

Structural analysis is intended to generate experimentally testable mechanistic hypotheses rather than serve as an endpoint.

Recombinant AmNblB has produced crystals in the Harris laboratory. The immediate action is to establish the status of these crystals and any existing diffraction data.

Current status:

- crystals: reported;
- diffraction quality: **N/A**;
- dataset: **N/A**;
- refined structure: **N/A**;
- resolution: **N/A**.

Objectives are to:

- establish the oligomeric and structural organization of recombinant AmNblB;
- identify candidate PBP-interaction surfaces;
- determine whether a lyase-like internal cavity is structurally conserved;
- map residues previously implicated in NblB function onto the experimental structure if obtained;
- compare AmNblB architecture with characterized bilin lyases.

If crystallography does not yield a usable structure, computational structural models and other experimentally accessible solution-state methods will be used to generate hypotheses. Computational predictions will be treated as models rather than experimental structures [@jumper2021].

## Aim 4C. Test structure-derived functional hypotheses

Candidate recognition or mechanistically relevant residues/surfaces will be tested by targeted mutagenesis of recombinant AmNblB.

A useful mutant should:

1. retain evidence of global folding and appropriate oligomeric behavior; and
2. selectively alter substrate interaction or remodeling.

Wild-type and mutant recombinant AmNblB will be compared using the substrate-state assays developed in Aims 3--4A.

The causal logic is:

\[
\text{structure/model}
\rightarrow
\text{candidate determinant}
\rightarrow
\text{mutation}
\rightarrow
\text{validated protein}
\rightarrow
\text{substrate/remodeling phenotype}.
\]

## Aim 4D. Determine the fate of the bilin chromophore

Fluorescence changes can report pigment environment, coupling, quenching or transfer but cannot by themselves demonstrate covalent chromophore detachment.

The analytical objective is to distinguish among:

- PCB remaining covalently attached to its PBP;
- loss of detectable covalently associated PCB;
- free/extracted PCB;
- transfer of PCB to another protein;
- chemical modification of PCB;
- altered pigment environment without detachment.

A staged analytical chain is proposed:

1. **Zinc-enhanced bilin fluorescence after SDS-PAGE.** Changes in Zn-enhanced fluorescence relative to protein staining provide an initial readout of detectable covalently associated bilin. Loss of signal alone will not be treated as definitive proof of chromophore detachment.
2. **Denaturing/extraction-based spectroscopy**, where validated, to compare protein-associated and extractable pigment.
3. **Reverse-phase HPLC** of extracted chromophore to resolve free or chemically altered pigment species where technically feasible.
4. **LC-MS/MS of chromopeptides** to test site occupancy and, where possible, identify transfer to alternative protein acceptors.

Exact extraction chemistry, HPLC method and chromopeptide-MS workflow require experimental validation and confirmation of institutional capabilities.

### Interpretive limit

The cell-free system can establish that defined combinations of native substrate and recombinant factors are sufficient to produce particular biochemical transformations. It cannot by itself establish their timing, localization, regulation or completeness in intact _A. marina_ cells.

# 6. Integration of the four chapters

The proposal deliberately uses two experimental systems rather than forcing them into one molecular pathway.

The dinoflagellate chapters ask:

\[
\text{environmental acclimation}
\rightarrow
\text{native antenna-state remodeling}
\rightarrow
\text{modified pigment energetics/photophysics}.
\]

The cyanobacterial chapters ask:

\[
\text{native antenna substrate}
+
\text{recombinant degradation factors}
\rightarrow
\text{defined remodeled substrate states}
\rightarrow
\text{PBP/bilin remodeling}.
\]

The systems are integrated at three levels.

**Biologically**, both examine regulated transitions in accessory photosynthetic antenna systems.

**Experimentally**, both use orthogonal biochemical, compositional and spectroscopic measurements to distinguish molecular states, although the exact methods are adapted to the physical properties of each system rather than assumed to be interchangeable.

**Conceptually**, both follow the same analytical logic:

1. define a reference molecular state;
2. apply a biologically meaningful perturbation;
3. identify reproducible remodeled states;
4. determine their biochemical and/or structural basis;
5. connect molecular remodeling to photophysical or degradation-related function.

This provides thesis-level coherence without implying evolutionary homology between acpPC and PBS.

# 7. Expected contributions

## 7.1 Symbiodiniaceae

The work is expected to provide:

- a reproducible comparative workflow for membrane-associated acpPC biochemistry across five Symbiodiniaceae strains;
- quantitative information on biomass requirements and biochemical recovery;
- strain-specific sequence resources supporting acpPC proteomics where technically achievable;
- biochemical characterization of acpPC-containing complexes beyond whole-cell optical measurements;
- evidence for or against strain-dependent acpPC remodeling during chronic irradiance acclimation;
- mechanistic links between selected molecular antenna states and spectral/EET behavior where time-resolved capability is available.

## 7.2 Cyanobacteria

The work is expected to provide:

- a defined cell-free reconstruction based on native AmPBS and recombinant AmNblA/AmNblB;
- an operational molecular description of recombinant-AmNblA-dependent AmPBS remodeling;
- a direct test of whether recombinant AmNblA is sufficient to generate an AmNblB-responsive substrate state;
- discrimination among substrate-state dependence, direct association, simultaneous cooperation, parallel activity and missing-component models;
- structural information or experimentally constrained structural models for recombinant AmNblB;
- experimentally tested AmNblB recognition hypotheses;
- chemical evidence addressing bilin fate rather than inference from fluorescence alone.

## 7.3 What will be known at the end that is not known now

For the dinoflagellate arm:

> **Whether chronic irradiance acclimation is encoded in reproducible changes in the molecular state of membrane-associated acpPC antennae, and which biochemical changes are associated with altered photophysical behavior.**

For the cyanobacterial arm:

> **Whether recombinant AmNblA is sufficient to convert native AmPBS into a molecular state with altered susceptibility to recombinant AmNblB, and what structural and biochemical properties determine AmNblB activity in that reconstruction.**

# 8. Significance

Antenna remodeling is fundamental to photosynthetic fitness because photon capture must be balanced against photochemical capacity, nutrient availability and photodamage risk. High-resolution structures increasingly provide static views of photosynthetic complexes, but the molecular transitions connecting those structures to physiological acclimation and regulated degradation remain less well resolved.

In Symbiodiniaceae, the proposed work tests how chronic environmental acclimation is encoded in the biochemical state of a membrane-associated antenna central to dinoflagellate photosynthesis. By combining controlled culture experiments with native-complex biochemistry, strain-supported proteomics and photophysics, the work aims to connect whole-cell acclimation with molecular antenna state rather than infer mechanism from bulk pigment or transcriptional measurements alone.

In _A. marina_, the proposed work reconstructs a defined portion of antenna degradation using a native molecular substrate and recombinant remodeling factors. This provides a tractable way to distinguish substrate conditioning, protein association and missing-component models while retaining explicit limits on what a purified reconstruction can establish about the intact cell.

A broader outcome is an experimentally grounded framework for treating photosynthetic antennae as ensembles of regulated molecular states rather than fixed structures.

# 9. Feasibility and available infrastructure

## 9.1 Biological material

Available or currently maintained:

- SSA01, SSA02, SSA03, SSB01 and SSE01 Symbiodiniaceae cultures;
- current S3 cultures at approximately 3 L in 5-L Erlenmeyer flasks;
- KAN plating available as a diagnostic/fallback assay for detectable cultivable bacterial contamination;
- native AmPBS isolated from _A. marina_ MBIC11017;
- recombinant overexpressed AmNblA;
- recombinant overexpressed AmNblB.

Approximately 8-L Symbiodiniaceae production cultures in transparent rectangular ~9-L vessels are under consideration but are not yet validated.

## 9.2 Instrumental and methodological access

Available within the Harris laboratory and/or Technion infrastructure includes:

- protein expression and purification;
- ÄKTA/FPLC;
- HPLC;
- gel electrophoresis and standard protein biochemistry;
- proteomics;
- Refeyn TwoMP mass photometry;
- Jobin Yvon Fluorolog-3 fluorescence spectroscopy;
- flow cytometry;
- microscopy;
- crystallization and structural biology infrastructure;
- cryo-EM access;
- sequencing services capable of delivering FASTQ data.

Availability of an instrument or service does not imply that the required assay has already been validated for the present samples.

## 9.3 Capabilities requiring confirmation

| Capability | Needed for | Status | Fallback |
|:--|:--|:--|:--|
| WGS sequencing platform | Chapters I--II sequence resource | **N/A** | Published sequence resources |
| WGS depth/coverage | Assembly/proteome utility | **N/A** | Scope adjusted to achievable resource |
| Genome assembly service/strategy | FASTQ → assembly | **N/A** | Local/external bioinformatics workflow |
| Gene annotation strategy | Assembly → gene models | **N/A** | Homology/transcript-supported targeted analysis |
| Predicted proteome generation | Custom LC-MS/MS FASTA | **N/A** | Published proteome/transcriptome databases |
| Proteomics Center custom-FASTA requirements | acpPC identification | **N/A/to confirm** | Standard/reference search database |
| RNA-seq necessity/cost | Gene-model support / conditional expression analysis | **N/A** | No RNA-seq unless justified |
| Time-resolved fluorescence/ultrafast spectroscopy | Chapter II EET claims | **Go/no-go** | Collaboration; otherwise restrict claims |
| LC-MS/MS chromopeptide analysis | Aim 4D | To confirm | Zn-fluorescence + HPLC/other validated chemistry |
| Cryo-EM scheduling | Structural fallback | To confirm | Crystallography/other solution-state approaches |
| Exact LED emission spectra/channels | Conditional spectral experiment | **N/A** | Do not perform spectral-recipe experiment |

# 10. Risks, limitations, and alternative strategies

## 10.1 Symbiodiniaceae cell disruption may limit biochemical recovery

The dinoflagellate arm depends on recovery of useful membrane material. Cell-disruption efficiency will therefore be tested before extensive downstream optimization. Failure to recover sufficient material will trigger optimization of disruption and membrane isolation before production-scale culture is expanded.

## 10.2 Production-scale culture requirements are unknown

Current ~3-L cultures demonstrate culture maintenance at useful scale but do not establish the biomass required for acpPC isolation. Approximately 8-L cultures are only a candidate production format.

Aim 1 will determine:

- biomass required per preparation;
- recovery through each biochemical step;
- practical production working volume;
- production-cycle duration.

No fixed 8-L or 21-day production cycle is assumed.

## 10.3 Culture optical measurements contain non-pigment contributions

Whole-cell absorption contains wavelength-dependent scattering and is influenced by cell concentration, morphology and aggregation. OD$_{750}$ is not automatically proportional to biomass. Refill history and evaporation can also change culture optical properties.

Comparative experiments will therefore standardize culture history and interpret optical data together with independent cell/biomass measurements where required.

## 10.4 Culture-associated microorganisms are a potential analytical confound, not a routine exclusion criterion

The biochemical aims do not require demonstration of culture axenicity before each experiment. The target endpoint is an isolated and molecularly identified Symbiodiniaceae antenna fraction.

Culture-associated microorganisms could nevertheless complicate particular analyses, especially WGS and proteomics. These will be handled using analytical QC appropriate to the affected experiment.

KAN plating is available as a diagnostic/fallback assay if bacterial proliferation is suspected. Because plating detects only organisms able to grow under the assay conditions, a negative result will not be interpreted as proof of axenicity.

If microbial material materially prevents interpretation of a specific experiment, additional culture-cleaning or microbiological controls may be introduced at that point.

## 10.5 acpPC isolation may perturb native organization

Detergent solubilization can alter higher-order antenna organization. Increased purity will not automatically be interpreted as increased biological relevance.

Less-disrupted membrane fractions, multiple solubilization conditions and orthogonal compositional/spectral measurements will be used where necessary to distinguish native biology from purification artifacts.

## 10.6 Five strains create excessive combinatorial scope

The five-strain panel is used for comparative screening. Deep biochemical, structural or photophysical analysis will focus on selected contrasts.

Large production cultures will therefore not be generated for every strain × treatment × replicate combination.

## 10.7 WGS may not yield a useful predicted proteome automatically

Generation of FASTQ data is only the first step toward a proteomic search database.

Dinoflagellate genome size, repetitive sequence, divergent gene structures and unusual genome organization can complicate assembly and annotation. Published Symbiodiniaceae studies have used transcript evidence and multi-tool gene prediction to improve gene models.

Culture-associated microbial DNA creates an additional QC requirement but does not itself require an axenic starting culture. Taxonomic screening/decontamination will be incorporated at the read and/or assembly level where appropriate.

Accordingly, the WGS component will be judged by whether it generates a sequence resource useful for acpPC identification, not by whether it produces a chromosome-level genome.

If whole-genome annotation is inadequate, targeted use of assembled genomic sequence, transcript evidence, published proteins and homology-based acpPC identification will be retained.

## 10.8 RNA-seq could cause scope expansion

RNA-seq could improve gene models and provide useful biological information, but adding transcriptomics to all five strains and irradiance conditions would substantially expand the project.

It will therefore be added only if it resolves a defined limitation or mechanistic question.

## 10.9 Whole-cell phenotypes are not acpPC-specific

Absorption, fluorescence, microscopy and flow cytometry provide physiological context but cannot establish acpPC molecular remodeling without biochemical fractionation.

## 10.10 Time-resolved spectroscopy may be unavailable

Without time-resolved capability, Chapter II cannot directly establish altered EET kinetics. In that case, the chapter will be restricted to biochemical organization and steady-state photophysical differences unless collaboration is established.

## 10.11 Recombinant AmNblA/AmNblB may not reproduce endogenous protein states

Heterologous overexpression can alter folding, oligomerization, modifications or associated cofactors. Protein purity is therefore not equivalent to biological activity.

Recombinant AmNblA and AmNblB will be validated functionally against native AmPBS before mechanistic interpretation.

Failure of the reconstruction will be evaluated as potentially reflecting either an incorrect mechanistic model or missing properties/components of the recombinant system.

## 10.12 Mass photometry has molecular and sample-compatibility limits

TwoMP is well suited to sufficiently large soluble assemblies such as AmPBS-derived particles but not necessarily to free NblA/NblB or detergent-solubilized membrane complexes.

Its use in the acpPC arm is conditional on empirical compatibility.

## 10.13 Fluorescence does not prove chromophore detachment

Spectral changes will be interpreted as changes in photophysical state until orthogonal chemical/biochemical measurements establish chromophore fate.

## 10.14 NblA/NblB may be insufficient for complete reconstruction

PBS degradation involves additional proteins, including bilin lyases, proteases and NblD-related pathways [@hu2020; @krauspe2021; @krauspe2022].

Failure of the minimal system to reproduce complete degradation will therefore be used to test missing-component models rather than automatically interpreted as failure of NblA/NblB involvement.

## 10.15 AmNblB crystals may not yield a structure

Existing recombinant AmNblB crystals do not yet constitute structural data. If they fail to yield useful diffraction, structural hypotheses can still be generated from validated computational models and experimentally constrained oligomeric/solution-state information and tested by mutagenesis.

# 11. Work plan

Timing remains provisional and assumes a four-year programme. The cyanobacterial cell-free arm can generate mechanistic results while the more technically uncertain Symbiodiniaceae membrane workflow and sequence resources are being established.

| Period | Cyanobacterial arm | Dinoflagellate arm |
|:--|:--|:--|
| Y1 H1 | Establish recombinant AmNblB crystal/diffraction status; native-AmPBS sample budget; validate recombinant AmNblA/AmNblB preparations | Cell-disruption and membrane-recovery trials; quantify biomass/yield; define culture-history controls; microbial QC only where analytically indicated |
| Y1 H2 | Native AmPBS + recombinant AmNblA baseline; begin AmPBS* definition; direct recombinant NblA--NblB interaction tests | Aim 1 isolation workflow; irradiance pilot; determine production biomass requirement; confirm time-resolved spectroscopy access |
| Y1--Y2 | Continue cell-free reconstruction | WGS enabling workflow if feasible: sequencing → FASTQ QC/taxonomic screening → assembly → annotation/predicted proteins; confirm Proteomics Center custom-FASTA requirements |
| Y2 | Aim 4A mechanistic matrix; separation-of-function control development | Aim 1 comparative biochemical characterization; final irradiance design; chronic acclimation experiment |
| Y3 | AmNblB structural/oligomeric analysis; mutagenesis | Selected production-scale cultures; acpPC proteomics/pigment/assembly analysis; select mechanistic contrasts |
| Y4 | Aim 4D chromophore fate; integrate reconstitution model | Mechanistic/photophysical follow-up of selected acpPC contrasts; thesis integration |

RNA-seq is not scheduled because its necessity is currently **N/A**. If required for gene-model support, it should be introduced early enough to inform proteomic database construction. If required to answer a Chapter II mechanistic question, its design will follow the biochemical result rather than precede it.

The principal dependency structure is:

1. maintain traceable, strain-controlled Symbiodiniaceae cultures;
2. determine biomass requirement and establish reproducible membrane/acpPC recovery;
3. generate strain-specific sequence resources where feasible and determine whether they support proteomic identification;
4. address microbial contamination analytically if it becomes relevant to WGS, proteomics or culture interpretation;
5. establish the chronic irradiance screen and biological-stability criteria;
6. select strain × condition contrasts;
7. generate only the production biomass required for selected biochemical contrasts;
8. characterize acpPC remodeling and, where capability permits, EET consequences;
9. validate recombinant AmNblA/AmNblB activity with native AmPBS;
10. define recombinant-AmNblA-dependent AmPBS states;
11. discriminate AmNblB mechanistic models;
12. integrate AmNblB structural information with mutagenesis;
13. resolve bilin fate with orthogonal chemistry.

# 12. Candidate's contribution

All new experimental work described in Chapters I--IV will be carried out by the candidate except where specialized institutional or collaborative measurements are explicitly required.

The five Symbiodiniaceae strains were supplied by Prof. Tingting Xiang. Their maintenance, culture scaling, acclimation experiments, production strategy and biochemical characterization in this project are the candidate's work.

The proposal does not require routine demonstration of axenicity for these cultures. Where microbial contamination becomes analytically relevant, the candidate will apply appropriate QC, including the available KAN plating assay as a diagnostic tool and sequence/proteomic filtering where appropriate.

WGS, if undertaken, will use institutional sequencing services for sequence generation. The candidate's scientific responsibility includes experimental design, sample preparation and the integration of sequence resources with the acpPC biochemical/proteomic questions. The exact division of responsibility for assembly and annotation is currently **N/A** and will depend on the service or collaboration established.

Proteomic measurements will use the Technion Proteomics Center. Where strain-specific predicted protein FASTAs can be generated, these will be integrated into the proteomic search strategy in consultation with the center.

For the cyanobacterial arm, native AmPBS and the existing recombinant AmNblA/AmNblB preparations and crystallization work are Harris-laboratory starting resources and will be identified as such. The proposal does not represent recombinant AmNblA or AmNblB as native purified proteins.

Time-resolved spectroscopy, advanced proteomics, sequencing and structural measurements performed through specialist facilities or collaborations will be acknowledged accordingly, with the candidate responsible for the biological question, sample preparation where appropriate, experimental integration and interpretation.

---

# Appendix A --- Internal working register (not for submission)

_This appendix is working material for the candidate and supervisor. It should be removed before the proposal is submitted._

## A.1 Open decisions

| Item | Status | Why it matters |
|:--|:--|:--|
| Final thesis title | Open | Must cover all four chapters without implying a shared molecular mechanism |
| Required proposal length/format | Open | Determines final compression |
| Culture-associated microbial contamination | Not a routine exclusion criterion; KAN plating available as diagnostic QC | Potential confound for WGS/proteomics or abnormal culture behavior; address analytically when relevant |
| Biomass required per acpPC preparation | **N/A** | Determines production scale |
| Production working volume | **N/A until Aim 1 yield test** | ~8 L is under consideration, not validated |
| Production-cycle duration | **N/A** | Cannot assume a fixed harvest cycle |
| Final irradiance values | **N/A/pilot** | Primary Aim 2 perturbation |
| Biological stability criterion after ≥3-week acclimation | **N/A/pilot** | Three weeks is a minimum, not proof of acclimation |
| Final biological replicate number | Provisional n≥3; revise from pilot variance | Required for reproducibility |
| Final acpPC isolation protocol | Aim 1 objective | Must preserve useful native-like material |
| Primary comparative acpPC unit | Open | Free acpPC vs photosystem-associated vs enriched membrane fraction |
| WGS sequencing platform | **N/A** | Determines read properties and assembly strategy |
| WGS depth/coverage | **N/A** | Determines assembly feasibility |
| Genome assembly strategy/service | **N/A** | FASTQ alone is insufficient |
| Gene annotation strategy | **N/A** | Dinoflagellate gene prediction is nontrivial |
| Predicted proteome generation | **N/A** | Required for strain-specific protein FASTA |
| Proteomics Center custom-FASTA requirements | **N/A/to confirm** | Required before database construction |
| RNA-seq necessity | **N/A** | Conditional gene-model/mechanistic support |
| RNA-seq cost/design | **N/A** | Do not commit without scientific need |
| Exact LED channels/emission spectra | **N/A** | Spectral-quality experiment remains conditional |
| Time-resolved EET access | **Go/no-go** | Determines whether Chapter II can make kinetic EET claims |
| Native AmPBS sample budget | To quantify | Constrains cell-free assay design |
| Recombinant AmNblA activity validation | To establish | Purity does not establish activity |
| Recombinant AmNblB activity validation | To establish | Purity/structure does not establish activity |
| AmNblA separation-of-function mutant | Candidate strategy only | Requires Am-specific validation |
| AmNblB diffraction status | **N/A/to establish** | Existing crystals are not yet a structure |
| AmNblB dataset/structure/resolution | **N/A** | No structural result assumed |
| Exact physiological AmNblB substrate | **N/A** | Central research question |
| Stable AmNblA--AmNblB interaction | **N/A/to test** | Heterologous negative result is not decisive for _A. marina_ |
| Definitive bilin-fate workflow | Staged strategy defined; exact methods to validate | Needed to distinguish detachment, transfer and modification |
| Requirement for lyases/additional factors | **N/A** | Explicit alternative model |
| Formal citation for previous Harris-lab thesis work | To add | Preliminary work must be attributable |

## A.2 Culture architecture register

The intended culture architecture is fixed conceptually:

\[
\text{strain-controlled culture bank}
\rightarrow
\text{liquid master}
\rightarrow
\text{replicated experimental cultures}
\rightarrow
\text{selected seed culture}
\rightarrow
\text{production-scale culture}
\rightarrow
\text{biochemical harvest}.
\]

Current status:

- five strains maintained;
- S3 cultures approximately 3 L in 5-L Erlenmeyer flasks;
- transparent rectangular ~9-L vessels available/considered for approximately 8-L production cultures;
- ~8 L is **not** a validated required volume;
- biomass requirement = **N/A**;
- production-cycle duration = **N/A**;
- a fixed 21-day production cycle is **not assumed**.

A deliberate irradiance, photoperiod or spectral change requires at least three weeks before the culture is considered for an acclimated-state assessment. Biological stability remains an additional requirement.

### Microbial QC position

Axenicity is **not** a routine requirement for the biochemical aims.

Instead:

\[
\text{suspected or analytically relevant microbial contribution}
\rightarrow
\text{diagnostic QC}
\rightarrow
\text{interpretation/troubleshooting}.
\]

Available QC includes KAN plating for detectable cultivable contamination under the established conditions, plus taxonomic sequence/proteomic filtering where relevant.

A negative KAN plate is not interpreted as proof of axenicity.

## A.3 WGS/proteomics register

The intended information flow is:

\[
\text{DNA}
\rightarrow
\text{WGS}
\rightarrow
\text{FASTQ reads}
\rightarrow
\text{QC/taxonomic screening}
\rightarrow
\text{genome assembly}
\rightarrow
\text{gene models}
\rightarrow
\text{predicted proteins}
\rightarrow
\text{FASTA search database}
\rightarrow
\text{LC-MS/MS identifications}.
\]

Important discipline:

- FASTQ ≠ predicted protein FASTA.
- Assembly ≠ annotation.
- Annotation ≠ experimentally validated proteome.
- Non-axenic culture ≠ unusable WGS dataset.
- Microbial reads must nevertheless be recognized and handled where relevant.
- A WGS dataset does not guarantee reliable recovery of all acpPC paralogs.
- Chromosome-level genome assembly is not required by the thesis.
- Transcript evidence may improve dinoflagellate gene prediction.
- RNA-seq remains conditional.
- Published/homology-based acpPC sequences remain a fallback.

The minimum successful output is a strain-specific sequence resource that improves acpPC-family identification.

## A.4 Cell-free reconstruction register

Correct terminology throughout the proposal:

\[
\boxed{
\text{native AmPBS}
+
\text{recombinant AmNblA}
+
\text{recombinant AmNblB}
}
\]

Do **not** describe AmNblA or AmNblB as purified native proteins.

The reconstruction tests biochemical sufficiency under defined conditions.

It does **not** automatically establish:

- endogenous protein state;
- endogenous stoichiometry;
- cellular localization;
- physiological timing;
- requirement/sufficiency _in vivo_;
- absence of additional pathway components.

## A.5 Evidence discipline

Three evidence levels are distinguished throughout:

### Published evidence

Peer-reviewed results used to establish background, precedent and the state of knowledge.

### Preliminary/unpublished evidence

Harris-laboratory results, current culture observations and previous thesis work. These are labeled as preliminary and are not presented as peer-reviewed findings.

### Proposed mechanisms

Hypotheses, candidate intermediate states and predicted pathways generated by this proposal. These remain explicitly testable.

## A.6 Scientific caution flags

The following statements should **not** enter the submitted proposal without stronger evidence:

- "Whole-cell absorption peaks identify acpPC."
- "OD$_{750}$ is biomass."
- "An 8-L culture provides enough acpPC."
- "A 21-day production cycle is sufficient."
- "Three weeks proves photoacclimation."
- "The cultures must be axenic for acpPC purification."
- "No growth on a KAN plate proves axenicity."
- "FASTQ files can be used directly for proteomic protein identification."
- "WGS will produce complete strain proteomes."
- "WGS will produce chromosome-level genomes."
- "RNA-seq is required."
- "acpPC oligomerization is the mechanism of irradiance acclimation."
- "Mass photometry will necessarily work on detergent-solubilized acpPC."
- "Recombinant AmNblA/AmNblB are equivalent to their endogenous molecular states."
- "Purified recombinant NblA/NblB are active because they are folded."
- "A cell-free reconstruction is the complete _in vivo_ degradation pathway."
- "Loss of Zn-enhanced bilin fluorescence alone proves chromophore detachment."

## A.7 Novelty audit --- current position

1. Photoacclimation in Symbiodiniaceae is established background, not the novelty claim.
2. acpPC architecture is no longer broadly unknown; modern PSI--AcpPCI structures provide molecular reference states [@zhao2024; @zhou2024].
3. Oligomerization is a candidate mechanism rather than a presumed one, and purification can alter assembly state.
4. The principal dinoflagellate gap is the missing bridge from chronic acclimation to native molecular antenna state and from that state to pigment energetics/function.
5. WGS is an enabling strategy for biochemical interpretation, not an independent genomics thesis aim.
6. Axenicity is not a thesis objective or routine prerequisite for the acpPC biochemical aims. Microbial contamination is addressed as an analytical QC issue when relevant.
7. Published Symbiodiniaceae genome studies support the feasibility of generating predicted protein resources but also show that transcript-supported, multi-method annotation may be necessary. Raw genomic sequencing alone should therefore not be equated with a usable predicted proteome.
8. Recent work on _A. marina_ light acclimation and horizontal acquisition/regulatory integration of its PC system strengthens the biological context without resolving the NblA/NblB mechanism [@viola2025; @ulrich2024; @miller2021].
9. Recent NblA work provides precedent for experimentally resolving ordered PBS degradation states [@zborovsky2025].
10. The cyanobacterial novelty claim concerns a defined cell-free reconstruction with native AmPBS and recombinant AmNblA/AmNblB. It does not depend on representing the recombinant proteins as native.

Current novelty formulation:

> **Connect chronic irradiance acclimation to the biochemical state of native membrane-associated acpPC antennae across multiple Symbiodiniaceae strains, and use a defined native-substrate/recombinant-factor reconstruction to determine how AmNblA-dependent AmPBS states govern AmNblB recognition and bilin/PBP remodeling.**

Repeat the novelty search immediately before submission.

## A.8 Bibliography notes

`Technion_Era.bib` remains the master bibliography.

Before submission:

- consolidate duplicate entries;
- verify DOI, author, title, year and journal metadata;
- remove or ignore Zotero-local `file=` fields for Overleaf;
- add recent primary literature where it changes the state of the field;
- add the formal citation for the Harris-laboratory MSc thesis;
- perform final searches on NblB structural literature and acpPC chronic-remodeling literature;
- add appropriate Symbiodiniaceae genome/annotation literature supporting the WGS strategy.

Citation keys currently used or requiring verification include:

- `@iglesiasprieto1997` --- irradiance-dependent Symbiodiniaceae photoacclimation/chlorophyll--protein complexes; verify against the master bibliography.
- `@zhou2024` --- **citation-key name may be misleading**: the 2024 _PNAS_ PSI--AcpPCI paper is Li et al., _Structures and organizations of PSI--AcpPCI supercomplexes from red tidal and coral symbiotic photosynthetic dinoflagellates_, _PNAS_ 121:e2315476121, DOI 10.1073/pnas.2315476121. The key may remain `zhou2024` for compatibility if already used, but the BibTeX metadata must contain the correct authors.
- `@boldt2012` --- Boldt, Yellowlees & Leggat, hyperdiversity of integral light-harvesting protein genes in _Symbiodinium_; verify metadata in `Technion_Era.bib`.
- `@miller2021` --- reacquisition of light-harvesting genes in _A. marina_ MBIC11017; verify master metadata.
- `@ulrich2024` --- integration of horizontally acquired light-harvesting genes into an ancestral regulatory network in _A. marina_ MBIC11017.
- `@viola2025` --- **bibliographic metadata require correction if the existing entry attributes the paper incorrectly**. The relevant 2025 _New Phytologist_ study is Oliver, Elias & Croce, concerning acclimation of _A. marina_ MBIC11017 to white light.
- `@zborovsky2025` --- **citation-key name may be retained for compatibility, but the article metadata require correction**. The relevant paper is Nadel et al. (2025), _Viral NblA proteins negatively affect oceanic cyanobacterial photosynthesis_, _Nature_ 648:434--442, DOI 10.1038/s41586-025-09656-x.
- `@hirose2022` --- if retained, verify carefully: the relevant 2022 comparative genomic work on _A. marina_ MBIC10699 is associated with Yamamoto et al.; do not propagate an incorrect author attribution.
- `@zhao2024` --- verify the 2024 _Symbiodinium_ PSI--AcpPCI structural entry against the primary article.
- additional Symbiodiniaceae genomics citation(s) should be added for the WGS/annotation rationale. Particularly relevant published evidence includes comparative analyses showing that Symbiodiniaceae gene prediction has used RNA-seq/transcript evidence together with multiple prediction algorithms, and recent _Effrenium voratum_ genome projects providing assembled genomes, predicted gene models and protein sequences. These references should be added with verified BibTeX metadata rather than assigned invented citation keys in this draft.

### External literature check used for Draft 3.3

The WGS section was checked against current Symbiodiniaceae genomic literature in addition to the uploaded sources.

This check supports the conservative formulation used here:

- comparative Symbiodiniaceae genome analyses have used transcript evidence together with multiple gene-prediction approaches;
- chromosome-scale Symbiodiniaceae work demonstrates the unusual organization and technical complexity of dinoflagellate genomes;
- recent _Effrenium voratum_ projects demonstrate that genome and transcriptome resources, predicted gene models and protein sequences can be generated, while also illustrating the scale and annotation challenge of these genomes.

These observations support:

\[
\text{WGS}
\rightarrow
\text{strain-specific sequence resource}
\rightarrow
\text{predicted proteins}
\rightarrow
\text{proteomic search database}
\]

as a realistic enabling objective, but do **not** justify promising that FASTQ generation alone will produce a complete or high-quality predicted proteome.

# References

References are managed in `Technion_Era.bib`. Citation keys are retained in Pandoc/Obsidian form for later migration to Overleaf/BibTeX.