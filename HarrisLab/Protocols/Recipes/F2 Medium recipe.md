---
final_media_volume_ml: 1375
f2_stock_x: 50
f2_stock_contains_vitamins: true
asw_filtration_um: 0.2
---

# F/2 Medium Preparation

Adapted from [[Symbiodiniaceae Culturing Protocols – Parkinson Lab]]

## Goal
Prepare fresh **1× F/2 medium in [[ASW]]** using **Guillard’s [[F2 medium]] 50× stock**.

## Important note about this F/2 stock
The available **Guillard’s F/2 Marine Water Enrichment Solution 50×** contains:

- major nutrients
- trace metals
- vitamins
- no silicate

Because this stock contains **vitamins**, do **not** autoclave the complete F/2 medium as the default method.  
Instead, sterilize the ASW first, then add the F/2 50× stock after filtration using sterile technique.

## Base logic
- A **50× stock** means the stock is **50 times more concentrated** than the final working medium.
- Therefore, the stock must make up **1/50** of the final volume.
- The rest of the final volume is **sterile ASW**.
- For exact 1× medium, calculate based on the **final total volume**, not by adding stock on top of 1 L ASW.

## Preferred preparation logic

```text
Prepare ASW → filter-sterilize ASW → add F/2 50× stock aseptically → final 1× F/2 medium
```

## Static preparation steps

1. Make artificial seawater using DI water and sea salt (see [[ASW recipe]])
   - Approximate starting point: **~28 mL volume of salt per 1 L DI water** to reach ~32 ppt.
   - Target salinity: **32–34 ppt**.
   - Check salinity with a refractometer.
   - Allow salt to dissolve completely before filtration.

2. Filter-sterilize the ASW  
   - Use pump and **0.2 µm filter**.
   - Collect the filtered ASW into clean/sterile glassware or bottle.

3. Add **Guillard’s [[F2 medium]] 50× stock** to the filtered ASW  
   - Add stock after ASW filtration.
   - Use sterile technique.
   - Mix gently.
   - Final concentration should be **1× F/2**.

4. Dispense medium into clean glassware  
   - See [[Cleaning Glassware]].
   - See [[Autoclaving Protocol]]
   - Use clean/sterile vessels appropriate for culture work.

5. Do **not** autoclave the complete medium as the default method  
   - The F/2 stock contains vitamins.
   - Autoclaving the complete medium may unnecessarily heat-expose vitamin-containing components.

6. Allow medium to equilibrate to room temperature before use, if needed.

7. Label the prepared medium  
   - Medium: **1× F/2 in ASW**
   - Date prepared
   - Final volume
   - F/2 stock used
   - Sterilization method: **ASW filtered, F/2 added after filtration**
   - Initials

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
- use **${aswVol} mL** of sterile ASW
- final volume = **${finalVol} mL**
`);

dv.header(2, "Preparation order");

dv.list([
  `Prepare and filter-sterilize **${aswVol} mL ASW**`,
  `Aseptically add **${stockVol} mL** of ${stockX}× F/2 stock after ASW filtration`,
  `Mix gently`,
  `Final volume = **${finalVol} mL** of 1× F/2 medium`
]);

dv.header(2, "Formula");

dv.list([
  `F/2 stock volume = final volume / ${stockX}`,
  `Sterile ASW volume = final volume - stock volume`
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
  ["Final 1× F/2 medium", "50× stock needed", "Sterile ASW needed"],
  rows
);
```

## Exact interpretation

For **50× F/2 stock**:

- **1 mL stock + 49 mL sterile ASW = 50 mL final medium**
- **2 mL stock + 98 mL sterile ASW = 100 mL final medium**
- **5 mL stock + 245 mL sterile ASW = 250 mL final medium**
- **10 mL stock + 490 mL sterile ASW = 500 mL final medium**
- **20 mL stock + 980 mL sterile ASW = 1000 mL final medium**

## Notes
- Think in terms of **final medium volume**, not “add stock to 1 L ASW”.
- For exact 1× medium, the stock should be included **within** the final total volume.
- So for **1 L final medium**, use **980 mL sterile ASW + 20 mL stock**, not **1000 mL ASW + 20 mL stock**.
- Add the F/2 stock **after ASW filtration**, because this stock contains vitamins.
- Do not autoclave the complete vitamin-containing F/2 medium unless the lab specifically accepts that approach.