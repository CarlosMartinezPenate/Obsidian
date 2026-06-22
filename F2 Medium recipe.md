---
final_media_volume_ml: 1375
f2_stock_x: 50
---

# F/2 Medium Preparation

Adapted From [[Symbiodiniaceae Culturing Protocols – Parkinson Lab]]

## Goal
Prepare fresh **1× F/2 medium in ASW** using **Guillard’s [[F2 medium]] 50× stock**.

## Base logic
- A **50× stock** means the stock is **50 times more concentrated** than the final working medium
- Therefore, the stock must make up **1/50 of the final volume**
- The rest of the final volume is **ASW**

## Static preparation steps
1. Make artificial seawater (see [[ASW recipe]]) (~28 mL volume of salt per 1 L DI water to get ~32 ppt (32–34 ppt acceptable; check with refractometer)).
2. Filter the seawater (use pump and 0.2 micron filter).
3. Add **Guillard’s [[F2 medium]] 50× stock** to the filtered ASW to reach the desired final 1× F/2 concentration.
4. Add media to the clean glassware (see [[Cleaning Glassware]]).
5. Autoclave.
6. Allow media to cool to room temperature before use.

## Dynamic F/2 calculation

```dataviewjs
const p = dv.current();

const finalVol = p.final_media_volume_ml ?? 1000;
const stockX = p.f2_stock_x ?? 50;

const stockVol = finalVol / stockX;
const aswVol = finalVol - stockVol;

dv.header(2, "Working calculation");

dv.paragraph(`
To prepare **${finalVol} mL** of final **1× F/2 medium** from a **${stockX}× stock**:

- use **${stockVol} mL** of F/2 stock
- use **${aswVol} mL** of ASW
- final volume = **${finalVol} mL**
`);

dv.header(2, "Formula");

dv.list([
  `F/2 stock volume = final volume / ${stockX}`,
  `ASW volume = final volume - stock volume`
]);

dv.header(2, "Examples");

const examples = [50, 100, 250, 500, 1000, finalVol]
  .filter((v, i, arr) => arr.indexOf(v) === i);

const rows = examples.map(v => {
  const stock = v / stockX;
  const asw = v - stock;
  return [`${v} mL`, `${stock} mL`, `${asw} mL`];
});

dv.table(
  ["Final 1× F/2 medium", "50× stock needed", "ASW needed"],
  rows
);
```

## Exact interpretation
For **50× F/2 stock**:

- **1 mL stock + 49 mL ASW = 50 mL final medium**
- **2 mL stock + 98 mL ASW = 100 mL final medium**
- **5 mL stock + 245 mL ASW = 250 mL final medium**
- **10 mL stock + 490 mL ASW = 500 mL final medium**
- **20 mL stock + 980 mL ASW = 1000 mL final medium**

## Notes
- Think in terms of **final medium volume**, not “add stock to 1 L ASW”
- For exact 1× medium, the stock should be included **within** the final total volume
- So for **1 L final medium**, use **980 mL ASW + 20 mL stock**, not **1000 mL ASW + 20 mL stock**