---
author: Carlos Alberto Martínez
bibliography: Technion_Era.bib
date: 2026-09-18
institution: Technion -- Israel Institute of Technology
status: Scientific working draft 3.1
supervisor: Prof. Dvir Harris
title: Research Proposal --- Working Draft 3.1
---

# Working title

**Regulated Molecular States of Photosynthetic Antennae: Acclimatory
Remodeling of Dinoflagellate acpPC and Controlled Disassembly of the
*Acaryochloris marina* Phycobilisome**

> **Title status:** Working title. Final title to be fixed at submission.

# Abstract

Photosynthetic antennae are usually described by their structures, but
their biological function depends on transitions between molecular
states. Cryo-EM has recently delivered high-resolution architectures for
both antenna systems studied here, yet the transitions that connect
those architectures to acclimation and to regulated degradation remain
unresolved. This proposal treats two evolutionarily independent antenna
systems as tractable models of the same problem: the membrane-associated
peridinin--chlorophyll *a/c*-binding complexes (acpPC) of Symbiodiniaceae
dinoflagellates, and the phycobilisome (PBS) degradation machinery of
*Acaryochloris marina* MBIC11017.

What the two systems share is not a shared architecture or a shared
spectral rationale but a shared experimental object: an accessory
pigment--protein antenna whose organization is under active
physiological control and whose functional states are separable in the
laboratory. Symbiodiniaceae peridinin-based antennae are remodeled
during photoacclimation. In *A. marina*, a phycocyanin antenna extends
harvesting into the yellow--orange region alongside chlorophyll *d*, and
the genes for both its assembly and its disassembly were lost
ancestrally and reacquired by horizontal transfer [@ulrich2024;
@miller2021]. Each therefore offers a case where antenna organization
must be actively established, maintained and dismantled.

The dinoflagellate arm uses five clonal Symbiodiniaceae strains derived
from the Xiang collection [@xiang2013]: *Symbiodinium linucheae* SSA01,
*S. necroappetens* SSA02, *S. pilosum* SSA03, *Breviolum minutum* SSB01
and *Effrenium voratum* SSE01. All five are established in culture at
volumes sufficient for biochemistry, with whole-culture absorption and
fluorescence spectra in hand. The work will first build a comparative
biochemical workflow for native membrane antenna fractions, then test
whether chronic irradiance acclimation produces reproducible changes in
acpPC organization, pigment environment and excitation-energy transfer.

The cyanobacterial arm asks how AmNblA-dependent remodeling of native
AmPBS is mechanistically coupled to AmNblB activity. Published work
establishes NblA as a phycobiliprotein-binding Clp adaptor and implicates
NblB in bilin remodeling in an NblA-dependent manner, yet no direct
NblA--NblB interaction was detected in the one system where it was
tested [@baier2014; @levi2018; @hu2020]. The Harris laboratory holds
purified native AmPBS, AmNblA and AmNblB, and has prior evidence that
NblA identity encodes substrate selectivity. The work will define
AmNblA-dependent molecular states of AmPBS, test how those states change
AmNblB activity, determine the structural organization of AmNblB, and
resolve the fate of the phycocyanobilin chromophore using orthogonal
chemistry rather than fluorescence alone.

The unifying question is whether antenna function is governed by
regulated transitions between defined pigment--protein states, and
whether such transitions preserve or redirect excitation-energy flow.

# 1. Scientific background and rationale

## 1.1 Photosynthetic antennae as dynamic molecular systems

Photosynthetic antenna systems extend the spectral and spatial
cross-section for photon capture and direct excitation energy toward
reaction centers. Their performance depends on the organization of
pigments within protein scaffolds, the association of antenna proteins
into higher-order complexes, and the energetic coupling among
chromophores. Antenna architecture is therefore not merely structural:
changes in protein composition, oligomerization, pigment occupancy,
chromophore geometry, or interaction with reaction centers can alter
excitation-energy transfer, quenching, and photoprotection.

The central premise of this proposal is that antennae should be studied
as **dynamic molecular systems**. Two forms of remodeling are
particularly informative. First, long-term acclimation to irradiance can
alter antenna abundance and composition while photosynthetic cells
remain viable and functional. Second, nutrient or environmental stress
can trigger controlled disassembly and recycling of antenna material.
These processes occur in very different organisms and protein systems,
but both require coordinated transitions between defined
pigment--protein states.

This proposal therefore investigates two complementary systems:

1.  **Symbiodiniaceae acpPC-containing membrane antennae**, in which
    irradiance-dependent acclimation provides a route to study adaptive
    remodeling of pigment--protein organization.
2.  ***Acaryochloris marina* phycobilisomes**, in which
    NblA/NblB-dependent degradation provides a route to study controlled
    antenna disassembly and pigment remodeling.

The proposal does **not** assume that these systems share a homologous
molecular mechanism. Their connection is threefold and explicit:

-   **Biological.** Both are accessory pigment--protein antennae whose
    abundance and organization are actively regulated rather than fixed,
    one by acclimatory remodeling and one by controlled destruction.
-   **Analytical.** Both arms follow the same logic --- define the
    native molecular state, apply a biologically meaningful
    perturbation, identify reproducible remodeled states, determine
    their biochemical basis, and connect them to pigment energetics ---
    using a shared core of native separation, steady-state and
    time-resolved fluorescence, pigment analysis and proteomics.
-   **Conceptual.** Both ask whether a defined molecular state, rather
    than a static architecture, is the correct unit of explanation for
    antenna behavior. The common object of the thesis is the
    experimentally resolvable transition between functional states of a
    pigment--protein antenna.

## 1.2 Symbiodiniaceae light harvesting

Symbiodiniaceae possess unusual photosynthetic antenna systems adapted
to marine light environments. Their major light-harvesting pigments
include chlorophyll *a*, chlorophyll *c*$_2$, and the carotenoid
peridinin. Peridinin-containing antennae occur in at least two major
biochemical contexts: soluble peridinin--chlorophyll *a* protein (PCP)
and membrane-associated chlorophyll *a/c*$_2$--peridinin protein
complexes (acpPC). PCP has been extensively characterized
spectroscopically and structurally, whereas membrane acpPC complexes are
less completely understood in native and acclimation-dependent states
[@jiang2012a; @carbonera2014; @jovine1995].

Cryo-EM has substantially advanced structural understanding of membrane
antenna organization in dinoflagellates. A 2.8 Å structure of a
*Symbiodinium* PSI--LHCI supercomplex resolved 13 AcpPCI proteins
surrounding a 13-subunit PSI core, including two previously
unidentified core subunits, and mapped predicted energy-transfer routes
[@zhao2024]. In parallel, three PSI--AcpPCI structures from two
dinoflagellates were determined at 2.70--2.99 Å, in one case resolving
17 AcpPCI subunits assigned using mass spectrometry and transcriptome
data [@li2024]. Earlier biochemical work demonstrated membrane-bound
light-harvesting complexes in dinoflagellates and provided precedents
for detergent-based isolation [@jovine1995]. These findings establish
that acpPC architecture can now be interrogated in a mechanistically
meaningful structural context --- and equally that architecture alone
has not answered how these complexes change with physiological state.

Two features make the system biochemically demanding and are treated
explicitly in the risk analysis. First, acpPC is encoded by a
hyperdiverse multigene family, including polyprotein precursors, so
subunit-level identification depends on strain-matched sequence
resources [@boldt2012]. Second, purification can itself alter assembly
state, so isolation conditions are part of the experiment rather than a
preliminary to it.

Light acclimation provides an experimentally relevant perturbation.
Classical work showed that Symbiodiniaceae alter chlorophyll--protein
complexes in response to photon flux and that these responses can be
species dependent [@iglesiasprieto1997]. High-light studies further
indicate that membrane antenna components, including acpPC-associated
excitation, can undergo strong non-photochemical quenching rather than
simply disconnecting soluble PCP from downstream antennae
[@kanazawa2014]. Thus, irradiance affects antenna function, but the
molecular relationship between chronic acclimation and the biochemical
state of native acpPC complexes remains unresolved.

### Knowledge gap 1

> **How does chronic irradiance acclimation alter the biochemical
> organization of membrane-bound acpPC complexes across phylogenetically
> distinct Symbiodiniaceae, and how are those changes related to
> chromophore environment and excitation-energy-transfer behavior?**

The proposal deliberately does not assume that acclimation must change
acpPC oligomerization, pigment stoichiometry, subunit composition, or
chromophore geometry. These are candidate mechanisms to be tested.

## 1.3 The *Acaryochloris marina* phycobilisome

Phycobilisomes are large bilin-containing antenna complexes found in
cyanobacteria and red algae [@adir2020]. Their modular architecture
allows substantial remodeling in response to nutrient availability and
environmental conditions.

*A. marina* MBIC11017 is an unusually informative host for this
question. The genus lost phycobiliprotein genes in its common ancestor;
MBIC11017 alone reacquired them by horizontal gene transfer, together
with the genes for PC **disassembly**, and these genes have since been
reintegrated into an ancestral light-responsive regulatory network
[@miller2021; @ulrich2024; @yamamoto2022]. The reacquired phycocyanin
antenna gives this strain access to yellow--green wavelengths that
chlorophyll *d* cannot exploit and that its close relatives cannot use,
broadening its solar niche [@miller2021]. Recent biochemical and
ultrafast work shows that MBIC11017 adjusts PSI/PSII ratio and PBS
content under different light qualities without altering PBS
composition, and that the PBS transfers excitation primarily to PSII
[@oliver2025].

The AmPBS itself is a compact rod-like antenna assembled predominantly
from phycocyanin and associated linkers, with red-shifted fluorescence
and multiple PC isoforms suited to the chlorophyll-*d* context. It is
therefore a well-characterized, purifiable native substrate for studying
regulated antenna disassembly --- and its degradation machinery is,
uniquely, of recent horizontal origin.

## 1.4 NblA, NblB, and controlled PBS degradation

During nitrogen starvation and other stresses, cyanobacteria degrade
PBSs and recycle their nitrogen-rich phycobiliproteins. NblA is a small
protein central to this process. Structural, biochemical, and genetic
work established that NblA binds phycobiliproteins and can act as an
adaptor connecting PBS substrates to ATP-dependent Clp proteolysis
[@baier2014]. NblA proteins can also exhibit substrate specificity,
suggesting that PBS degradation is not a nonspecific collapse of the
antenna. Recent work on cyanophage-encoded NblA supports stepwise,
positionally ordered disassembly: peripheral rod discs are attacked
before more internal discs and the core, a pattern resolved by
proteomic mapping of cleavage sites [@nadel2025].

NblB is a homolog of bilin-lyase-related proteins and is also required
for normal PBS degradation. Levi and colleagues implicated NblB in
degradation of both PC and APC and provided cell-free evidence for
involvement in pigment removal, with NblB activity dependent on NblA
[@levi2018]. Hu and colleagues subsequently showed that the reaction
network is more complex: NblA and NblB can both influence PBS/PBP
dissociation, interact with apo- and holo-PBPs and bilin lyases, and
modulate chromophore attachment, detachment, and transfer. That study
did not detect direct NblA--NblB interaction [@hu2020].

Additional factors, including NblD, show that PBS degradation is a
multi-component process rather than a linear NblA→NblB→protease pathway
[@krauspe2021; @krauspe2022]. This proposal focuses on the
**NblA/NblB/PBS mechanistic module** without claiming it constitutes the
complete cellular pathway.

### Knowledge gap 2

> **How does AmNblA alter the molecular state of a native AmPBS, and how
> does that state determine the recruitment and/or activity of AmNblB on
> chromophorylated phycobiliproteins?**

Three aspects are particularly unresolved:

-   the molecular state of the PBS/PBP substrate recognized by NblB;
-   the structural determinants by which NblB recognizes and remodels
    that substrate;
-   how NblB activity can depend on NblA in the absence of evidence,
    from a single heterologous system, for a stable NblA--NblB binary
    complex. Whether such a complex exists in *A. marina* has not been
    tested and will be tested here rather than assumed either way.

# 2. Overall research objective

The overall objective is to determine how photosynthetic antenna
complexes reorganize in response to physiological demands by resolving
molecular transitions in two complementary pigment--protein systems.

Four linked objectives:

1.  **Establish and compare native membrane antenna preparations from
    five Symbiodiniaceae strains and define acpPC-containing biochemical
    phenotypes.**
2.  **Determine how chronic irradiance acclimation remodels acpPC
    organization and associated photophysical behavior.**
3.  **Determine how AmNblA remodels native AmPBS and whether it
    generates reproducible degradation-associated molecular states.**
4.  **Determine how AmNblB recognizes and remodels AmPBS-derived
    substrates and establish the structural basis of its activity.**

# 3. Central hypotheses

## 3.1 Dinoflagellate hypothesis

> **Chronic irradiance acclimation induces reproducible changes in the
> biochemical organization of membrane-bound acpPC complexes, modifying
> the energetic environment and organization of their bound chromophores
> and thereby altering spectral properties and
> excitation-energy-transfer behavior.**

This hypothesis does not specify a priori whether the dominant
remodeling variable is subunit composition, pigment occupancy,
oligomerization, association with photosystems, or chromophore geometry.

## 3.2 Cyanobacterial hypothesis

> **AmNblA-dependent remodeling of AmPBS generates or enriches
> phycobiliprotein substrate states that determine the recruitment
> and/or activity of AmNblB, and the lyase-related architecture of
> AmNblB enables recognition and remodeling of chromophorylated PBPs in
> those states.**

The hypothesis is stated positively, as a substrate-state coupling
model, and is deliberately agnostic about the route by which coupling
occurs. A stable AmNblA--AmNblB complex is not assumed, but neither is
its absence: direct interaction in *A. marina* is an explicit competing
model and is tested in Aim 4A. Substrate-state coupling and direct
association are not mutually exclusive.

Competing models retained explicitly:

-   **Sequential substrate remodeling:** AmNblA generates a state
    subsequently preferred by AmNblB.
-   **Direct association:** AmNblA and AmNblB form a detectable complex
    in *A. marina*, contrary to the heterologous result.
-   **Simultaneous/substrate-mediated cooperation:** the two act
    together through a transient PBP-associated assembly.
-   **Parallel activity:** they remodel different properties of the PBS
    with limited mechanistic dependence in the purified system.
-   **Extended system:** full bilin remodeling requires additional
    components such as bilin lyases or other degradation factors.

## 3.3 Operational definition of "reproducible"

Because "reproducible molecular state" is load-bearing throughout, it is
defined once here and used consistently.

A remodeled state is treated as **reproducible** when the difference
from the reference state (i) is observed in at least three independent
biological preparations, (ii) exceeds the pooled within-condition
variation of the corresponding control by a pre-specified margin, and
(iii) is detected by at least two orthogonal readouts (for example, a
mass-photometry population shift together with a spectral or
compositional change). Effect-size thresholds per readout will be fixed
after the variance-estimation experiments in Aims 1 and 3 and recorded
before the comparative datasets are collected.

# 4. Research systems and preliminary data

## 4.1 Symbiodiniaceae strains

Five strains derived from the Xiang collection and supplied by Prof.
Tingting Xiang (Department of Bioengineering, University of California,
Riverside) are maintained in culture:

  Strain   Species
  -------- ------------------------------
  SSA01    *Symbiodinium linucheae*
  SSA02    *Symbiodinium necroappetens*
  SSA03    *Symbiodinium pilosum*
  SSB01    *Breviolum minutum*
  SSE01    *Effrenium voratum*

The originating collection was developed as clonal axenic material
[@xiang2013]. Axenicity of the present working cultures will be checked
by plating on organic-rich marine medium and by 16S rRNA amplification
at the start of the acclimation experiments, since bacterial load could
otherwise confound both growth phenotypes and proteomic assignment.

### Preliminary observations

-   All five strains established and maintained in culture.
-   Cultures scaled to volumes sufficient for biochemical work.
-   Growth followed by OD$_{750}$.
-   Whole-culture absorption and fluorescence spectra obtained.
-   Direct isolation of thylakoids, membrane antenna fractions, or
    acpPC-enriched complexes has **not yet been demonstrated**; this is
    the first experimental milestone.

**Figure 1. \[TO BE INSERTED\]** Whole-culture absorption and
fluorescence spectra of SSA01, SSA02, SSA03, SSB01, and SSE01.

These spectra are whole-cell phenotypes. No signal will be assigned to
acpPC without biochemical separation.

### Sequence resources

Subunit-level identification of acpPC by proteomics requires a
strain-appropriate reference. Genome or transcriptome coverage differs
substantially across the five strains, and the acpPC family is large and
includes polyproteins [@boldt2012]. Available references will be
compiled per strain before the proteomic work, and where a strain lacks
adequate coverage, identification will rely on de novo/homology-based
assignment against the published PSI--AcpPCI subunit sets
[@zhao2024; @li2024], with reduced subunit-level resolution stated
explicitly rather than glossed.

## 4.2 Cyanobacterial preliminary system

Preliminary and unpublished Harris-laboratory work provides the
foundation for the cyanobacterial aims. Available material: purified
native AmPBS; purified AmNblA; purified recombinant AmNblB.

Previous work in the laboratory (M. [surname], MSc thesis, Technion,
[year] --- to be cited formally) demonstrated that different NblA
proteins produce markedly different PBS-disassembly phenotypes and
PBP-interaction profiles: NblA1 showed broad PBP association and
extensive disassembly, whereas NblA2 was biased toward peripheral
phycoerythrin-containing regions in the marine system examined. This is
preliminary evidence that NblA identity encodes substrate selectivity
and extent of remodeling. The molecular basis of AmNblA specificity
remains unresolved.

AmNblB crystallization has produced crystals in the laboratory.
Diffraction, dataset and refinement status are not yet established and
no structure is assumed anywhere in this proposal. Resolving this status
is the first action item of Aim 4B (see §11).

# 5. Research plan

## Chapter I --- Comparative biochemical organization of Symbiodiniaceae membrane antennae

### Aim 1. Define the baseline biochemical organization and diversity of acpPC-containing membrane antennae across five Symbiodiniaceae strains

Development of a reproducible isolation workflow is the first
experimental objective of this Aim, not its scientific endpoint. The
endpoint is a comparative description of what native membrane antenna
material each strain contains under a common reference condition.

#### Rationale

High-resolution structures show that AcpPC proteins form extensive
membrane-associated antenna systems around dinoflagellate photosystems
[@zhao2024; @li2024]. Comparative biochemical characterization across
the five available Symbiodiniaceae strains is lacking. Before
irradiance-dependent remodeling can be interpreted, it is necessary to
establish what membrane antenna material can be reproducibly isolated
from each strain under a common reference condition.

#### Experimental strategy

Cells from each strain will be harvested under defined reference growth
conditions. The workflow will be built in the order in which it can
fail:

1.  **Cell disruption.** Symbiodiniaceae are mechanically robust
    (amphiesmal plates, high polysaccharide content). Bead-beating,
    French press and nitrogen cavitation will be compared, with
    disruption efficiency scored by microscopy and by chlorophyll
    release, before any downstream step is optimized. This is the
    highest-probability point of failure and is therefore addressed
    first.
2.  **Membrane/thylakoid enrichment**, with differential and
    sucrose-density centrifugation.
3.  **Mild detergent solubilization**, informed by published
    dinoflagellate membrane-complex and PSI--antenna purification
    [@jovine1995; @kato2020; @zhao2024].
4.  **Separation of major pigment--protein populations** (sucrose
    gradients, clear-native/blue-native PAGE, size-exclusion
    chromatography).
5.  **Identification of acpPC-containing fractions** using complementary
    biochemical and spectroscopic evidence.

Sucrose-density separation, native electrophoresis, SDS-PAGE,
absorption/fluorescence spectroscopy, HPLC pigment analysis, proteomics
and ÄKTA/FPLC are the candidate tools; their exact order and conditions
will be determined empirically.

#### Internal control

Soluble PCP is straightforward to recover from the same cells and has
well-defined spectroscopic properties. PCP recovery will be used as a
positive control for the extraction, pigment-analysis and spectroscopy
pipeline, so that failure to recover acpPC can be distinguished from
failure of the analytical chain.

#### Identification criteria

A fraction will not be designated "acpPC" on the basis of color or
fluorescence alone. Identification should combine, where feasible:
protein composition; pigment composition; spectral properties; apparent
molecular/oligomeric state; and comparison with published
acpPC/PSI--AcpPCI information.

#### Expected outcome

A reproducible biochemical map of membrane pigment--protein fractions
for each strain, and identification of fractions suitable for
comparative acpPC analysis.

#### Alternative outcomes

If intact acpPC complexes cannot be maintained during isolation, the
project will distinguish failure of extraction from genuine biological
absence by varying detergent identity and concentration, ionic strength,
membrane preparation and separation method. If photosystem-bound and
free antenna populations cannot initially be separated cleanly, the
first comparative unit will be an acpPC-enriched membrane fraction
rather than a purified molecular species; this is an acceptable and
pre-declared fallback, not a failure.

#### Decision criterion for Chapter II

A strain/condition advances to mechanistic analysis when an
acpPC-containing preparation can be generated in three independent
preparations and compared using at least two orthogonal readouts, per
the reproducibility definition in §3.3.

## Chapter II --- Irradiance-dependent remodeling of acpPC

### Aim 2. Determine how chronic irradiance acclimation changes acpPC biochemical and photophysical states

#### Rationale

Symbiodiniaceae acclimate to changes in photon flux, with
species-specific changes in chlorophyll--protein complexes and pigment
composition [@iglesiasprieto1997]. High-light experiments implicate
membrane antennae, including acpPC, in photoprotective quenching
[@kanazawa2014]. What remains unclear is whether chronic acclimation
produces reproducible biochemical remodeling of native acpPC complexes
and whether such remodeling differs among Symbiodiniaceae lineages.

#### Experimental design

**Irradiance design.** A light-response pilot will bracket three
growth-permissive conditions per strain --- low, reference and high ---
at a fixed photoperiod and temperature. Absolute photon flux densities
will be fixed experimentally rather than imposed, because the
growth-permissive range differs among these species; historical
conditions from the Symbiodiniaceae photoacclimation literature
[@iglesiasprieto1997] serve as pilot anchors, not as justification for
applying identical treatments to all five strains. The pilot fixes the
high condition as the highest irradiance supporting stable exponential
growth in the most sensitive strain, and the low condition as the lowest
supporting adequate biomass yield.

**Acclimation criterion.** Cultures are treated as acclimated when
growth rate and Chl *a*-normalized absorption spectra are stable across
consecutive sampling points, after a number of generations at the target
irradiance to be set from the pilot growth curves.

**Replication.** A minimum of three independent biological replicates
per strain × irradiance, with the culture as the statistical unit;
replicate number will be revised upward for any comparison whose pilot
variance indicates insufficient power.

Culture-level screen readouts: growth/OD$_{750}$; flow-cytometric
scatter and red autofluorescence; microscopy where informative;
whole-culture absorption and fluorescence. Flow cytometry is a
high-throughput phenotypic readout, not evidence of acpPC molecular
state.

After acclimation, membrane antenna preparations will be generated using
the Aim 1 workflow. Comparative analysis will test candidate remodeling
variables: acpPC abundance; subunit composition; pigment
composition/occupancy; oligomeric or higher-order state; association
with larger photosynthetic complexes; absorption/fluorescence
properties; excitation-energy-transfer behavior.

The five-strain screen is not intended to support equally deep analysis
of all strain × irradiance combinations. Two or three informative
contrasts will be selected for mechanistic follow-up on the basis of
reproducibility and the magnitude and type of molecular phenotype.

**Working mechanistic model**

$$
\text{irradiance acclimation} \rightarrow \text{acpPC biochemical remodeling} \rightarrow \text{altered chromophore environment/organization} \rightarrow \text{altered spectral and EET behavior}
$$

Every arrow is testable; none is assumed.

#### Mechanistic follow-up and a go/no-go on energy transfer

Selected contrasts will be investigated using proteomics, pigment HPLC,
chromatography, fluorescence spectroscopy and structural approaches
where justified.

The final arrow of the model requires time-resolved fluorescence
(TCSPC and/or ultrafast transient absorption). **Confirming access to a
time-resolved capability is a go/no-go item to be resolved in year 1**,
because it determines whether Chapter II can answer its own question. If
in-house access is unavailable, options in priority order are: (i) a
Technion collaboration; (ii) an external collaboration with a
photosynthesis ultrafast laboratory; (iii) restriction of Chapter II
claims to steady-state spectral and biochemical phenotypes, with the EET
arrow stated as an untested prediction. Option (iii) is survivable but
weakens the chapter and should not be the default.

#### Falsification and alternative interpretation

The hypothesis is weakened if stable irradiance acclimation produces
reproducible whole-cell physiological change but no reproducible
difference in acpPC composition, organization or photophysics under
validated isolation conditions. Such a result remains informative:
acclimation may instead be dominated by antenna abundance,
reaction-center regulation, xanthophyll-cycle activity or other cellular
processes.

## Chapter III --- Generation of degradation-associated AmPBS states by AmNblA

### Aim 3. Determine whether AmNblA generates reproducible molecular states of native AmPBS

#### Rationale

NblA is established as a central PBS-degradation factor that binds PBP
substrates and recruits Clp machinery [@baier2014], and recent
phage-NblA work shows that disassembly can proceed in a positionally
ordered, stepwise fashion [@nadel2025]. Preliminary
Harris-laboratory results support differential substrate/disassembly
behavior among NblA proteins. The molecular state generated by AmNblA on
native AmPBS is not defined.

This chapter avoids presupposing a specific "partially disassembled"
intermediate. An AmNblA-remodeled state, denoted AmPBS\*, is defined
operationally from experimental evidence.

#### Operational definition of AmPBS\*

AmPBS\* is defined as a **reproducible AmNblA-dependent change (per
§3.3) in the molecular and/or spectroscopic state of AmPBS that is
distinguishable from untreated AmPBS and can subsequently be tested as a
substrate for AmNblB**. Its molecular identity is an experimental
outcome, not an assumption.

#### Initial reconstruction

$$
\text{AmPBS} \quad \text{vs.} \quad \text{AmPBS} + \text{AmNblA}
$$

followed by concentration- and time-dependent series. A first
sample-budget calculation from available AmPBS stock will be performed
before assay design, since it constrains how many conditions and
replicates are affordable; this calculation is the first task of Aim 3.

#### Readouts

**Mass photometry (Refeyn TwoMP).** Tests whether AmNblA treatment
redistributes AmPBS-derived particle populations. The objective is not
detection of free AmNblA but identification of changes in native antenna
assemblies and candidate intermediates.

**Fluorescence spectroscopy (Jobin Yvon Fluorolog-3).** Steady-state
excitation/emission spectroscopy determines whether AmNblA-dependent
structural changes are accompanied by changes in PCB/PBP photophysical
state.

**Biochemical separation and composition.** Native separation, density
gradients, electrophoresis, chromatography and proteomics will determine
the composition of reproducible states. Where a state appears
positionally ordered (rod-distal versus core), proteomic cleavage/
composition mapping following the approach used for phage NblA
[@nadel2025] will be used to test that ordering directly.

#### Possible outcomes

**A --- discrete molecular intermediates.** Reproducible particle
populations emerge after AmNblA treatment; these become candidate
substrates for Aim 4.

**B --- heterogeneous disassembly.** Broad fragmentation without stable
intermediates; NblB experiments then address substrate distributions
rather than a single AmPBS\* species.

**C --- local remodeling without major mass change.** Fluorescence or
biochemical changes without a large TwoMP shift, indicating altered
interfaces, pigment coupling or accessibility.

**D --- no reproducible effect under validated conditions.** The
hypothesis that isolated AmNblA generates a measurable AmPBS
intermediate is weakened, and simultaneous or multi-component mechanisms
gain priority.

## Chapter IV --- Structural and biochemical mechanism of AmNblB

### Aim 4. Determine how AmNblB recognizes and remodels AmPBS-derived substrates

#### Rationale

NblB is required for normal PBS degradation and is implicated in
PBP/bilin remodeling [@levi2018]. Its homology to bilin-lyase-related
proteins suggests a connection to chromophore chemistry, but available
data do not support a simple autonomous reverse-lyase model: NblA and
NblB influence multiple lyase/PBP reactions, and direct NblA--NblB
binding was not detected in the Hu et al. system [@hu2020]. The
mechanistic question is not whether NblB "removes PCB" but **what
substrate state NblB recognizes and what transformation it promotes**.

### Aim 4A. Test substrate-state dependence of AmNblB activity

Core experimental matrix:

$$
\begin{array}{ll}
\text{A} & \text{AmPBS} \\
\text{B} & \text{AmPBS} + \text{AmNblA} \\
\text{C} & \text{AmPBS} + \text{AmNblB} \\
\text{D} & \text{AmPBS} + \text{AmNblA} + \text{AmNblB} \\
\text{E} & \text{AmPBS} \xrightarrow{\text{AmNblA pretreatment}} \text{AmPBS}^* + \text{AmNblB}
\end{array}
$$

Concentrations, stoichiometries, incubation times and temperatures
follow from the Aim 3 optimization and sample budget.

**Direct interaction test.** In parallel, AmNblA--AmNblB association
will be tested directly in the *A. marina* proteins by pull-down, mass
photometry co-analysis and chemical crosslinking with MS identification.
This is inexpensive, has not been done in this organism, and converts an
inherited negative result into a tested claim.

**Required controls.** Separating substrate remodeling from Clp-adaptor
recruitment requires a separation-of-function AmNblA mutant. Such a
mutant will be developed, prioritizing residues implicated in ClpC
recruitment --- the NblA C-terminus in characterized homologs --- while
experimentally confirming retention of AmPBS/PBP binding. Retention of
binding is a required, verified property of any mutant used, not an
assumed consequence of the mutation; if no candidate satisfies both
conditions, the dependence will instead be probed by titration and by
order-of-addition rather than by a mutant. A structurally intact but
function-deficient AmNblB control follows from Aim 4C.

#### Model discrimination

**Model 1 --- sequential substrate remodeling**

$$
\text{AmPBS} \xrightarrow{\text{NblA}} \text{AmPBS}^* \xrightarrow{\text{NblB}} \text{AmPBS}^{**}
$$

*Prediction:* NblA-pretreated AmPBS responds differently to AmNblB than
untreated AmPBS (E ≠ C).

**Model 2 --- direct association.** *Prediction:* a detectable
AmNblA--AmNblB species in the interaction assays, and a D-condition
phenotype that pretreatment cannot reproduce.

**Model 3 --- simultaneous/substrate-mediated cooperation.**
*Prediction:* D produces a state not reproduced by E, without a
detectable binary complex.

**Model 4 --- parallel activity.** *Prediction:* AmNblB effects are
largely independent of prior AmNblA treatment (C ≈ E).

**Model 5 --- missing-component dependence.** *Prediction:* the
three-component system fails to reproduce chromophore remodeling despite
individually active proteins, indicating a requirement for lyases or
additional machinery.

Mass photometry and Fluorolog measurements provide orthogonal assembly
and photophysical readouts throughout.

### Aim 4B. Determine the structural organization of AmNblB

Structural analysis generates mechanistic hypotheses; it is not an
endpoint.

The immediate action is to establish the status of existing AmNblB
crystals: screen for diffraction, and if diffraction is inadequate,
proceed to reproducible crystallization trials in parallel with a
cryo-EM/SEC-SAXS assessment of oligomeric state. Objectives:

-   establish the oligomeric and structural organization of AmNblB;
-   identify candidate PBP-interaction surfaces;
-   determine whether a lyase-like internal cavity is structurally
    conserved;
-   map residues previously implicated in NblB function onto the
    experimental structure;
-   compare AmNblB architecture with structurally characterized bilin
    lyases.

If crystallography does not yield a usable structure, structure
prediction and alternative experimental methods will be used;
computational models are treated as hypotheses, not structures
[@jumper2021]. Solution-state oligomeric information from mass
photometry and SEC-MALS is obtainable regardless of crystallographic
outcome and is sufficient to keep Aim 4C tractable.

### Aim 4C. Test structure-derived functional hypotheses

Candidate recognition/catalytic residues or surfaces will be tested by
targeted mutagenesis. A mechanistically useful mutant should (i) retain
global folding and oligomeric integrity, verified by circular dichroism
and mass photometry, and (ii) selectively alter substrate interaction or
remodeling. Wild-type and mutant AmNblB will be compared using the
substrate-state assays of Aims 3--4A:

$$
\text{structure} \rightarrow \text{candidate determinant} \rightarrow \text{mutation} \rightarrow \text{assembly/spectroscopic phenotype}
$$

rather than docking alone.

### Aim 4D. Determine the fate of the bilin chromophore

Fluorescence changes report pigment environment, coupling, quenching or
transfer but **cannot prove covalent chromophore detachment**. An
orthogonal analytical chain will distinguish: PCB covalently attached to
PBP; detached/free PCB; PCB transferred to another protein; and altered
pigment environment without detachment.

The planned chain, in increasing cost and specificity:

1.  **Zinc-enhanced bilin fluorescence of SDS-PAGE gels.** Zn²⁺ staining
    reports bilin that remains covalently bound to a polypeptide after
    denaturing electrophoresis. Loss of Zn-fluorescence from a band that
    is still present by Coomassie indicates loss or alteration of
    detectable covalently associated bilin under the assay conditions;
    appearance of Zn-fluorescence on a different polypeptide is
    suggestive of transfer. Neither observation is on its own proof of
    detachment, since altered bilin chemistry can reduce Zn-enhanced
    fluorescence without cleavage of the thioether linkage. This is
    inexpensive and serves as the primary routine screen; steps 3 and 4
    are what make a detachment or transfer conclusion chemically
    defensible.
2.  **Acid-urea extraction and absorption spectroscopy** of denatured
    PBP to quantify bound bilin per protein, and solvent extraction to
    recover free bilin.
3.  **Reverse-phase HPLC** of extracted chromophore, with
    absorption/fluorescence detection, to identify free PCB and any
    chemically modified species.
4.  **LC-MS/MS of tryptic chromopeptides** to localize the attachment
    site and confirm occupancy at specific cysteines, and to detect
    transfer acceptors.

This chain replaces the previous "method to be determined" and makes the
chapter's central claim falsifiable with in-house or readily accessible
capability.

# 6. Integration of the four chapters

The proposal deliberately uses two experimental systems rather than one
linear pathway. Integration occurs at three levels.

The dinoflagellate chapters ask:

$$
\text{environmental acclimation} \rightarrow \text{antenna reorganization} \rightarrow \text{modified excitation-energy behavior}
$$

The cyanobacterial chapters ask:

$$
\text{regulated degradation signal} \rightarrow \text{antenna substrate remodeling} \rightarrow \text{pigment/protein disassembly and recycling}
$$

**Biologically**, both are accessory pigment--protein antennae whose
organization is actively regulated rather than fixed: one by acclimatory
remodeling, the other by controlled destruction.

**Methodologically**, both arms rely on the same core --- native
separation, steady-state and time-resolved fluorescence, pigment
chemistry and proteomics --- so approaches developed in one arm inform
the other. Mass photometry is central to the soluble AmPBS system, where
particle sizes and sample behavior suit the method well. Whether it is
applicable to detergent-solubilized membrane pigment--protein complexes
is a separate question; it is listed as a candidate acpPC readout
contingent on demonstrated detergent compatibility, and is not part of
the claimed methodological symmetry until that is shown.

**Conceptually**, the common analytical logic is:

1.  define the native molecular state;
2.  apply a biologically meaningful perturbation;
3.  identify reproducible remodeled states;
4.  determine their biochemical/structural basis;
5.  connect molecular remodeling to pigment photophysics or degradation
    function.

This provides coherence without implying evolutionary homology between
acpPC and PBS systems.

# 7. Expected contributions

## 7.1 Symbiodiniaceae

-   a reproducible comparative workflow for native membrane antenna
    isolation across five Symbiodiniaceae strains;
-   biochemical characterization of acpPC-containing complexes beyond
    whole-cell spectral measurement;
-   evidence for or against strain-dependent acpPC remodeling during
    chronic irradiance acclimation;
-   mechanistic links between biochemical antenna state and
    spectral/EET behavior in selected contrasts.

## 7.2 Cyanobacteria

-   an operational molecular description of AmNblA-induced AmPBS
    remodeling;
-   a direct test, in *A. marina*, of whether NblA dependence of NblB
    arises through substrate-state remodeling or through association;
-   structural information on AmNblB and experimentally tested
    recognition hypotheses;
-   resolution of bilin fate by chemistry rather than inference;
-   a refined model of how protein disassembly and bilin remodeling are
    coordinated during PBS degradation, in the one organism whose PBS
    assembly and disassembly genes are of recent horizontal origin.

## 7.3 What will be known at the end that is not known now

Stated plainly, one question per arm: whether chronic light acclimation
is written into the molecular state of a dinoflagellate membrane antenna
or only into its abundance; and how AmNblA alters the molecular state of
AmPBS, and how that state determines the recruitment and/or activity of
AmNblB.

The second question is deliberately not posed as substrate-state versus
protein--protein interaction. Those are two of the five models in Aim
4A, and the experimental matrix is designed to discriminate among all
five rather than to adjudicate a dichotomy.

# 8. Significance

Antenna remodeling is fundamental to photosynthetic fitness because
photon capture must be balanced against photochemical capacity, nutrient
availability and photodamage risk. High-resolution structures
increasingly provide static views of photosynthetic complexes, but the
molecular transitions connecting those structures to acclimation and
degradation remain less well resolved.

The proposed work addresses this at two scales. In Symbiodiniaceae, it
tests how chronic environmental acclimation is encoded in the
biochemical state of a membrane antenna central to coral-associated
dinoflagellate photosynthesis --- a system of direct relevance to how
symbionts respond to light stress. In cyanobacteria, it reconstructs a
regulated antenna-degradation module from purified native and
recombinant components and asks how a degradation substrate is generated
and then recognized.

A broader outcome is an experimentally grounded framework for treating
photosynthetic antennae as ensembles of regulated molecular states
rather than fixed structures.

# 9. Feasibility and available infrastructure

## Biological material

-   Five cultured Symbiodiniaceae strains: available.
-   Native AmPBS, AmNblA, AmNblB: available.

## Instrumental and methodological access

Available within the Harris laboratory and/or Technion infrastructure:
protein expression and purification; ÄKTA/FPLC; HPLC; gel
electrophoresis and standard protein biochemistry; proteomics; Refeyn
TwoMP mass photometry; Jobin Yvon Fluorolog-3 fluorescence spectroscopy
(280--900 nm, temperature-controlled holder); flow cytometry;
microscopy; crystallization and structural biology infrastructure;
cryo-EM access.

## Capabilities requiring confirmation

| Capability | Needed for | Status | Fallback |
| :--- | :--- | :--- | :--- |
| Time-resolved fluorescence (TCSPC/ultrafast) | Chapter II EET claims; AmPBS trapping | To confirm, year 1 | Collaboration; else restrict claims to steady-state |
| LC-MS/MS chromopeptide analysis | Aim 4D | To confirm with proteomics unit | Zn-fluorescence + HPLC only |
| Cryo-EM time/scheduling | Aim 4B fallback | To confirm | Crystallography + SEC-SAXS |
| Strain-matched sequence references | Aim 1/2 proteomics | Partially available | Homology assignment, stated resolution limits |

# 10. Risks, limitations, and alternative strategies

## 10.1 Cell disruption may limit the entire dinoflagellate arm

Symbiodiniaceae are mechanically robust and rich in polysaccharides and
phenolics. If no disruption method yields intact membranes at workable
yield, the acpPC arm cannot proceed as designed. This is addressed
first, with three independent methods trialed and a quantitative
efficiency criterion, before downstream optimization begins.

## 10.2 acpPC isolation may perturb native organization

Detergent solubilization can alter higher-order antenna organization.
Increased purity will not be equated with increased biological
relevance. Multiple detergent/separation conditions and less-disrupted
membrane fractions will be compared.

## 10.3 Five strains create excessive combinatorial scope

The panel is for comparative screening. Deep structural and
photophysical work will focus on two to three informative contrasts
selected from the screen.

## 10.4 Whole-cell optical phenotypes are not acpPC-specific

Culture absorption, fluorescence and flow cytometry give phenotypic
context but cannot establish acpPC molecular mechanism without
fractionation.

## 10.5 Proteomic identification depends on sequence resources

acpPC is a hyperdiverse family with polyprotein precursors [@boldt2012],
and reference coverage differs among the five strains. Where coverage is
inadequate, subunit-level claims will be downgraded to family-level
claims explicitly.

## 10.6 Mass photometry has a lower molecular-mass limit

TwoMP will be used for PBS-derived assemblies and complexes rather than
free NblA or small isolated proteins.

## 10.7 Fluorescence does not prove chromophore detachment

Spectral changes are interpreted as photophysical-state changes until
the Aim 4D chemical chain establishes chromophore fate.

## 10.8 NblA/NblB may be insufficient for complete reconstruction

PBS degradation involves bilin lyases, proteases and NblD-related
pathways [@hu2020; @krauspe2021; @krauspe2022]. Failure of the minimal
purified system will be used to identify missing biochemical
requirements rather than treated as failure of the hypothesis.

## 10.9 AmNblB crystals may not diffract

Structural information is desirable but Aim 4C can proceed from
prediction-guided mutagenesis combined with experimentally determined
oligomeric state, provided every structure-derived hypothesis is tested
functionally.

# 11. Work plan

Timing is provisional and assumes a four-year programme. The
cyanobacterial arm front-loads deliverable results while the
dinoflagellate workflow is being established, which balances risk across
the thesis.

| Period | Cyanobacterial arm | Dinoflagellate arm |
| :--- | :--- | :--- |
| Y1 H1 | AmNblB crystal/diffraction status; AmPBS sample budget; AmPBS + AmNblA baseline (MP, fluorescence) | Cell-disruption trials; PCP control pipeline; light-response pilot |
| Y1 H2 | AmPBS\* definition; direct NblA--NblB interaction tests | Membrane enrichment and solubilization screen; confirm time-resolved access |
| Y2 | Aim 4A matrix; AmNblA control mutant | Aim 1 workflow fixed; acclimation experiment run |
| Y3 | AmNblB structure/oligomeric state; mutagenesis | Comparative acpPC analysis; contrast selection |
| Y4 | Aim 4D chromophore fate; integration | Mechanistic follow-up on selected contrasts; integration |

Dependency structure:

1.  establish reproducible Symbiodiniaceae membrane/acpPC workflow;
2.  establish irradiance acclimation screen;
3.  select mechanistically informative acpPC contrasts;
4.  characterize AmNblA-dependent AmPBS remodeling;
5.  establish NblB substrate-state assay;
6.  integrate AmNblB structural information with mutagenesis and
    functional assays;
7.  resolve chromophore fate using an orthogonal analytical method.

# 12. Candidate's contribution

All experimental work described in Chapters I--IV will be carried out by
the candidate. Prior Harris-laboratory results are used as starting
material and are identified as such throughout: the purified AmPBS,
AmNblA and AmNblB preparations, the existing AmNblB crystallization
condition, and the earlier thesis work on NblA substrate selectivity.
The five Symbiodiniaceae strains were supplied by Prof. Tingting Xiang;
all culture, acclimation and biochemical work on them is the candidate's
own. Time-resolved spectroscopy, if obtained through collaboration, will
be acknowledged as such with the candidate responsible for sample
preparation, experimental design and analysis.

---

# Appendix A --- Internal working register (not for submission)

*This appendix is working material for the candidate and supervisor. It
should be removed before the proposal is submitted.*

## A.1 Open decisions

| Item | Status | Why it matters |
| :--- | :--- | :--- |
| Final thesis title | Open | Must cover all four chapters |
| Required proposal length/format | Open | Determines final compression |
| Axenicity of current cultures | To test at start of Aim 2 | Confounds growth and proteomics |
| Final irradiance values | Open; low/reference/high bracket defined, PFDs from pilot | Committee will ask; must be empirical, not imposed |
| Acclimation criterion | Open; stability of growth rate + Chl a-normalized spectra | Generation count set from pilot growth curves |
| Replicate number | Minimum n=3 cultures, power-revised | Statistical unit = culture; fixed after pilot variance |
| Final acpPC isolation protocol | Aim 1 objective | — |
| Primary comparative acpPC unit | Open | Free vs PSI-associated vs enriched fraction |
| Mass photometry / detergent compatibility | Untested for acpPC | Determines whether MP is an acpPC readout at all |
| Time-resolved EET access | **Go/no-go, year 1** | Determines Chapter II scope |
| AmPBS sample budget | First task of Aim 3 | Constrains assay design |
| AmNblA separation-of-function mutant | Requirement defined, phenotype not assumed | Binding retention must be verified, not predicted |
| AmNblB diffraction status | First task of Aim 4B | No structure assumed |
| Thesis citation for prior lab work | Needs full formal reference | Currently informal |

## A.2 Evidence discipline

Three levels are distinguished throughout: **published evidence**
(peer-reviewed, checked against primary literature and structural
databases before submission); **preliminary/unpublished evidence**
(Harris-laboratory results, labeled as such); and **proposed
mechanisms** (hypotheses and predicted intermediates, written as
testable models).

## A.3 Novelty audit --- current position

1.  Photoacclimation in Symbiodiniaceae is established background, not
    the novelty claim.
2.  acpPC architecture is no longer broadly unknown: two independent
    2024 cryo-EM efforts provide PSI--AcpPCI reference architectures
    [@zhao2024; @li2024].
3.  Oligomerization is a candidate mechanism, not the presumed one;
    purification itself can alter assembly state.
4.  The principal dinoflagellate gap is the missing bridge from chronic
    acclimation to native molecular antenna state, and from that state
    to pigment energetics.
5.  **New since the previous audit, and favorable.** Oliver, Elias &
    Croce [@oliver2025] show physiological, light-quality-driven
    remodeling of PBS abundance and excitation trapping in MBIC11017,
    but do not address the NblA/NblB degradation mechanism. Ulrich &
    Miller [@ulrich2024] establish evolutionary and regulatory
    assimilation of the reacquired PC system --- including its
    disassembly genes --- without resolving the molecular degradation
    mechanism. Both therefore sharpen the contemporary biological
    context for Chapters III--IV rather than threatening their novelty.
    Nadel et al. [@nadel2025] provide a methodological precedent for
    defining ordered disassembly states by proteomics; it is a Technion
    paper and should be engaged with directly.

Current novelty formulation:

> **Connect chronic irradiance acclimation to the biochemical state of
> native acpPC-containing membrane antennae across multiple
> Symbiodiniaceae strains; and determine, in the one cyanobacterium
> whose phycobilisome assembly and disassembly machinery is of recent
> horizontal origin, how NblA alters the molecular state of the
> phycobilisome and how that state governs NblB recruitment and
> activity.**

Repeat the novelty search immediately before submission.

## A.4 Bibliography notes

`Technion_Era.bib` is the master bibliography. Before submission:
consolidate duplicates; verify DOI/title/year; Zotero-local `file=`
fields are irrelevant to Overleaf; add recent primary literature where
it changes the state of the field; run dedicated final searches on NblB
structure and acpPC remodeling.

**Citation keys used here that need to be added or corrected:**

-   `@iglesiasprieto1997` --- replaces the malformed `@iglesias-prieto`
    (no year), which will not compile.
-   `@li2024` --- Li et al. (2024), Structures and organizations of
    PSI--AcpPCI supercomplexes from dinoflagellates, *PNAS*
    121:e2315476121, doi:10.1073/pnas.2315476121.
-   `@boldt2012` --- Boldt, Yellowlees & Leggat (2012), Hyperdiversity
    of genes encoding integral light-harvesting proteins in
    *Symbiodinium*, *PLoS ONE* 7:e47456,
    doi:10.1371/journal.pone.0047456.
-   `@miller2021` --- Reacquisition of light-harvesting genes in a
    marine cyanobacterium, *Current Biology* 31:1539--1546.e4.
-   `@ulrich2024` --- Ulrich & Miller (2024), Integration of
    horizontally acquired light-harvesting genes into an ancestral
    regulatory network in *A. marina* MBIC11017, *mBio* 15(12),
    doi:10.1128/mbio.02423-24.
-   `@oliver2025` --- Oliver, Elias & Croce (2025), Acclimation to white
    light in a far-red light specialist: insights from *Acaryochloris
    marina* MBIC11017, *New Phytologist* 247(1):128--143,
    doi:10.1111/nph.70188.
-   `@nadel2025` --- Nadel et al. (2025), Viral NblA proteins negatively
    affect oceanic cyanobacterial photosynthesis, *Nature*
    648:434--442, doi:10.1038/s41586-025-09656-x. A Technion paper;
    worth engaging with directly and, if appropriate, as an internal
    methodological contact for the proteomic cleavage-mapping approach.
-   `@yamamoto2022` --- Yamamoto et al. (2022), Comparative genomic
    analysis of *A. marina* MBIC10699, *Microorganisms* 10:1374,
    doi:10.3390/microorganisms10071374. Supports reacquisition of the
    PBP gene cluster and establishes MBIC10699 as the closely related
    PBP-lacking comparison strain.

# References

References are managed in `Technion_Era.bib`. Citation keys are retained
in Pandoc/Obsidian form for migration to Overleaf/BibTeX.
