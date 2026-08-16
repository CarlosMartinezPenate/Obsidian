---
title: Tricine KCl Extraction Buffer Calculator
aliases:
  - Tricine KCl Calculator
  - PCP Extraction Buffer Calculator
tags:
  - protocol
  - buffer
  - calculator
target_tricine_mM: 50
target_kcl_mM: 20
target_pH: 7.5
---

This calculator prepares:

- **50 mM Tricine**
- **20 mM KCl**
- **pH 7.5**

## Reagents

### Tricine

- CAS: 5704-04-1
- Formula: C₆H₁₃NO₅
- MW: **179.17 g/mol**

### KCl

- SDFCL
- Product code: 39594
- Formula: KCl
- MW: **74.55 g/mol**

### KOH

- Biolab Ltd.
- Cat. No.: 16490291
- Formula: KOH
- CAS: 1310-58-3
- MW: **56.11 g/mol**
- Form: flakes

> [!warning]
> The published extraction buffer is **50 mM Tricine + 20 mM KCl, pH 7.5**.
>
> The publication does not specify which reagent was used for pH adjustment. KOH is used here as the working pH-adjustment reagent.
>
> KOH is **not** assigned a fixed concentration in the final extraction buffer. Add KOH gradually while measuring pH.

> [!danger]
> KOH is strongly corrosive and releases considerable heat when dissolved.
>
> - Wear appropriate eye protection, gloves, and lab coat.
> - Add KOH flakes gradually **to water**.
> - Do not pour water onto concentrated KOH flakes.
> - Allow the KOH solution to cool before bringing it to final volume.

```dataviewjs
const container = dv.el("div", "");

container.innerHTML = `
<style>
.tricine-calculator {
    max-width: 760px;
    padding: 18px;
    border: 1px solid var(--background-modifier-border);
    border-radius: 10px;
    background: var(--background-secondary);
}

.tricine-calculator h3 {
    margin-top: 0;
}

.tricine-section {
    margin-top: 18px;
    padding-top: 14px;
    border-top: 1px solid var(--background-modifier-border);
}

.tricine-grid {
    display: grid;
    grid-template-columns: minmax(240px, 1fr) minmax(160px, 220px);
    gap: 12px;
    align-items: center;
}

.tricine-grid input,
.tricine-grid select {
    width: 100%;
    box-sizing: border-box;
}

.tricine-button {
    margin-top: 18px;
    padding: 8px 18px;
    cursor: pointer;
}

.tricine-result {
    margin-top: 18px;
    padding: 14px;
    border: 1px solid var(--background-modifier-border);
    border-radius: 8px;
    background: var(--background-primary);
}

.tricine-result table {
    width: 100%;
    border-collapse: collapse;
}

.tricine-result th,
.tricine-result td {
    padding: 7px;
    border-bottom: 1px solid var(--background-modifier-border);
    text-align: left;
    vertical-align: top;
}

.tricine-note {
    margin-top: 12px;
    padding: 10px;
    border-left: 4px solid var(--interactive-accent);
    background: var(--background-primary);
}

.tricine-error {
    margin-top: 16px;
    padding: 12px;
    border-radius: 8px;
    background: var(--background-modifier-error);
    color: var(--text-error);
}
</style>

<div class="tricine-calculator">

    <h3>Final extraction buffer</h3>

    <div class="tricine-grid">

        <label for="buffer-volume">
            Final buffer volume
        </label>

        <input
            id="buffer-volume"
            type="number"
            min="0.1"
            step="any"
            value="75"
        >

        <label for="buffer-volume-unit">
            Volume unit
        </label>

        <select id="buffer-volume-unit">
            <option value="mL" selected>mL</option>
            <option value="L">L</option>
        </select>

    </div>

    <div class="tricine-section">

        <h3>Buffer composition</h3>

        <div class="tricine-grid">

            <label for="tricine-concentration">
                Tricine concentration (mM)
            </label>

            <input
                id="tricine-concentration"
                type="number"
                min="0.001"
                step="any"
                value="50"
            >

            <label for="kcl-concentration">
                KCl concentration (mM)
            </label>

            <input
                id="kcl-concentration"
                type="number"
                min="0.001"
                step="any"
                value="20"
            >

            <label for="target-ph">
                Target pH
            </label>

            <input
                id="target-ph"
                type="number"
                min="1"
                max="14"
                step="0.01"
                value="7.50"
            >

        </div>

    </div>

    <div class="tricine-section">

        <h3>KOH stock</h3>

        <div class="tricine-grid">

            <label for="koh-stock-concentration">
                KOH stock concentration
            </label>

            <input
                id="koh-stock-concentration"
                type="number"
                min="0.001"
                step="any"
                value="1"
            >

            <label for="koh-stock-concentration-unit">
                Concentration unit
            </label>

            <select id="koh-stock-concentration-unit">
                <option value="M" selected>M</option>
                <option value="mM">mM</option>
            </select>

            <label for="koh-stock-volume">
                KOH stock final volume
            </label>

            <input
                id="koh-stock-volume"
                type="number"
                min="0.1"
                step="any"
                value="50"
            >

            <label for="koh-stock-volume-unit">
                Volume unit
            </label>

            <select id="koh-stock-volume-unit">
                <option value="mL" selected>mL</option>
                <option value="L">L</option>
            </select>

        </div>

    </div>

    <button
        id="calculate-buffer"
        class="tricine-button"
    >
        Calculate
    </button>

    <div id="buffer-output"></div>

</div>
`;

const MW = {
    tricine: 179.17,
    kcl: 74.55,
    koh: 56.11
};

function getPositiveNumber(selector, label) {

    const value = Number(
        container.querySelector(selector).value
    );

    if (!Number.isFinite(value) || value <= 0) {
        throw new Error(
            `${label} must be greater than zero.`
        );
    }

    return value;
}

function formatMass(g) {

    if (g >= 10) {
        return `${g.toFixed(2)} g`;
    }

    if (g >= 1) {
        return `${g.toFixed(3)} g`;
    }

    if (g >= 0.001) {
        return `${(g * 1000).toFixed(2)} mg`;
    }

    return `${(g * 1000000).toFixed(1)} µg`;
}

function formatVolume(mL) {

    if (mL >= 1000) {
        return `${(mL / 1000).toFixed(3)} L`;
    }

    if (mL >= 10) {
        return `${mL.toFixed(1)} mL`;
    }

    if (mL >= 1) {
        return `${mL.toFixed(2)} mL`;
    }

    return `${(mL * 1000).toFixed(1)} µL`;
}

function formatConcentration(M) {

    if (M >= 1) {
        return `${M.toFixed(3)} M`;
    }

    return `${(M * 1000).toFixed(1)} mM`;
}

function calculate() {

    const output =
        container.querySelector("#buffer-output");

    try {

        // ---------------------------
        // Final buffer
        // ---------------------------

        const bufferVolumeEntered =
            getPositiveNumber(
                "#buffer-volume",
                "Final buffer volume"
            );

        const bufferVolumeUnit =
            container.querySelector(
                "#buffer-volume-unit"
            ).value;

        const bufferVolumeML =
            bufferVolumeUnit === "L"
                ? bufferVolumeEntered * 1000
                : bufferVolumeEntered;

        const bufferVolumeL =
            bufferVolumeML / 1000;

        const tricineMM =
            getPositiveNumber(
                "#tricine-concentration",
                "Tricine concentration"
            );

        const kclMM =
            getPositiveNumber(
                "#kcl-concentration",
                "KCl concentration"
            );

        const targetPH =
            getPositiveNumber(
                "#target-ph",
                "Target pH"
            );

        const tricineM =
            tricineMM / 1000;

        const kclM =
            kclMM / 1000;

        const tricineMoles =
            tricineM * bufferVolumeL;

        const kclMoles =
            kclM * bufferVolumeL;

        const tricineMassG =
            tricineMoles * MW.tricine;

        const kclMassG =
            kclMoles * MW.kcl;

        const startingWaterML =
            bufferVolumeML * 0.75;

        // ---------------------------
        // KOH stock
        // ---------------------------

        const kohConcentrationEntered =
            getPositiveNumber(
                "#koh-stock-concentration",
                "KOH stock concentration"
            );

        const kohConcentrationUnit =
            container.querySelector(
                "#koh-stock-concentration-unit"
            ).value;

        const kohConcentrationM =
            kohConcentrationUnit === "M"
                ? kohConcentrationEntered
                : kohConcentrationEntered / 1000;

        const kohVolumeEntered =
            getPositiveNumber(
                "#koh-stock-volume",
                "KOH stock volume"
            );

        const kohVolumeUnit =
            container.querySelector(
                "#koh-stock-volume-unit"
            ).value;

        const kohVolumeML =
            kohVolumeUnit === "L"
                ? kohVolumeEntered * 1000
                : kohVolumeEntered;

        const kohVolumeL =
            kohVolumeML / 1000;

        const kohMoles =
            kohConcentrationM * kohVolumeL;

        const kohMassG =
            kohMoles * MW.koh;

        // ---------------------------
        // Output
        // ---------------------------

        output.innerHTML = `
            <div class="tricine-result">

                <h3>Extraction buffer result</h3>

                <p>
                    <strong>Target</strong><br>
                    ${tricineMM.toFixed(1)} mM Tricine<br>
                    ${kclMM.toFixed(1)} mM KCl<br>
                    pH ${targetPH.toFixed(2)}<br>
                    Final volume:
                    <strong>${formatVolume(bufferVolumeML)}</strong>
                </p>

                <table>

                    <tr>
                        <th>Reagent</th>
                        <th>Amount to weigh</th>
                    </tr>

                    <tr>
                        <td>
                            Tricine
                            <br>
                            <small>
                                MW ${MW.tricine} g/mol
                            </small>
                        </td>

                        <td>
                            <strong>
                                ${formatMass(tricineMassG)}
                            </strong>
                        </td>
                    </tr>

                    <tr>
                        <td>
                            KCl
                            <br>
                            <small>
                                MW ${MW.kcl} g/mol
                            </small>
                        </td>

                        <td>
                            <strong>
                                ${formatMass(kclMassG)}
                            </strong>
                        </td>
                    </tr>

                </table>

                <h4>Preparation</h4>

                <ol>

                    <li>
                        Add approximately
                        <strong>
                            ${formatVolume(startingWaterML)}
                        </strong>
                        DI or ultrapure water.
                    </li>

                    <li>
                        Add
                        <strong>
                            ${formatMass(tricineMassG)}
                        </strong>
                        Tricine.
                    </li>

                    <li>
                        Add
                        <strong>
                            ${formatMass(kclMassG)}
                        </strong>
                        KCl.
                    </li>

                    <li>
                        Mix until completely dissolved.
                    </li>

                    <li>
                        Measure the pH.
                    </li>

                    <li>
                        Add KOH stock gradually while stirring
                        until
                        <strong>
                            pH ${targetPH.toFixed(2)}
                        </strong>
                        is reached.
                    </li>

                    <li>
                        Bring to a final volume of
                        <strong>
                            ${formatVolume(bufferVolumeML)}
                        </strong>
                        with water.
                    </li>

                    <li>
                        Mix and confirm the final pH.
                    </li>

                    <li>
                        Chill to approximately
                        <strong>4 °C</strong>
                        before extraction.
                    </li>

                </ol>

                <div class="tricine-note">
                    <strong>KOH addition:</strong>
                    the required volume of KOH is intentionally
                    not calculated. Add it empirically while
                    measuring pH.
                </div>


                <div class="tricine-section">

                    <h3>KOH stock result</h3>

                    <p>
                        To prepare
                        <strong>
                            ${formatVolume(kohVolumeML)}
                        </strong>
                        of
                        <strong>
                            ${formatConcentration(kohConcentrationM)}
                        </strong>
                        KOH:
                    </p>

                    <table>

                        <tr>
                            <th>Reagent</th>
                            <th>Amount</th>
                        </tr>

                        <tr>
                            <td>
                                KOH flakes
                                <br>
                                <small>
                                    MW ${MW.koh} g/mol
                                </small>
                            </td>

                            <td>
                                <strong>
                                    ${formatMass(kohMassG)}
                                </strong>
                            </td>
                        </tr>

                        <tr>
                            <td>
                                Final stock volume
                            </td>

                            <td>
                                <strong>
                                    ${formatVolume(kohVolumeML)}
                                </strong>
                            </td>
                        </tr>

                    </table>

                    <h4>KOH preparation</h4>

                    <ol>

                        <li>
                            Add approximately 70–80% of the
                            intended final volume as DI water
                            to a suitable container.
                        </li>

                        <li>
                            Slowly add
                            <strong>
                                ${formatMass(kohMassG)}
                            </strong>
                            KOH flakes while stirring.
                        </li>

                        <li>
                            Allow the solution to cool completely.
                        </li>

                        <li>
                            Bring to
                            <strong>
                                ${formatVolume(kohVolumeML)}
                            </strong>
                            with DI water.
                        </li>

                        <li>
                            Mix thoroughly and label with
                            concentration and preparation date.
                        </li>

                    </ol>

                </div>

            </div>
        `;

    } catch (error) {

        output.innerHTML = `
            <div class="tricine-error">
                <strong>Calculation error:</strong>
                ${error.message}
            </div>
        `;

    }
}

container
    .querySelector("#calculate-buffer")
    .addEventListener("click", calculate);

calculate();
```

# Calculation basis

## Tricine

The required amount of Tricine is:

$$
n_{\mathrm{Tricine}}
=
C_{\mathrm{Tricine}}
\times
V_{\mathrm{final}}
$$

The required mass is:

$$
m_{\mathrm{Tricine}}
=
n_{\mathrm{Tricine}}
\times
MW_{\mathrm{Tricine}}
$$

Using:

$$
MW_{\mathrm{Tricine}}
=
179.17\ \mathrm{g\,mol^{-1}}
$$

therefore:

$$
m_{\mathrm{Tricine}}
=
C_{\mathrm{Tricine}}
\times
V_{\mathrm{final}}
\times
179.17
$$

## KCl

The required amount of KCl is:

$$
n_{\mathrm{KCl}}
=
C_{\mathrm{KCl}}
\times
V_{\mathrm{final}}
$$

and:

$$
m_{\mathrm{KCl}}
=
n_{\mathrm{KCl}}
\times
74.55\ \mathrm{g\,mol^{-1}}
$$

## KOH stock

For a KOH stock:

$$
n_{\mathrm{KOH}}
=
C_{\mathrm{KOH}}
\times
V_{\mathrm{stock}}
$$

and:

$$
m_{\mathrm{KOH}}
=
n_{\mathrm{KOH}}
\times
56.11\ \mathrm{g\,mol^{-1}}
$$

For example, for **50 mL of 1 M KOH**:

$$
m_{\mathrm{KOH}}
=
1\ \mathrm{mol\,L^{-1}}
\times
0.050\ \mathrm{L}
\times
56.11\ \mathrm{g\,mol^{-1}}
$$

$$
m_{\mathrm{KOH}}
=
2.8055\ \mathrm{g}
$$

# Molecular weights

| Compound | Formula | Molecular weight |
|---|---|---:|
| Tricine | C₆H₁₃NO₅ | 179.17 g/mol |
| KCl | KCl | 74.55 g/mol |
| KOH | KOH | 56.11 g/mol |

> [!important]
> For the published extraction buffer, normally change only the **final volume**:
>
> - Tricine: **50 mM**
> - KCl: **20 mM**
> - pH: **7.50**

> [!note]
> KOH is used only to reach the target pH. Its final concentration in the extraction buffer is therefore not predefined.

> [!danger]
> KOH is corrosive and its dissolution is strongly exothermic. Add KOH to water slowly and allow the solution to cool before bringing it to final volume.