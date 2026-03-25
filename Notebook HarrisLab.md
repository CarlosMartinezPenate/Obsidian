# 🧬 [[NbLB]] — [[AlphaFold]]3 Analysis (Monomer)

**Date:** 2026-03-16  
**System:** *Acaryochloris marina* MBIC 11017  
**Target:** [[NbLB]]  
**Constructs analyzed:**
- Protein-only (no tag)
- C-terminal His₆-tagged construct

---

## 🧠 Objective

Evaluate:
- Folding state of [[NbLB]]
- Presence of disorder
- Effect of His-tag
- Implications for expression, purification, and structural work

---

## 📊 Summary of Results

### 🔹 Global Fold

- Predicted structure is **compact and predominantly α-helical**
- No evidence of multi-domain flexibility
- Likely a **single-domain protein**

**Confidence:**
- pTM ≈ 0.89–0.90 → **high confidence global fold**
- Consistent across all 5 model seeds → **high reproducibility**

---

## 📈 Disorder Analysis ([[pLDDT]]-based)

### 🔹 Protein-only construct (220 aa)

**Low-confidence residues (<70):**
- Residue 2 (His)
- Residue 219 (Glu)
- Residue 220 (Pro)

**Very low confidence (<50):**
- None

**Interpretation:**
- Structure is **almost entirely ordered**
- Only minor flexibility at **N- and C-termini**

---

### 🔹 His-tag construct (226 aa)

**Low-confidence residues (<70):**
- Residues 1–2 (N-terminus)
- Residues 219–220 (C-terminal edge)

**Very low confidence (<50):**
- Residues 221–226 → **His₆ tag**

**Interpretation:**
- Core fold unchanged
- His-tag behaves as **flexible tail (expected)**

---

## 🧬 Structural Interpretation

### 🔹 Fold Type

- Predominantly **α-helical bundle**
- Likely:
  - scaffold protein
  - protein–protein interaction module
  - lyase-like fold (consistent with literature)

---

### 🔹 Flexibility

- Minimal intrinsic disorder
- Flexibility limited to:
  - termini
  - short loops
- No large disordered regions

---

## 🔬 Experimental Implications

### ✅ Expression

- Likely to express **solubly**
- No indication of intrinsic instability

---

### ✅ Purification

- His-tag construct should behave normally
- Tag does not disrupt folding
- Expect:
  - soluble fraction
  - clean IMAC purification

---

### ✅ SEC behavior (prediction)

- Likely **monodisperse**
- Possible:
  - monomer
  - weak oligomerization (to be tested)

---

### ⚠️ Crystallization

**Favorable features:**
- compact fold
- low disorder

**Potential caveats:**
- flexible termini
- His-tag tail

**Future optimization options:**
- tag removal (TEV)
- terminal truncations (if needed)

---

## 🧪 Thermal Stability (DSF)

**Conclusion:**
- Not required at this stage

**Use later for:**
- buffer optimization
- ligand binding detection
- construct comparison

---

## 🧠 Biological Interpretation

- [[NbLB]] is likely:
  - **independently folded**
  - not intrinsically disordered
  - structurally stable without partners

- Suggests role as:
  - **interaction scaffold**
  - rather than folding-dependent partner

---

## 🚀 Next Steps (Computational)

Once sequences are available:

- [ ] [[NbLB]] + APCβ
- [ ] [[NbLB]] + CpcA
- [ ] [[NbLB]] + NblA (control)

Focus:
- interface formation
- reproducibility
- interface confidence (PAE)

---

## 🚀 Next Steps (Experimental — future)

1. Expression test
2. Solubility check
3. IMAC purification
4. SEC profiling
5. Decide:
   - apo structure vs complex-driven project

---

## 🧠 Key Takeaway

> [[NbLB]] is a structurally well-behaved protein candidate.  
> The main challenge is likely **function and interactions**, not folding or stability.

---