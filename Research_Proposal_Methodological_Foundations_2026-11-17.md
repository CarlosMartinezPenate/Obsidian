# Methodological foundations for investigating photosynthetic antenna systems

**Working expansion for discussion — 17 November 2026**

Companion to *Molecular Organization and Regulation of Photosynthetic Antenna Systems*. This draft develops the physical and chemical foundations of the proposed approaches. It includes a condensed chromatography section so that the discussion is self-contained. Crystallography is included as a complementary route relevant to the AmNblB crystals already obtained; its inclusion in the final proposal remains an editorial choice. Instrument-specific operating settings belong in the Methods once established.

## 1. Connecting molecular organization to experimental observables

Photosynthetic antenna function depends on several levels of organization: pigment chemistry, the local environment imposed by the apoprotein, interactions between pigments, and the association of subunits into larger assemblies. These levels are related but experimentally distinguishable. An antenna can retain its constituent proteins while losing excitation-energy transfer, or undergo subunit dissociation without immediate destruction of its chromophores. Conversely, altered fluorescence can arise from quenching or changes in pigment environment without detectable changes in particle mass. A mechanistic investigation therefore requires complementary measurements of composition, assembly, optical behavior, and structure.

In Chapter 1, this approach will connect the biochemical isolation of Symbiodiniaceae antenna fractions to their molecular organization. In Chapter 2, it will distinguish changes in native *Acaryochloris marina* phycobilisomes (AmPBS) induced by AmNblA and AmNblB. The central interpretive task will be to determine which molecular changes account for an observed signal, while identifying alternative explanations that the measurement alone cannot exclude.

## 2. Chemical conditions that preserve—or alter—antenna assemblies

Isolation changes the environment in which an antenna is stable. Protein interfaces depend on hydrophobic interactions, electrostatics, hydrogen bonding, and other noncovalent contacts, while pigments can be coordinated or otherwise constrained within specific binding sites. Buffer composition is consequently part of the experimental model: it can preserve an assembly, shift its association equilibrium, or generate an apparent biological transition during handling.

The protonation of ionizable groups depends on pH. For a simple acid–base pair, the Henderson–Hasselbalch relationship is

\[
\mathrm{pH}=\mathrm{p}K_a+\log_{10}\frac{[\mathrm{A^-}]}{[\mathrm{HA}]}.
\]

This concentration form approximates the activity relationship under suitable solution conditions. A buffer is most effective near its relevant pKa, but buffering capacity also depends on total concentration. Changes in protonation can alter protein surface charge, pigment ligation, and interface stability. Because buffer pKa can vary with temperature, the temperature at which pH is measured matters when samples are subsequently handled cold.

Salt influences electrostatic interactions through ionic strength,

\[
I=\tfrac12\sum_i c_i z_i^2,
\]

where each ionic species contributes according to its concentration and squared charge. Thus, equal molar concentrations of different salts need not produce equivalent electrostatic conditions. Specific ion effects and phosphate speciation further limit simple comparisons. For AmPBS, a buffer exchange must therefore be assessed as a possible perturbation of the substrate itself, with a matched untreated control.

Membrane-associated acpPC and photosystem-containing fractions introduce an additional requirement: shielding hydrophobic surfaces after removal from the lipid bilayer. Detergents contain hydrophilic and hydrophobic regions and can form micelles above their critical micelle concentration (CMC). Solubilization produces mixtures of free detergent, micelles, lipid–detergent particles, and protein-associated detergent. The CMC is a useful solution property, but it does not specify a universally suitable extraction concentration. Extraction also depends on detergent identity, membrane loading, detergent-to-lipid ratio, exposure time, and temperature. [1,2]

For this project, detergent conditions will therefore be evaluated by the properties of recovered antenna fractions, including pigment retention, spectral behavior, and assembly distributions. A higher soluble yield will not by itself establish better preservation. Likewise, the size of a detergent-solubilized particle will include contributions from associated detergent and lipids, complicating comparisons with soluble PCP.

Dialysis and ultrafiltration address different aspects of sample preparation. Dialysis permits diffusible solutes to redistribute across a semipermeable membrane down their chemical-potential gradients; repeated external-buffer changes favor exchange of small solutes. Ultrafiltration uses pressure to drive solvent and permeating solutes through a membrane while concentrating retained material. A membrane's molecular-weight cutoff is nominal, rather than an exact boundary between molecular masses. Recovery and composition must therefore be checked experimentally. Detergent removal is especially nontrivial because monomers and micelles differ in permeability and exchange with one another. [1]

## 3. Chromatography: resolving hydrodynamic and electrostatic heterogeneity

An ÄKTA system provides controlled liquid delivery, sample introduction, detection, and fraction collection. The separation mechanism is determined by the column chemistry. Pumps establish flow and buffer composition; valves control the fluid path; detectors monitor properties such as absorbance and conductivity. Pressure reports resistance to flow and must remain compatible with both the column and instrument. A chromatographic peak is therefore a detector response from material leaving the column, rather than an intrinsic identification of a molecular species.

In size-exclusion chromatography (SEC), porous beads partition molecules according to their access to the pore volume. Larger hydrodynamic particles access less internal volume and elute earlier; smaller particles explore more pores and elute later. Elution can be expressed as

\[
K_{\mathrm{av}}=\frac{V_e-V_0}{V_t-V_0},
\]

where Ve is elution volume, V0 is void volume, and Vt is total bed volume under the stated convention. Within a column's fractionation range, suitable standards relate elution behavior to apparent size. However, SEC responds to hydrodynamic dimensions rather than directly to molecular mass. Molecular shape, hydration, and nonideal resin interactions can alter elution. [3]

The distinction can be understood through the Stokes–Einstein relationship,

\[
D=\frac{k_BT}{6\pi\eta R_h},
\]

which connects translational diffusion to hydrodynamic radius Rh for an equivalent sphere in a fluid of viscosity η. A long particle and a compact particle can have different Rh values despite similar masses. For acpPC-containing fractions, bound detergent and lipids further affect the particle's hydrodynamic behavior. Thus, an early-eluting pigmented fraction will motivate investigation of a larger assembly, but will not establish its stoichiometry. Column dilution may also shift reversible association equilibria, so the chromatogram describes material under the separation conditions. [4]

Ion-exchange chromatography instead exploits reversible electrostatic association with charged ligands on the stationary phase. An anion exchanger has positively charged groups that bind suitably anionic protein surfaces; a cation exchanger has negatively charged groups. A protein's isoelectric point provides an initial guide to its net charge at a given pH, but retention also depends on accessible charge patches, buffer composition, and conformation. Raising salt concentration commonly weakens retention through screening and competition, while changing pH changes the ionization of interacting groups. [5]

For antenna preparations, distinct retention profiles may reflect differences in protein composition, processing, pigment loading, or associated material. These are hypotheses to be tested in collected fractions. Sample conductivity must be compatible with the intended binding step; otherwise a protein may pass through despite a potentially suitable exchanger. Monitoring conductivity helps distinguish the programmed gradient from the solution conditions actually reaching the detector.

Pigment-sensitive absorbance channels can help locate antenna-containing fractions, while absorbance near 280 nm provides a broader signal from protein and other absorbing material. Neither signal alone establishes purity. Instrument configuration determines which channels are available. The fluid volume between detector and collection point also produces a delay between a recorded peak and its arrival in a tube; fraction assignment must account for that delay. Together, chromatography will provide physically separated populations for subsequent optical, compositional, and structural characterization.

## 4. Absorption spectroscopy: electronic transitions and pigment environments

Absorption occurs when incident light drives a transition between molecular energy states. Photon energy is related to wavelength by

\[
E=\frac{hc}{\lambda}.
\]

The conjugated electronic systems of chlorophylls, carotenoids, and bilins give rise to their visible absorption. Chlorophyll spectra include the lower-energy Q bands and higher-energy Soret region. Carotenoid absorption is dominated by strongly allowed transitions, whereas lower excited states can have weak optical transitions and still participate in energy transfer. Consequently, the absence of a strong absorption band does not imply that an excited state is biologically irrelevant. Peridinin provides a particularly relevant example because its excited-state behavior cannot be reduced to a single fluorescent donor state. [6]

For a homogeneous, sufficiently dilute sample with negligible scattering and suitable instrumental conditions, absorbance follows the Beer–Lambert relationship:

\[
A(\lambda)=-\log_{10}\frac{I(\lambda)}{I_0(\lambda)}
=\varepsilon(\lambda)c\ell.
\]

Here I0 and I are incident and transmitted intensities, ε is the molar extinction coefficient, c is concentration, and ℓ is optical path length. For noninteracting absorbers, component contributions are additive. In antenna assemblies, however, pigment environments and pigment–pigment interactions can change spectral positions, shapes, and intensities. An isolated-pigment spectrum therefore does not necessarily reproduce the spectrum of that pigment when protein-bound.

The absorbance instrument measures transmission through the sample relative to a reference. Loss of transmitted light can include scattering from aggregates, membranes, or large particles, so a sloping baseline cannot automatically be interpreted as pigment absorption. Matched blanks, appropriate path length, and measurements within the instrument's reliable absorbance range are essential. Dilution tests can reveal nonlinear behavior, although dilution itself may alter an unstable assembly.

In Chapter 1, spectra will be used to compare pigment-containing fractions and assess changes in their optical environments. Chlorophyll-band shifts or broadening may indicate altered interactions, but a blue shift alone will not uniquely diagnose detergent-induced uncoupling. Differences in composition, aggregation, or solution conditions must also be considered. Studies comparing PCP forms show why protein architecture and pigment arrangement must be considered together when interpreting spectra. [7,8]

In Chapter 2, changes in phycobiliprotein absorption will report changes in the ensemble of bilin chromophores and their environments. A decrease at one wavelength can reflect a shifted band rather than loss of pigment. Full-spectrum comparisons will therefore be more informative than a single absorbance trace. Pigment extraction into solvent, when used, can address pigment composition but removes much of the information about native pigment–protein coupling.

## 5. Fluorescence spectroscopy: competing excited-state pathways

After absorption, excitation can be lost through fluorescence, nonradiative relaxation, intersystem crossing, quenching, or transfer to another pigment. For a simple excited state with competing first-order pathways,

\[
\tau=\frac{1}{k_F+k_{\mathrm{nr}}+k_{\mathrm{ISC}}+k_{\mathrm{ET}}+\cdots},
\qquad
\Phi_F=\frac{k_F}{k_F+k_{\mathrm{nr}}+k_{\mathrm{ISC}}+k_{\mathrm{ET}}+\cdots}.
\]

The fluorescence lifetime τ and fluorescence quantum yield ΦF therefore depend on all competing pathways. Real antennae contain coupled pigments and heterogeneous populations, so these expressions provide a conceptual starting point rather than a complete kinetic model. Increased fluorescence can result from loss of transfer to an acceptor, whereas decreased fluorescence can result from improved transfer, additional quenching, photobleaching, or simply lower absorption.

An emission spectrum scans emitted wavelength at fixed excitation wavelength. An excitation spectrum scans the excitation wavelength while monitoring a selected emission wavelength or band. Monitoring chlorophyll emission while exciting in an accessory-pigment absorption region can reveal sensitized chlorophyll fluorescence. After correcting for instrumental response and accounting for overlapping direct chlorophyll excitation, this supports functional energy transfer. It does not, by itself, yield an exact transfer efficiency. PCP spectroscopy illustrates the value of comparing absorption, excitation, and emission measurements rather than interpreting an emission maximum alone. [7,9]

In the weak-coupling, point-dipole regime, Förster theory describes a transfer rate with a strong distance dependence:

\[
k_{\mathrm{ET}}=\frac{1}{\tau_D}\left(\frac{R_0}{r}\right)^6.
\]

The Förster distance R0 depends on spectral overlap, donor quantum yield, dipole orientation, and the refractive environment. This framework explains why pigment spacing and orientation can affect transfer. Its assumptions are not universally satisfied in densely packed antennae, where excitonic coupling, short-range interactions, and carotenoid-specific excited-state pathways may require other descriptions. [6,9]

A spectrofluorometer such as the Fluorolog-3 uses an excitation source, wavelength-selection optics, a sample compartment, emission-selection optics, and a detector. The exact optical and detector arrangement depends on the installed configuration. Slit widths determine spectral bandwidth and photon throughput: widening a slit increases signal but can blur spectral features. The scan step is the sampling interval, not the optical resolution. Integration time, detector response, and excitation intensity also influence signal quality and susceptibility to photobleaching. Manufacturer documentation should guide the eventual instrument-specific procedure. [10,11]

Corrections must address wavelength-dependent excitation intensity and detection sensitivity. Solvent Raman scattering and scattered excitation light can create features unrelated to pigment fluorescence. At elevated absorbance, the inner-filter effect reduces excitation penetration, while reabsorption preferentially removes some emitted wavelengths. These effects can distort intensity and spectral shape. Matched optical conditions and sufficiently low absorbance will be sought without assuming that dilution leaves all assemblies unchanged.

Steady-state fluorescence reports the integrated outcome of excited-state processes. Where suitable equipment is available, time-resolved measurements can help separate changes in population from changes in decay kinetics. Such measurements require an instrument response function and a kinetic model appropriate to the time scale. Nanosecond fluorescence measurements cannot automatically resolve ultrafast carotenoid-to-chlorophyll transfer. Neither steady-state intensity nor fluorescence lifetime alone is equivalent to photosynthetic photochemical efficiency.

## 6. Native and Deriphat-PAGE: mobility of pigment-containing assemblies

Electrophoresis separates charged particles in an electric field. In a simplified free-solution description, migration velocity is v = μE, where μ is electrophoretic mobility and E is field strength. Mobility depends on effective charge and friction; in a polyacrylamide gel, molecular sieving adds dependence on particle size and shape. A native-gel position is consequently not a direct molecular-mass measurement.

Native electrophoresis aims to retain associations that denaturing SDS-PAGE disrupts. However, “native” describes the separation conditions rather than proving preservation of the original cellular assembly. Buffer exchange, electric fields, detergent exposure, and dilution can affect fragile complexes. Blue-native electrophoresis uses a charge-shifting dye, whereas Deriphat-based approaches use a different detergent system. Their migration behavior and effects on pigment-containing particles should not be treated as interchangeable. Deriphat electrophoresis was developed to separate chlorophyll–protein complexes while limiting pigment dissociation under the tested conditions. [12,13]

For Chapter 1, pigmented bands will provide evidence that chromophores remain associated with electrophoretically resolved material. Reproducible discrete bands will support a limited set of apparent populations under those conditions, but a single band may contain co-migrating species. Excised bands can be analyzed by denaturing electrophoresis or proteomics to investigate their composition. Agreement with SEC and optical measurements will strengthen an assembly assignment.

For Chapter 2, treatment-dependent band shifts or loss of larger bands may support redistribution of AmPBS assemblies. Interpretation will require accounting for material retained in wells, precipitated material, and changes in staining or fluorescence. A fluorescent band becoming dimmer does not necessarily indicate fewer particles, because the fluorescence yield may have changed.

## 7. Mass photometry: interferometric detection of individual particles

Mass photometry detects light scattered by individual particles as they interact with a glass–solution interface. The measured intensity contains interference between a reference field Er and a particle-scattered field Es:

\[
I=|E_r+E_s|^2=|E_r|^2+|E_s|^2+2\operatorname{Re}(E_rE_s^*).
\]

For weak scatterers, the interference term makes small scattering signals detectable. Under calibrated conditions, scattering contrast is approximately proportional to protein mass. Event detection in recorded images produces contrast distributions that are converted to mass distributions using standards. The Refeyn TwoMP therefore measures a calibrated optical observable, rather than directly weighing freely diffusing molecules. [14]

Distinct populations can support different assembly states when their masses are resolvable and consistent with known composition. Peak width reflects both measurement uncertainty and possible heterogeneity; it should not automatically be interpreted as a distribution of biological stoichiometries. Calibration, buffer background, surface quality, sample concentration, and acquisition conditions must be controlled. Landing counts can also be biased by differences in surface interaction, limiting their interpretation as solution population fractions. [14]

Membrane antennae present additional complications. Detergent micelles can generate background, and particle contrast can include associated lipid or detergent. A calibration established for protein alone does not automatically give the protein-only mass of a mixed particle. Dilution used to obtain measurable events may also destabilize a complex or alter its association equilibrium. These issues have been demonstrated in applications of mass photometry to membrane proteins. [15]

In this project, mass photometry will test whether chromatographic fractions contain distinguishable particle populations compatible with candidate assemblies. Stoichiometric interpretation will require compositional evidence and an explicit treatment of associated nonprotein material. Suitability for detecting small isolated regulatory proteins will be established from the validated measurement range, rather than assumed from the ability to measure larger antenna particles.

## 8. LC-MS/MS: identifying proteins through peptide evidence

In bottom-up proteomics, proteins are digested into peptides, separated chromatographically, ionized, and analyzed by tandem mass spectrometry. Reversed-phase liquid chromatography commonly separates peptides according to their interactions with a hydrophobic stationary phase as solvent composition changes. Electrospray generates gas-phase ions, often carrying multiple charges. The mass analyzer measures mass-to-charge ratio, not mass alone. Fragmentation of selected or collectively acquired precursor ions then provides sequence-informative spectra.

Database searching compares measured spectra with candidate peptide sequences under defined assumptions about digestion, modifications, and mass accuracy. Identification confidence must be controlled at the relevant levels, including peptide-spectrum matches, peptides, and protein groups. A confident peptide assignment does not ensure an unambiguous protein assignment if several proteins contain that peptide. Shared-peptide ambiguity and quantitative interpretation are distinct problems. [16]

This distinction is central to the acpPC question. Closely related sequences may share many detectable peptides. A suitable sequence database and distinguishing peptide evidence will therefore determine whether a fraction can be assigned to a specific protein, several alternatives, or a protein group. Failure to observe a unique peptide will not establish absence of the corresponding protein. Precursor processing also means that detection of peptides from a predicted gene product may not determine the boundaries of the mature polypeptide present in an assembly.

Proteomics will identify constituents of purified fractions and gel bands, while chromatography and structural analysis will test their association. Co-detection in one fraction cannot alone establish membership in the same particle. Likewise, peptide signal intensity is affected by digestion, recovery, ionization, and detectability; raw intensity ratios are not direct subunit stoichiometries. Quantitative claims will require an appropriate acquisition and analysis strategy. More elaborate co-fractionation approaches illustrate how multiple separation profiles can improve inference beyond a single mixed sample. [17]

The LC separation used for proteomics is analytically distinct from ÄKTA purification of intact antenna complexes. Access to LC-MS/MS will therefore be described through the confirmed analytical facility and workflow, without implying that the laboratory's ÄKTA systems provide peptide mass spectrometry or pigment HPLC.

## 9. Cryo-electron microscopy: reconstructing heterogeneous assemblies

Single-particle cryo-EM examines particles embedded in thin vitrified aqueous films. Rapid cooling suppresses formation of crystalline ice, allowing hydrated particles to be imaged without requiring a protein crystal. Electrons interact with the specimen's electrostatic potential; a three-dimensional reconstruction is consequently interpreted as a map related to that potential. Recorded images provide noisy two-dimensional projections of particles in different orientations.

Radiation damage limits the electron exposure that can be used to obtain signal. Frame-based acquisition permits correction for specimen motion and appropriate treatment of dose-dependent information loss. Defocus creates useful phase contrast but also modulates spatial frequencies through the contrast transfer function. Image processing must therefore account for the microscope's transfer of structural information before combining particle views. These principles underlie likelihood-based reconstruction approaches such as RELION. [18]

Particle selection, two-dimensional classification, orientation estimation, and three-dimensional classification can identify reconstructable populations. However, classification is not a direct census of all solution states. Fragile particles may dissociate during preparation, some conformations may preferentially adsorb to interfaces, and poorly ordered populations may be excluded during processing. Ice thickness, particle concentration, orientation distribution, and detergent background are therefore experimental variables that determine which molecular states are observed.

Independent half-map reconstruction and Fourier shell correlation help evaluate reproducible spatial information and limit overfitting. A global resolution estimate does not guarantee equivalent detail in every part of the map. Local flexibility, compositional variation, and orientation limitations can reduce confidence in peripheral antennae even when a central region is well resolved. Atomic interpretation must consider local map quality and model validation, not only a single reported resolution. [19,20]

For Chapter 1, cryo-EM may reveal antenna arrangement, subunit interfaces, and pigment organization in sufficiently stable and tractable assemblies. Specific pigment or lipid identities will be assigned only where map features and independent chemistry support them. Near-atomic resolution is an experimental outcome, not a guaranteed property of the technique. For Chapter 2, comparisons of untreated and remodeled AmPBS may reveal structural changes, while biochemical measurements will establish how those structures relate to the reaction mixture.

## 10. X-ray crystallography: a complementary route for AmNblB

Protein crystals contain repeating molecular arrangements that scatter X-rays coherently. Constructive interference is described by Bragg's law,

\[
n\lambda=2d\sin\theta,
\]

where d is the spacing between lattice planes and θ is the corresponding diffraction angle. Diffraction spot positions report lattice geometry, while intensities contain information about the repeating electron-density distribution. Suitable diffraction requires sufficient crystalline order; obtaining visible crystals does not establish that a structure can be solved. [21]

Measured intensities are related to squared structure-factor amplitudes, but the phases needed to calculate electron density are not directly recorded. Molecular replacement can provide initial phase estimates using a related or predicted structural model. Such a model remains a hypothesis: successful placement must be followed by refinement and examination of experimental support, particularly in regions that differ from the search model.

Refinement adjusts an atomic model against diffraction data while maintaining chemically plausible geometry. The Rwork statistic describes agreement with reflections used in refinement, while Rfree evaluates agreement with a withheld test set. Their interpretation, together with density maps, stereochemistry, completeness, and other data-quality indicators, helps identify overfitting or unsupported structural detail. [22]

For AmNblB, a validated structure could reveal candidate interaction surfaces and guide targeted perturbations. Crystal contacts alone would not establish the physiological oligomer, and a fold resembling a known protein family would not demonstrate identical biochemical activity. Any proposed functional residue would require experimental testing, including checks that the perturbation has not simply destabilized the protein.

## 11. Reconstitution: defining sufficiency under controlled conditions

An in vitro reconstitution assay asks whether specified components can generate a defined change under specified conditions. Comparing AmPBS alone, AmPBS with AmNblA, AmPBS with AmNblB, and AmPBS with both proteins will separate individual effects from the combined response. This design will test sufficiency within the reconstructed system, rather than establish that the same components are sufficient for the entire cellular degradation pathway.

Interpretability will depend on matched substrate preparations, protein-buffer contributions, incubation conditions, and sampling times. Vehicle controls will reproduce the buffer introduced with each recombinant protein. Protein quality and substrate stability will be assessed independently, because failure to observe an effect can arise from inactive material, an unsuitable readout, or omission of a required component. Prior studies of Nbl proteins motivate testing remodeling and chromophore-related changes, but do not justify assuming a fully defined catalytic mechanism for the AmNblA/AmNblB pair. [23,24]

Concentration dependence can distinguish some limiting possibilities, but it must be interpreted in terms of an appropriate model. For a simple reversible interaction A + B ⇌ AB,

\[
K_d=\frac{[A][B]}{[AB]}
\]

at equilibrium. PBS contains multiple possible interaction sites and may change during the assay, so a single-site binding model will not be imposed without supporting evidence. If particle composition is uncertain, protein mass concentration will not be converted into an exact number of intact PBS particles by assuming an unsupported molecular mass.

An enhanced response in the combined condition will establish a combination-dependent effect on the chosen readout. Calling it synergy will require a defined reference model. For example, the factorial contrast RAB − RA − RB + R0 tests departure from additivity on the chosen response scale. A nonzero contrast does not uniquely identify direct binding or a sequential mechanism, particularly when responses saturate or optical signals combine nonlinearly. Time courses and complementary structural readouts will help distinguish a larger endpoint effect from faster progression through the same process.

## 12. Order-of-addition and carryover experiments: testing persistent remodeling

Order-of-addition experiments will ask whether exposure to one protein changes subsequent responsiveness to the other. Comparing simultaneous addition with AmNblA-first and AmNblB-first conditions can reveal order dependence. However, pretreatment changes the time each component has contacted the substrate. Appropriate comparisons will therefore match total substrate age and include controls for the additional incubation period.

Removal of free AmNblA after pretreatment will provide a stronger test of whether the substrate retains an altered state. A persistent response to subsequent AmNblB addition would be compatible with substrate remodeling, but could also reflect residual free or substrate-bound AmNblA. Separation recovery and protein carryover will therefore be measured where feasible, and untreated AmPBS will undergo the same mock separation. Loss of activity after separation could indicate a requirement for simultaneous occupancy, but could also arise from reversal of a weakly bound state or damage introduced during handling.

These experiments will discriminate among mechanistic models by combining order, persistence, and composition. “Priming” will denote an experimentally demonstrated change in subsequent substrate responsiveness; it will not itself imply covalent modification or identify the molecular event responsible.

## 13. Spectral deconvolution and chromophore fate

For a mixture with invariant component spectra and negligible scattering, the measured absorbance can be modeled as

\[
A(\lambda)=\ell\sum_i c_i\varepsilon_i(\lambda)+B(\lambda),
\]

where B represents an explicitly justified background. Estimating component contributions requires appropriate reference spectra and sufficient spectral distinction. Strongly overlapping components can make multiple solutions fit almost equally well. Fitting several mathematical peaks therefore does not establish the existence of the same number of biochemical species.

Disassembly complicates this model because the spectra of bound chromophores can change as their environments change. Reference spectra from intact assemblies, dissociated proteins, and free pigments are not interchangeable. In AmPBS experiments, component assignments will follow evidence for the actual preparation, without importing an assumed conventional rod–core composition. Studies of *A. marina* phycobiliproteins show that optical responses to destabilizing conditions can depend on the starting material and growth conditions. [25]

Three outcomes will be distinguished: dissociation of assemblies, altered excitation-energy transfer, and chemical alteration or detachment of chromophores. Spectroscopy can detect changes compatible with each, but cannot uniquely separate them in all cases. Assembly measurements will test physical dissociation, whereas fractionation of protein-associated and lower-molecular-mass material can help locate chromophore-containing products. Recovery must be tracked because precipitation or adsorption can otherwise resemble pigment loss.

Where chemical identification becomes necessary, targeted analysis of pigments or chromophore-bearing peptides would provide stronger evidence than spectral bleaching alone. A bilin can remain covalently attached to a small peptide after proteolysis, so low-molecular-mass pigment-containing material is not automatically free bilin. The distinction between dissociation, proteolysis, and chromophore-bond cleavage will remain explicit in mechanistic conclusions.

## 14. Interaction assays: testing association and functional dependence

Pull-down assays enrich a candidate partner through association with an immobilized bait, while co-elution assays ask whether components migrate together during separation. Both approaches can support interaction hypotheses, but retention can also arise from the affinity tag, matrix, nonspecific adsorption, or indirect bridging through the substrate. Relevant controls will include bait and prey alone, matrix or tag controls, and comparisons with and without AmPBS. Reciprocal capture will be informative where compatible constructs are available.

A negative pull-down does not exclude a weak or transient interaction: dilution and washing may remove it. Conversely, co-elution can occur by coincidence when separate proteins have similar chromatographic behavior. An interaction detected only in the presence of AmPBS would be consistent with substrate-mediated recruitment, but would not by itself distinguish direct regulator–regulator contact from binding to different sites on the same particle. Earlier reconstitution studies provide a reason to test these alternatives explicitly. [24]

Functional necessity will require a perturbation that selectively affects the proposed association while preserving other relevant properties. If an interaction-disrupting variant loses remodeling activity but also unfolds, the causal interpretation remains unresolved. Structural, biochemical, and spectroscopic measurements will therefore be combined to connect physical association to antenna remodeling.

## 15. Relating evidence to conclusions

| Scientific question | Principal observable | Evidence needed for a stronger conclusion |
|---|---|---|
| Are distinct assemblies present? | SEC profile, native-gel migration, mass-photometry populations | Composition and agreement across methods under documented solution conditions |
| Are accessory pigments functionally coupled? | Corrected excitation/emission behavior; suitable time-resolved signals | Absorption normalization, direct-excitation controls, and an appropriate kinetic model |
| Which proteins are present? | Confident peptide identifications | Distinguishing peptides or explicitly reported protein groups |
| How are subunits and pigments arranged? | Validated structural maps and models | Local resolution, chemical plausibility, and independent compositional evidence |
| Do AmNblA and AmNblB remodel AmPBS together? | Combination-dependent changes over time | Matched controls, concentration dependence, and independent assembly readouts |
| Does one regulator leave a persistent substrate change? | Post-separation responsiveness | Carryover measurements, mock separation, recovery, and matched incubation times |
| Are chromophores detached or chemically modified? | Changed spectra and location of pigment-containing products | Product identification and distinction from pigment-bearing peptides |
| Is an interaction required for remodeling? | Association plus loss of function after selective perturbation | Preserved protein stability and exclusion of indirect effects |

## References and technical sources

Manufacturer documents below support instrument principles and operation; biological and mechanistic arguments are supported by research papers. Links are provided for direct checking before the final bibliography is formatted.

1. Thermo Fisher Scientific. [Detergents for cell lysis and protein extraction](https://www.thermofisher.com/us/en/home/life-science/protein-biology/protein-biology-learning-center/protein-biology-resource-library/pierce-protein-methods/detergents-cell-lysis-protein-extraction.html).
2. Merck. [Solubilization of membrane proteins](https://www.merckmillipore.com/LC/en/technical-documents/protocol/protein-biology/protein-purification/solubilization).
3. Cytiva. [Size Exclusion Chromatography: Principles and Methods](https://cdn.cytivalifesciences.com/api/public/content/digi-11639-pdf).
4. [SEC-based hydrodynamic-radius methodology](https://pmc.ncbi.nlm.nih.gov/articles/PMC8410290/). Protocol source for interpreting hydrodynamic size.
5. Merck/Sigma-Aldrich. [Ion-exchange separation](https://www.sigmaaldrich.com/US/en/technical-documents/technical-article/protein-biology/protein-purification/iex-separation).
6. [Primary study of peridinin excited-state and charge-transfer behavior](https://doi.org/10.1073/pnas.262537599). PNAS (2002). [Full text](https://pmc.ncbi.nlm.nih.gov/articles/PMC139217/).
7. Kleima et al. (2000). [PCP steady-state spectroscopy study](https://doi.org/10.1021/bi992427s).
8. Ilagan et al. (2006). [Comparative PCP spectroscopy](https://doi.org/10.1007/s11120-006-9090-8). [Full text](https://pmc.ncbi.nlm.nih.gov/articles/PMC1769343/).
9. Kleima et al. (2000). [PCP energy-transfer study](https://pubmed.ncbi.nlm.nih.gov/10620298/).
10. HORIBA. [Fluorolog-3 operation manual, revision G](https://www.horiba.com/fileadmin/uploads/Scientific/Downloads/UserArea/Fluorescence/Manuals/Total_Fluorolog-3_Manual_J81014_rev_G__May_2014_.pdf).
11. HORIBA. [How to calculate signal-to-noise ratio](https://www.horiba.com/int/scientific/technologies/fluorescence-spectroscopy/how-to-calculate-signal-to-noise-ratio/).
12. Markwell, Thornber & Boggs (1979). [Higher plant chloroplasts: Evidence that all the chlorophyll exists as chlorophyll-protein complexes](https://doi.org/10.1073/pnas.76.3.1233).
13. [Separation of chlorophyll-protein complexes by Deriphat polyacrylamide gradient gel electrophoresis](https://pubmed.ncbi.nlm.nih.gov/7859709/).
14. Refeyn. [Basics of mass photometry](https://refeyn.com/tech-notes-basics-of-mass-photometry).
15. Olerinyova et al. (2021). [Mass Photometry of Membrane Proteins](https://doi.org/10.1016/j.chempr.2020.11.011). [Full text](https://pmc.ncbi.nlm.nih.gov/articles/PMC7815066/).
16. [Accurate Mass Spectrometry Based Protein Quantification via Shared Peptides](https://pmc.ncbi.nlm.nih.gov/articles/PMC3317402/) (2012).
17. [DIP-MS: ultra-deep interaction proteomics for the deconvolution of protein complexes](https://doi.org/10.1038/s41592-024-02211-y) (2024).
18. Scheres (2012). [RELION: Implementation of a Bayesian approach to cryo-EM structure determination](https://pubmed.ncbi.nlm.nih.gov/23000701/).
19. Scheres & Chen (2012). [Prevention of overfitting in cryo-EM structure determination](https://doi.org/10.1038/nmeth.2115).
20. [New tools for the analysis and validation of cryo-EM maps and atomic models](https://pmc.ncbi.nlm.nih.gov/articles/PMC6130467/) (2018).
21. International Union of Crystallography. [Bragg's law](https://dictionary.iucr.org/Bragg%27s_law).
22. International Union of Crystallography. [Free R factor](https://dictionary.iucr.org/Free_R_factor).
23. Levi et al. (2018). [Study of NblB-dependent phycobiliprotein chromophore-related changes](https://doi.org/10.1111/tpj.13896).
24. Hu et al. (2020). [NblA/NblB reconstitution and phycobiliprotein disassembly study](https://doi.org/10.1111/tpj.14647).
25. Niedzwiedzki et al. (2019). [Spectroscopy of *Acaryochloris marina* phycobiliprotein assemblies](https://doi.org/10.1016/j.bbabio.2019.01.002).

---

## Implementation details to confirm — separate from manuscript text

These entries record missing implementation information, not proposed settings.

| Item | Current status |
|---|---|
| Exact ÄKTA model, detector channels, installed columns, and detector-to-collector delay | N/A — confirm local configuration |
| Validated extraction detergent, concentration, exposure time, and recovery | N/A — establish experimentally for selected material |
| Fluorolog-3 detector, correction files, temperature accessory, and time-resolved configuration | N/A — confirm installed components and performance |
| Reference spectra and extinction coefficients appropriate to the measured pigment states | N/A — select and validate |
| Native/Deriphat gel formulation and compatibility with each preparation | N/A — establish experimentally |
| TwoMP calibration, buffer compatibility, usable mass range, and detergent strategy | N/A — validate for these samples |
| Proteomics facility, sequence database, digestion, acquisition, and protein-inference strategy | N/A — define with analytical facility |
| Cryo-EM specimen preparation and acquisition settings | N/A — optimize after biochemical characterization |
| AmNblB crystal diffraction quality and crystallographic solution | N/A — crystals obtained; structural outcome pending |
| Quantitative carryover assay and product-identification strategy for AmPBS experiments | N/A — select according to sensitivity and available material |

**Editorial use:** This is a full foundation draft. The final introduction can retain the principle, biological relevance, and interpretation limits of each approach; operating details can move to Methods. The equations are most useful where they clarify a real distinction, such as hydrodynamic size versus mass, absorbance versus concentration, or fluorescence intensity versus energy-transfer efficiency.
