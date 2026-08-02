---
title: Ethanol Dilution Calculator
aliases:
  - Ethanol Calculator
  - Alcohol Dilution Calculator
tags:
  - protocol
  - calculator
  - ethanol
---

# Ethanol Dilution Calculator

Calculate how much stock ethanol and water are required to prepare:

- **20% (v/v) ethanol from absolute ethanol (100%)**
- **70% (v/v) ethanol from 96% ethanol**

---

# Principle

The calculation follows the dilution equation:

$begin:math:display$
C\_1V\_1\=C\_2V\_2
$end:math:display$

where:

- **C₁** = stock ethanol concentration (%)
- **V₁** = stock ethanol volume
- **C₂** = desired concentration (%)
- **V₂** = final volume

Water volume is simply:

$begin:math:display$
V\_\{water\}\=V\_2\-V\_1
$end:math:display$

---

# Calculator

```dataviewjs
const container = dv.el("div", "");

container.innerHTML = `
<style>
.ethanol-calculator{
max-width:700px;
padding:18px;
border:1px solid var(--background-modifier-border);
border-radius:10px;
background:var(--background-secondary);
}

.ethanol-calculator h3{
margin-top:0;
}

.ethanol-calculator label{
display:block;
margin-top:12px;
font-weight:600;
}

.ethanol-calculator input,
.ethanol-calculator select{
width:100%;
padding:8px;
margin-top:5px;
border-radius:6px;
}

.ethanol-result{
margin-top:18px;
padding:14px;
border-radius:8px;
background:var(--background-primary);
border:1px solid var(--background-modifier-border);
line-height:1.7;
}

.big{
font-size:1.15em;
font-weight:bold;
}
</style>

<div class="ethanol-calculator">

<h3>Ethanol Dilution Calculator</h3>

<label>Preparation</label>

<select id="prep">
<option value="20">20% from Absolute (100%)</option>
<option value="70">70% from 96%</option>
</select>

<label>Final volume (mL)</label>

<input
id="volume"
type="number"
value="1000"
min="1"
step="1"
/>

<div class="ethanol-result" id="output"></div>

</div>
`;

const prep = container.querySelector("#prep");
const volume = container.querySelector("#volume");
const output = container.querySelector("#output");

function update(){

const V2 = parseFloat(volume.value);

if(isNaN(V2) || V2<=0){
output.innerHTML="Enter a valid volume.";
return;
}

let C1;
let C2;

if(prep.value==="20"){
C1=100;
C2=20;
}else{
C1=96;
C2=70;
}

const V1=(C2*V2)/C1;
const water=V2-V1;

output.innerHTML=`
<div class="big">Prepare ${V2.toFixed(1)} mL</div>

<b>Stock ethanol:</b><br>
${V1.toFixed(1)} mL

<br><br>

<b>Water:</b><br>
${water.toFixed(1)} mL

<br><br>

<b>Check</b><br>
${C1}% ethanol × ${V1.toFixed(1)} mL → ${C2}% final
`;
}

prep.oninput=update;
volume.oninput=update;

update();
```

---

# Examples

## 20% ethanol from absolute ethanol

|Final volume|Absolute ethanol|Water|
|------------:|---------------:|----:|
|100 mL|20 mL|80 mL|
|500 mL|100 mL|400 mL|
|1 L|200 mL|800 mL|
|2 L|400 mL|1600 mL|
|4 L|800 mL|3200 mL|

---

## 70% ethanol from 96% ethanol

|Final volume|96% ethanol|Water|
|------------:|----------:|----:|
|100 mL|72.9 mL|27.1 mL|
|500 mL|364.6 mL|135.4 mL|
|1 L|729.2 mL|270.8 mL|
|2 L|1458.3 mL|541.7 mL|
|4 L|2916.7 mL|1083.3 mL|

---

# Notes

> [!warning]
> These calculations assume **v/v percentages**.

> [!tip]
> For accurate laboratory preparations:
>
> - Use volumetric glassware whenever possible.
> - Add ethanol first, then bring to the final volume with water.
> - Label the final concentration, preparation date, and preparer.