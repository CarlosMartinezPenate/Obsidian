---
title: Buffer Preparation Calculator
buffer_name: 50 mM K-phosphate + 100 mM NaCl
final_volume_ml: 1000
target_pH: 7.2
storage: 4 °C
component_1_name: K-phosphate
component_1_mode: stock
component_1_target_mM: 50
component_1_stock_M: 1
component_1_MW: 0
component_2_name: NaCl
component_2_mode: solid
component_2_target_mM: 100
component_2_stock_M: 0
component_2_MW: 58.44
component_3_name: Imidazole
component_3_mode: none
component_3_target_mM: 0
component_3_stock_M: 0
component_3_MW: 68.08
component_4_name: Glycerol
component_4_mode: none
component_4_target_percent: 0
component_5_name: Additional component
component_5_mode: none
component_5_target_mM: 0
component_5_stock_M: 0
component_5_MW: 0
---

# **Editable settings**

Edit the values in the Properties panel or in the YAML section at the top.

## **Component modes**

Use one of these values:

- `solid` — calculate the mass to weigh
- `stock` — calculate the volume of stock solution to add
- `none` — do not include the component

## **Units**

- Final buffer volume: mL
- Target concentration: mM
- Stock concentration: M
- Molecular weight: g/mol
- Calculated solid mass: g or mg
- Calculated stock volume: mL or µL

---

# **Calculated quantities**

```dataviewjs
const p = dv.current();

const finalVolumeMl = Number(p.final_volume_ml);
const finalVolumeL = finalVolumeMl / 1000;

if (!Number.isFinite(finalVolumeMl) || finalVolumeMl <= 0) {
    dv.paragraph("⚠️ Enter a valid final_volume_ml.");
} else {
    const rows = [];

    for (let i = 1; i <= 5; i++) {
        const name = p[`component_${i}_name`];
        const mode = String(p[`component_${i}_mode`] ?? "none").toLowerCase();
        const targetMm = Number(p[`component_${i}_target_mM`] ?? 0);
        const stockM = Number(p[`component_${i}_stock_M`] ?? 0);
        const mw = Number(p[`component_${i}_MW`] ?? 0);

        if (!name || mode === "none") {
            continue;
        }

        let result = "";
        let instruction = "";

        if (mode === "solid") {
            if (!Number.isFinite(targetMm) || targetMm <= 0) {
                result = "Invalid target concentration";
                instruction = "Enter target concentration in mM";
            } else if (!Number.isFinite(mw) || mw <= 0) {
                result = "Missing molecular weight";
                instruction = "Enter molecular weight in g/mol";
            } else {
                const moles = (targetMm / 1000) * finalVolumeL;
                const massG = moles * mw;

                if (massG >= 1) {
                    result = `${massG.toFixed(3)} g`;
                } else {
                    result = `${(massG * 1000).toFixed(1)} mg`;
                }

                instruction = `Weigh ${result} of ${name}`;
            }
        }

        else if (mode === "stock") {
            if (!Number.isFinite(targetMm) || targetMm <= 0) {
                result = "Invalid target concentration";
                instruction = "Enter target concentration in mM";
            } else if (!Number.isFinite(stockM) || stockM <= 0) {
                result = "Missing stock concentration";
                instruction = "Enter stock concentration in M";
            } else {
                const targetM = targetMm / 1000;
                const stockVolumeL = (targetM * finalVolumeL) / stockM;
                const stockVolumeMl = stockVolumeL * 1000;

                if (stockVolumeMl >= 1) {
                    result = `${stockVolumeMl.toFixed(2)} mL`;
                } else {
                    result = `${(stockVolumeMl * 1000).toFixed(1)} µL`;
                }

                instruction = `Add ${result} of ${stockM} M ${name} stock`;
            }
        }

        else {
            result = "Unknown mode";
            instruction = "Use solid, stock, or none";
        }

        rows.push([
            name,
            `${targetMm} mM`,
            mode,
            result,
            instruction
        ]);
    }

    if (rows.length === 0) {
        dv.paragraph("No active components. Set at least one component mode to solid or stock.");
    } else {
        dv.table(
            [
                "Component",
                "Final concentration",
                "Source",
                "Quantity",
                "Instruction"
            ],
            rows
        );
    }
}
```

---

# **Optional glycerol calculation**

Use this section when glycerol is added as a liquid percentage by volume.

Set:

```yaml
component_4_name: Glycerol
component_4_mode: liquid_percent
component_4_target_percent: 10
```

```dataviewjs
const p = dv.current();

const finalVolumeMl = Number(p.final_volume_ml);
const glycerolMode = String(p.component_4_mode ?? "none").toLowerCase();
const glycerolPercent = Number(p.component_4_target_percent ?? 0);

if (glycerolMode === "liquid_percent" && glycerolPercent > 0) {
    const glycerolVolumeMl = finalVolumeMl * glycerolPercent / 100;

    dv.table(
        ["Component", "Final percentage", "Volume"],
        [[
            p.component_4_name ?? "Glycerol",
            `${glycerolPercent}% v/v`,
            `${glycerolVolumeMl.toFixed(2)} mL`
        ]]
    );
} else {
    dv.paragraph("Glycerol is not currently included.");
}
```

---

# **Preparation procedure**

1. Add approximately 70–80% of the final volume of ultrapure water to a clean beaker.
2. Add the calculated quantities of the solid reagents.
3. Add the calculated volumes of stock solutions.
4. Mix until all components are fully dissolved.
5. Measure the pH.
6. Adjust to pH `= this.target_pH` using the appropriate acid or base.
7. Transfer the buffer to a graduated cylinder or volumetric flask.
8. Bring to a final volume of `= this.final_volume_ml` mL with ultrapure water.
9. Mix thoroughly.
10. Sterilize only using a method compatible with all buffer components.
11. Label the bottle with the buffer name, composition, pH, date, and preparer.
12. Store at `= this.storage`.

---

# **Calculation formulas**

## **Solid reagent**

Mass in grams:

```text
mass_g =
(target_mM / 1000)
× final_volume_L
× molecular_weight_g_per_mol
```

Since the note uses final volume in mL:

```text
final_volume_L = final_volume_ml / 1000
```

Therefore:

```text
mass_g =
(target_mM / 1000)
× (final_volume_ml / 1000)
× molecular_weight
```

### **Example: 100 mM NaCl in 1 L**

```text
mass =
(100 / 1000)
× 1 L
× 58.44 g/mol

mass = 5.844 g
```

---

## **Stock solution**

Use:

```text
C1 × V1 = C2 × V2
```

Therefore:

```text
V1 = (C2 × V2) / C1
```

In this calculator:

```text
stock_volume_L =
(target_concentration_M × final_volume_L)
/
stock_concentration_M
```

### **Example: 50 mM K-phosphate from a 1 M stock for 1 L**

```text
stock volume =
(0.050 M × 1 L)
/
1 M

stock volume = 0.050 L
stock volume = 50 mL
```

---

# **Current buffer examples**

## **Buffer A: 50 mM K-phosphate + 100 mM NaCl**

For 1 L, using a 1 M K-phosphate stock:

```text
50 mL of 1 M K-phosphate stock
5.844 g NaCl
Water to a final volume of 1 L
```

Use these properties:

```yaml
buffer_name: 50 mM K-phosphate + 100 mM NaCl
final_volume_ml: 1000

component_1_name: K-phosphate
component_1_mode: stock
component_1_target_mM: 50
component_1_stock_M: 1
component_1_MW: 0

component_2_name: NaCl
component_2_mode: solid
component_2_target_mM: 100
component_2_stock_M: 0
component_2_MW: 58.44

component_3_name: Imidazole
component_3_mode: none
component_3_target_mM: 0
component_3_stock_M: 0
component_3_MW: 68.08
```

---

## **Buffer B: 50 mM K-phosphate without NaCl**

For 1 L, using a 1 M K-phosphate stock:

```text
50 mL of 1 M K-phosphate stock
Water to a final volume of 1 L
```

Change the NaCl mode to `none`:

```yaml
buffer_name: 50 mM K-phosphate
component_2_mode: none
component_2_target_mM: 0
```

---

## **Elution buffer example**

Example composition:

```text
50 mM K-phosphate
100 mM NaCl
500 mM imidazole
```

For 1 L, using a 1 M K-phosphate stock and solid NaCl and imidazole:

```text
50 mL of 1 M K-phosphate stock
5.844 g NaCl
34.040 g imidazole
Water to a final volume of 1 L
```

Use:

```yaml
buffer_name: 50 mM K-phosphate + 100 mM NaCl + 500 mM imidazole

component_1_name: K-phosphate
component_1_mode: stock
component_1_target_mM: 50
component_1_stock_M: 1
component_1_MW: 0

component_2_name: NaCl
component_2_mode: solid
component_2_target_mM: 100
component_2_stock_M: 0
component_2_MW: 58.44

component_3_name: Imidazole
component_3_mode: solid
component_3_target_mM: 500
component_3_stock_M: 0
component_3_MW: 68.08
```

---

# **K-phosphate warning**

K-phosphate is a buffer system, not necessarily one individual reagent.

It is normally prepared using:

- KH₂PO₄, monobasic potassium phosphate
- K₂HPO₄, dibasic potassium phosphate

The ratio of these two salts determines the pH.

The safest approach is to use an existing K-phosphate stock of known concentration and pH. Enter it as a `stock` component.

Do not enter a molecular weight for “K-phosphate” unless you are deliberately preparing the buffer from one specific phosphate salt.

---

# **Preparation record**

|**Field**|**Entry**|
|---|---|
|Buffer name|`= this.buffer_name`|
|Final volume|`= this.final_volume_ml` mL|
|Target pH|`= this.target_pH`|
|Measured pH||
|Preparation date||
|Prepared by||
|Storage|`= this.storage`|
|Sterilization method||
|Notes||