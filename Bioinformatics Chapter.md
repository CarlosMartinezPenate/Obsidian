Absolutely. In fact, I think the **bioinformatics could become the engine** that generates hypotheses, while the wet lab validates only the most promising designs.

This is very similar to how modern protein engineering is done: you don’t experimentally test 10,000 combinations—you computationally narrow them down to perhaps 10.

For example, you could imagine a pipeline like this:

1. **Build a library of light-responsive proteins**
    - PCPs from different Symbiodiniaceae
    - Phytochromes
    - LOV domains
    - BLUF proteins
    - Orange carotenoid proteins (OCPs)
    - Fluorescent proteins
    - Rhodopsins
2. **Predict their structures**
    - Many already have experimental structures.
    - Others can be modeled with AlphaFold.
3. **Analyze their properties**
    - Surface charge
    - Accessible residues
    - Cofactor-binding pockets
    - Flexibility/disorder
    - Conserved regions
    - Oligomeric state
    - Spectral properties (from literature or computational prediction where possible)
4. **Design combinations**
    - Which proteins could be fused?
    - Where should the linker go?
    - Which orientations keep the chromophores close enough?
    - Which interfaces are least likely to disrupt folding?
5. **Prioritize candidates**
    - Stability
    - Expression feasibility
    - Predicted distance between chromophores
    - Structural confidence
    - Manufacturability

Only then would you move into the lab.

---

### **This becomes even more interesting with AI**

Instead of asking:

“Which two proteins should I combine?”

you could ask:

**“Given a desired optical behavior, which combination of proteins is most likely to produce it?”**

Imagine specifying:

- absorb 450–550 nm
- emit at ~650 nm
- respond to blue light
- remain stable at 40°C

and having a computational workflow suggest a handful of candidate architectures.

That is much closer to **protein design** than traditional bioinformatics.

---

### **Your Symbiodiniaceae collection could become a resource**

Rather than treating SSA01, SSA02, SSA03, SSB01, and SSE01 as five organisms to characterize, you could treat them as five sources of **optical modules**.

For each PCP, you could build a database containing:

- absorption spectrum
- emission spectrum
- fluorescence lifetime
- photostability
- thermal stability
- pH tolerance
- predicted structure
- pigment composition
- oligomeric state

Over time, this becomes a searchable catalog for engineering.

---

### **Where I think there is a real research opportunity**

A lot of current bioinformatics predicts **protein structure**.

Much less work has focused on predicting **emergent function when proteins are assembled into synthetic systems**.

A possible long-term question is:

**Can we computationally design multi-protein photonic assemblies with desired optical properties before they are built experimentally?**

That would combine structural bioinformatics, protein engineering, photophysics, and biomaterials.

One note of caution: predicting the behavior of _individual proteins_ is now quite advanced. Predicting the optical properties of **new combinations** of pigment-binding proteins remains much harder because energy transfer depends on chromophore identity, orientation, distance, local environment, and excited-state physics. So a computational pipeline would likely need to integrate structural prediction with photophysical modeling and then rely on experimental validation.

Ironically, that limitation is also an opportunity. There is still no standard workflow that takes a set of photosynthetic proteins and answers, “If I assemble these in this geometry, what optical behavior should I expect?” Developing even part of that workflow could itself be a valuable research contribution.