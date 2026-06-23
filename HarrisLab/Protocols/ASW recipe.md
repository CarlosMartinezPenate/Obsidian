---
asw_final_volume_ml: 1347.5
coral_pro_ratio_g_per_l: 37.1
coral_pro_manual_reference_g_per_l: 39.5
target_salinity_ppt: 32
---
Using [[TingTing's Culturing Symbiodinium Protocol]]

1. Dissolve 37.1 g [[Coral Pro]] salt into 1L pure water; check the salinity of the dissolved seawater and make sure it is between 32 and 34. *Note: This step of dissolving sea salts may take a while, stir overnight is recommended.*

Using  [[Symbiodiniaceae Culturing Protocols Parkinson - Lab]]
1. Make artificial seawater (~28 mL volume of salt per 1 L DI water to get ~32 ppt (32-34 ppt acceptable; check with refractometer).
2. Filter the seawater (use pump and 0.2 micron filter).

## Note on ratios
- **Tingting protocol working ratio**: **37.1 g/L**
- **Coral Pro manual reference at 34 ppt**: **39.5 g/L**
- Parkinson’s note says to make ASW to about **32–34 ppt** and check with refractometer.

## Dynamic Coral Pro calculation

```dataviewjs

const p = dv.current();
const finalVolMl = p.asw_final_volume_ml ?? 1000;
const ratio = p.coral_pro_ratio_g_per_l ?? 37.1;
const manualRef = p.coral_pro_manual_reference_g_per_l ?? 39.5;
const salinity = p.target_salinity_ppt ?? 32;
const finalVolL = finalVolMl / 1000;
const saltNeeded = finalVolL * ratio;
const manualEquivalent = finalVolL * manualRef;
dv.header(2, "Working calculation");
dv.paragraph(`
To prepare **${finalVolMl} mL** (${finalVolL.toFixed(3)} L) of ASW using the **Tingting ratio** of **${ratio} g/L**:
- use **${saltNeeded.toFixed(2)} g Coral Pro**
- add to water
- mix until dissolved
- check salinity and adjust if needed 
`);
dv.header(2, "Reference against Coral Pro manual");
dv.paragraph(`
If using the **Coral Pro manual reference** of **${manualRef} g/L** (listed for **34 ppt**), the same volume would use:
- **${manualEquivalent.toFixed(2)} g Coral Pro**
`);
dv.header(2, "Formula");
dv.list([

`final volume in liters = final volume in mL / 1000`,
`Coral Pro needed (g) = final volume in liters × ${ratio}`,
`Manual reference salt (g) = final volume in liters × ${manualRef}`
]);
dv.header(2, "Examples");
const examples = [250, 500, 1000, 1250, finalVolMl]
  .filter((v, i, arr) => arr.indexOf(v) === i);
const rows = examples.map(v => {
  const L = v / 1000;
  const ting = L * ratio;
  const man = L * manualRef;
  return [
    `${v} mL`,
    `${ting.toFixed(2)} g`,
    `${man.toFixed(2)} g`
  ];
});
dv.table(
  ["Final ASW volume", `Coral Pro at ${ratio} g/L`, `Coral Pro at ${manualRef} g/L`],
  rows 
);  

```

  

## Practical steps
1. Measure the desired volume of pure / RO water.
2. Weigh the required **Coral Pro** amount.
3. Add the salt to the water.
4. Mix without aeration until dissolved.
5. Do not mix more than 4 hours.
6. Bring the water to about 25°C.
7. Measure salinity with a refractometer.
8. Adjust with more salt or water if needed.