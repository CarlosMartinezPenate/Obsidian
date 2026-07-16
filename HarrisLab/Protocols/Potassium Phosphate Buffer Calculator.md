---
title: Potassium Phosphate Buffer Calculator
aliases:
  - KPhos Calculator
tags:
  - protocol
  - buffer
  - calculator
stock_concentration_M: 1
---

# Potassium Phosphate Buffer Calculator

This calculator prepares potassium phosphate buffer using either:

1. **1 M phosphate stocks**
   - 1 M KH₂PO₄
   - 1 M K₂HPO₄

2. **Dry phosphate salts**
   - KH₂PO₄
   - anhydrous K₂HPO₄

Optional components:

- NaCl, from powder or stock solution
- Imidazole, from powder or stock solution

> [!warning]
> The calculated phosphate ratio is a starting formulation. Temperature, phosphate concentration, NaCl, and especially imidazole can alter the measured pH. Measure the pH after all components have been added, then bring the solution to its final volume.

```dataviewjs
const container = dv.el("div", "");

container.innerHTML = `
<style>
.kphos-calculator {
    max-width: 760px;
    padding: 18px;
    border: 1px solid var(--background-modifier-border);
    border-radius: 10px;
    background: var(--background-secondary);
}

.kphos-calculator h3 {
    margin-top: 0;
}

.kphos-section {
    margin-top: 18px;
    padding-top: 14px;
    border-top: 1px solid var(--background-modifier-border);
}

.kphos-grid {
    display: grid;
    grid-template-columns: minmax(240px, 1fr) minmax(160px, 210px);
    gap: 12px;
    align-items: center;
}

.kphos-grid input,
.kphos-grid select {
    width: 100%;
    box-sizing: border-box;
}

.kphos-button {
    margin-top: 18px;
    padding: 8px 18px;
    cursor: pointer;
}

.kphos-result {
    margin-top: 18px;
    padding: 14px;
    border: 1px solid var(--background-modifier-border);
    border-radius: 8px;
    background: var(--background-primary);
}

.kphos-result table {
    width: 100%;
    border-collapse: collapse;
}

.kphos-result th,
.kphos-result td {
    padding: 7px;
    border-bottom: 1px solid var(--background-modifier-border);
    text-align: left;
    vertical-align: top;
}

.kphos-error {
    margin-top: 16px;
    padding: 12px;
    border-radius: 8px;
    background: var(--background-modifier-error);
    color: var(--text-error);
}

.kphos-note {
    margin-top: 12px;
    padding: 10px;
    border-left: 4px solid var(--interactive-accent);
    background: var(--background-primary);
}
</style>

<div class="kphos-calculator">

    <h3>Final buffer</h3>

    <div class="kphos-grid">

        <label for="kphos-volume">Final buffer volume</label>
        <input
            id="kphos-volume"
            type="number"
            min="0.001"
            step="any"
            value="1000"
        >

        <label for="kphos-volume-unit">Volume unit</label>
        <select id="kphos-volume-unit">
            <option value="mL" selected>mL</option>
            <option value="L">L</option>
        </select>

    </div>

    <div class="kphos-section">
        <h3>Potassium phosphate</h3>

        <div class="kphos-grid">

            <label for="kphos-mode">Phosphate preparation method</label>
            <select id="kphos-mode">
                <option value="stocks" selected>From 1 M stocks</option>
                <option value="powder">From powders</option>
            </select>

            <label for="kphos-concentration">
                Final phosphate concentration
            </label>
            <input
                id="kphos-concentration"
                type="number"
                min="0.001"
                step="any"
                value="100"
            >

            <label for="kphos-concentration-unit">
                Phosphate concentration unit
            </label>
            <select id="kphos-concentration-unit">
                <option value="mM" selected>mM</option>
                <option value="M">M</option>
            </select>

            <label for="kphos-ph">Target pH</label>
            <input
                id="kphos-ph"
                type="number"
                min="6.6"
                max="7.6"
                step="0.01"
                value="7.20"
            >

        </div>
    </div>

    <div class="kphos-section">
        <h3>NaCl</h3>

        <div class="kphos-grid">

            <label for="nacl-mode">NaCl preparation method</label>
            <select id="nacl-mode">
                <option value="none">Do not add NaCl</option>
                <option value="powder" selected>From powder</option>
                <option value="stock">From stock solution</option>
            </select>

            <label for="nacl-concentration">
                Final NaCl concentration
            </label>
            <input
                id="nacl-concentration"
                type="number"
                min="0"
                step="any"
                value="100"
            >

            <label for="nacl-concentration-unit">
                NaCl concentration unit
            </label>
            <select id="nacl-concentration-unit">
                <option value="mM" selected>mM</option>
                <option value="M">M</option>
            </select>

            <label for="nacl-stock-concentration">
                NaCl stock concentration
            </label>
            <input
                id="nacl-stock-concentration"
                type="number"
                min="0.001"
                step="any"
                value="5"
            >

            <label for="nacl-stock-unit">
                NaCl stock unit
            </label>
            <select id="nacl-stock-unit">
                <option value="M" selected>M</option>
                <option value="mM">mM</option>
            </select>

        </div>
    </div>

    <div class="kphos-section">
        <h3>Imidazole</h3>

        <div class="kphos-grid">

            <label for="imidazole-mode">
                Imidazole preparation method
            </label>
            <select id="imidazole-mode">
                <option value="none" selected>Do not add imidazole</option>
                <option value="powder">From powder</option>
                <option value="stock">From stock solution</option>
            </select>

            <label for="imidazole-concentration">
                Final imidazole concentration
            </label>
            <input
                id="imidazole-concentration"
                type="number"
                min="0"
                step="any"
                value="500"
            >

            <label for="imidazole-concentration-unit">
                Imidazole concentration unit
            </label>
            <select id="imidazole-concentration-unit">
                <option value="mM" selected>mM</option>
                <option value="M">M</option>
            </select>

            <label for="imidazole-stock-concentration">
                Imidazole stock concentration
            </label>
            <input
                id="imidazole-stock-concentration"
                type="number"
                min="0.001"
                step="any"
                value="5"
            >

            <label for="imidazole-stock-unit">
                Imidazole stock unit
            </label>
            <select id="imidazole-stock-unit">
                <option value="M" selected>M</option>
                <option value="mM">mM</option>
            </select>

        </div>
    </div>

    <button id="kphos-calculate" class="kphos-button">
        Calculate
    </button>

    <div id="kphos-output"></div>
</div>
`;

const ratioTable = [
    { pH: 6.6, acid: 0.640, base: 0.360 },
    { pH: 6.7, acid: 0.596, base: 0.404 },
    { pH: 6.8, acid: 0.530, base: 0.470 },
    { pH: 6.9, acid: 0.480, base: 0.520 },
    { pH: 7.0, acid: 0.422, base: 0.578 },
    { pH: 7.1, acid: 0.368, base: 0.632 },
    { pH: 7.2, acid: 0.329, base: 0.671 },
    { pH: 7.3, acid: 0.268, base: 0.732 },
    { pH: 7.4, acid: 0.224, base: 0.776 },
    { pH: 7.5, acid: 0.188, base: 0.812 },
    { pH: 7.6, acid: 0.156, base: 0.844 }
];

const molecularWeights = {
    kh2po4: 136.09,
    k2hpo4: 174.18,
    nacl: 58.44,
    imidazole: 68.08
};

function getNumber(selector, label, allowZero = false) {
    const value = Number(
        container.querySelector(selector).value
    );

    if (!Number.isFinite(value)) {
        throw new Error(`${label} must be a valid number.`);
    }

    if (allowZero ? value < 0 : value <= 0) {
        throw new Error(
            `${label} must be ${allowZero ? "zero or greater" : "greater than zero"}.`
        );
    }

    return value;
}

function toMolar(value, unit) {
    return unit === "M" ? value : value / 1000;
}

function interpolateRatios(targetPH) {
    const minimumPH = ratioTable[0].pH;
    const maximumPH = ratioTable[ratioTable.length - 1].pH;

    if (targetPH < minimumPH || targetPH > maximumPH) {
        throw new Error(
            `This calculator is limited to pH ${minimumPH.toFixed(2)}–${maximumPH.toFixed(2)}.`
        );
    }

    const exactMatch = ratioTable.find(
        row => Math.abs(row.pH - targetPH) < 0.000001
    );

    if (exactMatch) {
        return {
            acid: exactMatch.acid,
            base: exactMatch.base,
            interpolated: false
        };
    }

    for (let i = 0; i < ratioTable.length - 1; i++) {
        const lower = ratioTable[i];
        const upper = ratioTable[i + 1];

        if (targetPH > lower.pH && targetPH < upper.pH) {
            const fraction =
                (targetPH - lower.pH) /
                (upper.pH - lower.pH);

            return {
                acid:
                    lower.acid +
                    fraction * (upper.acid - lower.acid),

                base:
                    lower.base +
                    fraction * (upper.base - lower.base),

                interpolated: true
            };
        }
    }

    throw new Error("Unable to determine the phosphate ratio.");
}

function formatVolume(volumeML) {
    if (volumeML >= 1000) {
        return `${(volumeML / 1000).toFixed(4)} L`;
    }

    if (volumeML >= 10) {
        return `${volumeML.toFixed(2)} mL`;
    }

    if (volumeML >= 1) {
        return `${volumeML.toFixed(3)} mL`;
    }

    return `${(volumeML * 1000).toFixed(1)} µL`;
}

function formatMass(massG) {
    if (massG >= 10) {
        return `${massG.toFixed(2)} g`;
    }

    if (massG >= 1) {
        return `${massG.toFixed(3)} g`;
    }

    if (massG >= 0.001) {
        return `${(massG * 1000).toFixed(2)} mg`;
    }

    return `${(massG * 1000000).toFixed(1)} µg`;
}

function formatConcentration(concentrationM) {
    if (concentrationM >= 1) {
        return `${concentrationM.toFixed(3)} M`;
    }

    return `${(concentrationM * 1000).toFixed(2)} mM`;
}

function calculateAdditive({
    name,
    mode,
    finalConcentrationM,
    finalVolumeL,
    stockConcentrationM,
    molecularWeight
}) {
    if (mode === "none") {
        return {
            name,
            mode,
            finalConcentrationM: 0,
            moles: 0,
            massG: 0,
            stockVolumeML: 0,
            row: "",
            instruction: ""
        };
    }

    if (finalConcentrationM <= 0) {
        throw new Error(
            `${name} concentration must be greater than zero when ${name} is enabled.`
        );
    }

    const moles =
        finalConcentrationM * finalVolumeL;

    if (mode === "powder") {
        const massG =
            moles * molecularWeight;

        return {
            name,
            mode,
            finalConcentrationM,
            moles,
            massG,
            stockVolumeML: 0,

            row: `
                <tr>
                    <td>
                        ${name} powder<br>
                        <small>MW ${molecularWeight} g/mol</small>
                    </td>
                    <td>
                        <strong>${formatMass(massG)}</strong>
                    </td>
                </tr>
            `,

            instruction: `
                <li>
                    Add
                    <strong>${formatMass(massG)}</strong>
                    of ${name}.
                </li>
            `
        };
    }

    if (mode === "stock") {
        if (
            !Number.isFinite(stockConcentrationM) ||
            stockConcentrationM <= 0
        ) {
            throw new Error(
                `${name} stock concentration must be greater than zero.`
            );
        }

        if (finalConcentrationM > stockConcentrationM) {
            throw new Error(
                `The final ${name} concentration cannot exceed its stock concentration.`
            );
        }

        const stockVolumeL =
            moles / stockConcentrationM;

        const stockVolumeML =
            stockVolumeL * 1000;

        return {
            name,
            mode,
            finalConcentrationM,
            moles,
            massG: 0,
            stockVolumeML,

            row: `
                <tr>
                    <td>
                        ${formatConcentration(stockConcentrationM)}
                        ${name} stock
                    </td>
                    <td>
                        <strong>${formatVolume(stockVolumeML)}</strong>
                    </td>
                </tr>
            `,

            instruction: `
                <li>
                    Add
                    <strong>${formatVolume(stockVolumeML)}</strong>
                    of ${formatConcentration(stockConcentrationM)}
                    ${name} stock.
                </li>
            `
        };
    }

    throw new Error(`Unknown preparation method for ${name}.`);
}

function calculate() {
    const output =
        container.querySelector("#kphos-output");

    try {
        const enteredVolume =
            getNumber(
                "#kphos-volume",
                "Final volume"
            );

        const volumeUnit =
            container.querySelector(
                "#kphos-volume-unit"
            ).value;

        const finalVolumeML =
            volumeUnit === "L"
                ? enteredVolume * 1000
                : enteredVolume;

        const finalVolumeL =
            finalVolumeML / 1000;

        const phosphateMode =
            container.querySelector("#kphos-mode").value;

        const phosphateEntered =
            getNumber(
                "#kphos-concentration",
                "Phosphate concentration"
            );

        const phosphateUnit =
            container.querySelector(
                "#kphos-concentration-unit"
            ).value;

        const finalPhosphateM =
            toMolar(phosphateEntered, phosphateUnit);

        const targetPH =
            getNumber(
                "#kphos-ph",
                "Target pH"
            );

        if (
            phosphateMode === "stocks" &&
            finalPhosphateM > 1
        ) {
            throw new Error(
                "A final phosphate concentration above 1 M cannot be prepared from 1 M phosphate stocks."
            );
        }

        const ratios =
            interpolateRatios(targetPH);

        const totalPhosphateMoles =
            finalPhosphateM * finalVolumeL;

        const acidMoles =
            totalPhosphateMoles * ratios.acid;

        const baseMoles =
            totalPhosphateMoles * ratios.base;

        const naclMode =
            container.querySelector("#nacl-mode").value;

        const naclEntered =
            getNumber(
                "#nacl-concentration",
                "NaCl concentration",
                true
            );

        const naclUnit =
            container.querySelector(
                "#nacl-concentration-unit"
            ).value;

        const finalNaClM =
            naclMode === "none"
                ? 0
                : toMolar(naclEntered, naclUnit);

        const naclStockEntered =
            getNumber(
                "#nacl-stock-concentration",
                "NaCl stock concentration"
            );

        const naclStockUnit =
            container.querySelector(
                "#nacl-stock-unit"
            ).value;

        const naclStockM =
            toMolar(
                naclStockEntered,
                naclStockUnit
            );

        const imidazoleMode =
            container.querySelector(
                "#imidazole-mode"
            ).value;

        const imidazoleEntered =
            getNumber(
                "#imidazole-concentration",
                "Imidazole concentration",
                true
            );

        const imidazoleUnit =
            container.querySelector(
                "#imidazole-concentration-unit"
            ).value;

        const finalImidazoleM =
            imidazoleMode === "none"
                ? 0
                : toMolar(
                    imidazoleEntered,
                    imidazoleUnit
                );

        const imidazoleStockEntered =
            getNumber(
                "#imidazole-stock-concentration",
                "Imidazole stock concentration"
            );

        const imidazoleStockUnit =
            container.querySelector(
                "#imidazole-stock-unit"
            ).value;

        const imidazoleStockM =
            toMolar(
                imidazoleStockEntered,
                imidazoleStockUnit
            );

        const naclResult =
            calculateAdditive({
                name: "NaCl",
                mode: naclMode,
                finalConcentrationM: finalNaClM,
                finalVolumeL,
                stockConcentrationM: naclStockM,
                molecularWeight: molecularWeights.nacl
            });

        const imidazoleResult =
            calculateAdditive({
                name: "imidazole",
                mode: imidazoleMode,
                finalConcentrationM: finalImidazoleM,
                finalVolumeL,
                stockConcentrationM: imidazoleStockM,
                molecularWeight: molecularWeights.imidazole
            });

        let phosphateRows = "";
        let phosphateInstructions = "";
        let phosphateLiquidVolumeML = 0;

        if (phosphateMode === "stocks") {
            const acidStockML =
                acidMoles * 1000;

            const baseStockML =
                baseMoles * 1000;

            phosphateLiquidVolumeML =
                acidStockML + baseStockML;

            phosphateRows = `
                <tr>
                    <td>
                        1 M KH₂PO₄<br>
                        <small>Monobasic stock</small>
                    </td>
                    <td>
                        <strong>${formatVolume(acidStockML)}</strong>
                    </td>
                </tr>

                <tr>
                    <td>
                        1 M K₂HPO₄<br>
                        <small>Dibasic stock</small>
                    </td>
                    <td>
                        <strong>${formatVolume(baseStockML)}</strong>
                    </td>
                </tr>
            `;

            phosphateInstructions = `
                <li>
                    Add
                    <strong>${formatVolume(acidStockML)}</strong>
                    of 1 M KH₂PO₄.
                </li>

                <li>
                    Add
                    <strong>${formatVolume(baseStockML)}</strong>
                    of 1 M K₂HPO₄.
                </li>
            `;
        }

        if (phosphateMode === "powder") {
            const acidMassG =
                acidMoles *
                molecularWeights.kh2po4;

            const baseMassG =
                baseMoles *
                molecularWeights.k2hpo4;

            phosphateRows = `
                <tr>
                    <td>
                        KH₂PO₄ powder<br>
                        <small>
                            MW ${molecularWeights.kh2po4} g/mol
                        </small>
                    </td>
                    <td>
                        <strong>${formatMass(acidMassG)}</strong>
                    </td>
                </tr>

                <tr>
                    <td>
                        K₂HPO₄ powder<br>
                        <small>
                            Anhydrous; MW
                            ${molecularWeights.k2hpo4} g/mol
                        </small>
                    </td>
                    <td>
                        <strong>${formatMass(baseMassG)}</strong>
                    </td>
                </tr>
            `;

            phosphateInstructions = `
                <li>
                    Add
                    <strong>${formatMass(acidMassG)}</strong>
                    of KH₂PO₄.
                </li>

                <li>
                    Add
                    <strong>${formatMass(baseMassG)}</strong>
                    of anhydrous K₂HPO₄.
                </li>
            `;
        }

        const totalLiquidStockML =
            phosphateLiquidVolumeML +
            naclResult.stockVolumeML +
            imidazoleResult.stockVolumeML;

        if (totalLiquidStockML > finalVolumeML) {
            throw new Error(
                `The required liquid stocks total ${formatVolume(totalLiquidStockML)}, which exceeds the final volume of ${formatVolume(finalVolumeML)}. Use more concentrated stocks or prepare one or more components from powder.`
            );
        }

        const approximateWaterCapacityML =
            finalVolumeML - totalLiquidStockML;

        const targetParts = [
            `${formatConcentration(finalPhosphateM)} potassium phosphate`,
            `pH ${targetPH.toFixed(2)}`
        ];

        if (naclMode !== "none") {
            targetParts.push(
                `${formatConcentration(finalNaClM)} NaCl`
            );
        }

        if (imidazoleMode !== "none") {
            targetParts.push(
                `${formatConcentration(finalImidazoleM)} imidazole`
            );
        }

        const imidazoleWarning =
            imidazoleMode !== "none"
                ? `
                    <div class="kphos-note">
                        <strong>Imidazole and pH:</strong>
                        imidazole can substantially change the measured
                        pH. Add it before the final pH measurement and
                        before bringing the buffer to final volume.
                    </div>
                `
                : "";

        output.innerHTML = `
            <div class="kphos-result">

                <h3>Preparation result</h3>

                <p>
                    <strong>Target buffer:</strong><br>
                    ${targetParts.join("<br>")}<br>
                    Final volume:
                    ${formatVolume(finalVolumeML)}
                </p>

                <table>
                    <tr>
                        <th>Component</th>
                        <th>Required amount</th>
                    </tr>

                    ${phosphateRows}
                    ${naclResult.row}
                    ${imidazoleResult.row}

                    <tr>
                        <td>Total liquid stock volume</td>
                        <td>
                            ${formatVolume(totalLiquidStockML)}
                        </td>
                    </tr>

                    <tr>
                        <td>
                            Approximate remaining volume for water
                        </td>
                        <td>
                            ${formatVolume(approximateWaterCapacityML)}
                        </td>
                    </tr>
                </table>

                <h4>Phosphate proportions</h4>

                <p>
                    KH₂PO₄:
                    <strong>
                        ${(ratios.acid * 100).toFixed(2)}%
                    </strong>
                    <br>

                    K₂HPO₄:
                    <strong>
                        ${(ratios.base * 100).toFixed(2)}%
                    </strong>
                </p>

                ${
                    ratios.interpolated
                        ? `
                            <p>
                                <em>
                                    The phosphate ratio was linearly
                                    interpolated between adjacent
                                    reference pH values.
                                </em>
                            </p>
                        `
                        : ""
                }

                <h4>Preparation procedure</h4>

                <ol>
                    <li>
                        Add approximately 60–70% of the final
                        volume as ultrapure water.
                    </li>

                    ${phosphateInstructions}
                    ${naclResult.instruction}
                    ${imidazoleResult.instruction}

                    <li>
                        Mix until all components are completely
                        dissolved.
                    </li>

                    <li>
                        Measure the pH at the intended working
                        temperature.
                    </li>

                    <li>
                        Adjust the pH carefully if required.
                    </li>

                    <li>
                        Bring the solution to a final volume of
                        <strong>${formatVolume(finalVolumeML)}</strong>.
                    </li>

                    <li>
                        Mix again and confirm the final pH.
                    </li>

                    <li>
                        Filter-sterilize or store as required by
                        the experimental protocol.
                    </li>
                </ol>

                <p>
                    Do not add
                    ${formatVolume(approximateWaterCapacityML)}
                    of water directly. This is only the approximate
                    volume remaining after liquid stocks. Begin below
                    the final volume and bring to volume only after
                    pH adjustment.
                </p>

                ${imidazoleWarning}

                <div class="kphos-note">
                    <strong>Salt forms:</strong>
                    phosphate powder calculations assume anhydrous
                    KH₂PO₄ and anhydrous K₂HPO₄. Check the reagent
                    labels before weighing.
                </div>

            </div>
        `;
    } catch (error) {
        output.innerHTML = `
            <div class="kphos-error">
                <strong>Calculation error:</strong>
                ${error.message}
            </div>
        `;
    }
}

container
    .querySelector("#kphos-calculate")
    .addEventListener("click", calculate);

calculate();
```

## Calculation basis

### Total phosphate

The required total amount of phosphate is:

$$
n_{\mathrm{phosphate}}
=
C_{\mathrm{phosphate}}
\times
V_{\mathrm{final}}
$$

where:

- $n_{\mathrm{phosphate}}$ is the total amount of phosphate in moles
- $C_{\mathrm{phosphate}}$ is the final phosphate concentration
- $V_{\mathrm{final}}$ is the final buffer volume

The total phosphate is divided between monobasic and dibasic phosphate:

$$
n_{\mathrm{KH_2PO_4}}
=
n_{\mathrm{phosphate}}
\times
f_{\mathrm{acid}}
$$

$$
n_{\mathrm{K_2HPO_4}}
=
n_{\mathrm{phosphate}}
\times
f_{\mathrm{base}}
$$

The fractions satisfy:

$$
f_{\mathrm{acid}}
+
f_{\mathrm{base}}
=
1
$$

### Phosphate from 1 M stocks

For each phosphate stock:

$$
V_{\mathrm{stock}}
=
\frac{
n_{\mathrm{component}}
}{
C_{\mathrm{stock}}
}
$$

For this calculator:

$$
C_{\mathrm{stock}}
=
1\ \mathrm{mol\,L^{-1}}
$$

Therefore:

$$
V_{\mathrm{KH_2PO_4}}
=
\frac{
n_{\mathrm{KH_2PO_4}}
}{
1\ \mathrm{mol\,L^{-1}}
}
$$

$$
V_{\mathrm{K_2HPO_4}}
=
\frac{
n_{\mathrm{K_2HPO_4}}
}{
1\ \mathrm{mol\,L^{-1}}
}
$$

### Phosphate from powders

The required mass is:

$$
m
=
n
\times
M_{\mathrm{W}}
$$

Therefore:

$$
m_{\mathrm{KH_2PO_4}}
=
n_{\mathrm{KH_2PO_4}}
\times
136.09\ \mathrm{g\,mol^{-1}}
$$

$$
m_{\mathrm{K_2HPO_4}}
=
n_{\mathrm{K_2HPO_4}}
\times
174.18\ \mathrm{g\,mol^{-1}}
$$

### NaCl

The required amount of NaCl is:

$$
n_{\mathrm{NaCl}}
=
C_{\mathrm{NaCl}}
\times
V_{\mathrm{final}}
$$

When using powder:

$$
m_{\mathrm{NaCl}}
=
n_{\mathrm{NaCl}}
\times
58.44\ \mathrm{g\,mol^{-1}}
$$

When using a stock solution:

$$
V_{\mathrm{NaCl\ stock}}
=
\frac{
C_{\mathrm{NaCl,final}}
\times
V_{\mathrm{final}}
}{
C_{\mathrm{NaCl,stock}}
}
$$

### Imidazole

The required amount of imidazole is:

$$
n_{\mathrm{imidazole}}
=
C_{\mathrm{imidazole}}
\times
V_{\mathrm{final}}
$$

When using powder:

$$
m_{\mathrm{imidazole}}
=
n_{\mathrm{imidazole}}
\times
68.08\ \mathrm{g\,mol^{-1}}
$$

When using a stock solution:

$$
V_{\mathrm{imidazole\ stock}}
=
\frac{
C_{\mathrm{imidazole,final}}
\times
V_{\mathrm{final}}
}{
C_{\mathrm{imidazole,stock}}
}
$$

## Molecular weights

| Compound | Assumed form | Molecular weight |
|---|---|---:|
| KH₂PO₄ | anhydrous | 136.09 g/mol |
| K₂HPO₄ | anhydrous | 174.18 g/mol |
| NaCl | anhydrous | 58.44 g/mol |
| Imidazole | free base | 68.08 g/mol |

> [!important]
> This calculator assumes imidazole free base, not imidazole hydrochloride. It also assumes anhydrous K₂HPO₄. Confirm the compound name, formula, hydration state, and molecular weight on each reagent bottle.

> [!note]
> Imidazole should be added before final pH adjustment. Do not prepare the phosphate solution at the target pH, add concentrated imidazole afterward, and assume that the pH remains unchanged.