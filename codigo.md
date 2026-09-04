<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="color-scheme" content="light">
<meta name="description" content="Comparador de mercados y simulador de rentabilidad para servicios web entre Los Ángeles, La Paz y San Salvador.">
<title>Comparador Web · 3 Mercados</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">

<style>
/* ================================================================
   DESIGN TOKENS
   ================================================================ */
:root{
  --lime:#00DD00;
  --lime-deep:#00A300;
  --lime-ink:#086B10;
  --lime-wash:#EAFBEA;

  --ink:#0A130B;
  --ink-2:#3A463B;
  --muted:#77857A;

  --line:#E2E9E3;
  --line-strong:#CAD5CC;
  --panel:#F5F8F5;
  --white:#FFFFFF;

  --red:#D73E3E;
  --red-wash:#FDF0F0;

  --amber:#C98508;
  --amber-wash:#FDF8EC;

  --blue:#3267D6;
  --blue-wash:#EEF3FF;

  --shadow:
    0 1px 2px rgba(10,19,11,.04),
    0 8px 24px rgba(10,19,11,.05);

  --shadow-hover:
    0 2px 4px rgba(10,19,11,.05),
    0 14px 34px rgba(10,19,11,.08);

  --radius:14px;
  --radius-lg:18px;

  --display:"Space Grotesk",system-ui,sans-serif;
  --mono:"IBM Plex Mono",ui-monospace,SFMono-Regular,Menlo,monospace;
  --body:"Inter",system-ui,sans-serif;
}

*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

html{
  scroll-behavior:smooth;
}

body{
  font-family:var(--body);
  color:var(--ink);
  background:var(--white);
  line-height:1.5;
  -webkit-font-smoothing:antialiased;
  text-rendering:optimizeLegibility;
}

button,
input{
  font:inherit;
}

button{
  -webkit-tap-highlight-color:transparent;
}

button:focus-visible,
input:focus-visible{
  outline:3px solid rgba(0,221,0,.30);
  outline-offset:2px;
}

::selection{
  background:var(--lime);
  color:var(--ink);
}

[hidden]{
  display:none !important;
}

/* ================================================================
   HEADER
   ================================================================ */
header{
  position:sticky;
  top:0;
  z-index:50;
  background:rgba(255,255,255,.90);
  backdrop-filter:saturate(1.35) blur(12px);
  -webkit-backdrop-filter:saturate(1.35) blur(12px);
  border-bottom:1px solid var(--line);
}

.bar{
  max-width:1160px;
  margin:0 auto;
  padding:13px 22px;
  display:flex;
  align-items:center;
  gap:14px;
  flex-wrap:wrap;
}

.wordmark{
  display:flex;
  align-items:center;
  gap:11px;
  font-family:var(--display);
  font-weight:700;
  letter-spacing:-.02em;
  white-space:nowrap;
}

.beacon{
  width:11px;
  height:11px;
  border-radius:50%;
  background:var(--lime);
  box-shadow:0 0 0 4px var(--lime-wash);
  animation:pulse 2.4s ease-in-out infinite;
}

@keyframes pulse{
  0%,100%{opacity:1}
  50%{opacity:.45}
}

.wordmark small{
  font-family:var(--mono);
  font-weight:500;
  color:var(--muted);
  font-size:11px;
  letter-spacing:.14em;
  text-transform:uppercase;
  border-left:1px solid var(--line);
  padding-left:11px;
}

.bar-clock{
  margin-left:auto;
  font-family:var(--mono);
  font-size:12px;
  color:var(--ink-2);
  display:flex;
  align-items:center;
  gap:8px;
  white-space:nowrap;
}

.bar-clock b{
  color:var(--ink);
  font-weight:600;
  font-variant-numeric:tabular-nums;
}

.tabs{
  display:flex;
  gap:3px;
  background:var(--panel);
  border:1px solid var(--line);
  border-radius:11px;
  padding:4px;
}

.tab{
  font-family:var(--display);
  font-weight:600;
  font-size:13px;
  color:var(--ink-2);
  background:none;
  border:0;
  cursor:pointer;
  padding:7px 12px;
  border-radius:8px;
  transition:.16s ease;
  white-space:nowrap;
}

.tab[aria-selected="true"]{
  background:var(--ink);
  color:var(--white);
}

.tab:hover:not([aria-selected="true"]){
  color:var(--ink);
  background:#EDF2ED;
}

/* ================================================================
   HERO
   ================================================================ */
.hero{
  max-width:1160px;
  margin:0 auto;
  padding:44px 22px 12px;
}

.eyebrow{
  font-family:var(--mono);
  font-size:12px;
  letter-spacing:.18em;
  text-transform:uppercase;
  color:var(--lime-ink);
  font-weight:500;
  margin-bottom:14px;
  display:flex;
  align-items:center;
  gap:9px;
}

.eyebrow::before{
  content:"";
  width:26px;
  height:2px;
  background:var(--lime);
}

h1{
  font-family:var(--display);
  font-weight:700;
  font-size:clamp(32px,5vw,54px);
  letter-spacing:-.04em;
  line-height:1.01;
  max-width:16ch;
}

h1 em{
  font-style:normal;
  color:var(--lime-deep);
}

.lede{
  color:var(--ink-2);
  font-size:17px;
  max-width:62ch;
  margin-top:16px;
}

.wall{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:16px;
  margin:34px 0 8px;
}

.citycard{
  position:relative;
  min-height:330px;
  border-radius:var(--radius-lg);
  overflow:hidden;
  isolation:isolate;
  display:flex;
  align-items:center;
  justify-content:center;
  text-align:center;
  background:linear-gradient(160deg,#0B3D17,#052209);
  box-shadow:var(--shadow);
  transition:
    transform .25s ease,
    box-shadow .25s ease;
}

.citycard:hover{
  transform:translateY(-2px);
  box-shadow:var(--shadow-hover);
}

.citycard img.bg{
  position:absolute;
  inset:0;
  width:100%;
  height:100%;
  object-fit:cover;
  z-index:0;
  filter:saturate(.90) brightness(.82);
  transform:scale(1.025);
  transition:transform .6s ease;
}

.citycard:hover img.bg{
  transform:scale(1.065);
}

.citycard .tint{
  position:absolute;
  inset:0;
  z-index:1;
  background:rgba(0,150,0,.30);
  mix-blend-mode:multiply;
}

.citycard .grad{
  position:absolute;
  inset:0;
  z-index:2;
  background:
    linear-gradient(
      180deg,
      rgba(3,30,10,.34) 0%,
      rgba(3,30,10,.08) 38%,
      rgba(2,18,6,.83) 100%
    );
}

.citycard .content{
  position:relative;
  z-index:3;
  color:#fff;
  padding:24px 16px;
  display:flex;
  flex-direction:column;
  align-items:center;
  gap:2px;
  width:100%;
}

.citycard svg{
  width:108px;
  height:108px;
  filter:drop-shadow(0 4px 12px rgba(0,0,0,.35));
}

.citycard .city{
  font-family:var(--display);
  font-weight:600;
  font-size:18px;
  margin-top:12px;
}

.citycard .country{
  font-size:12px;
  color:rgba(255,255,255,.82);
}

.citycard .digital{
  font-family:var(--mono);
  font-weight:600;
  font-size:22px;
  margin-top:9px;
  font-variant-numeric:tabular-nums;
  text-shadow:0 1px 10px rgba(0,0,0,.45);
}

.citycard .meta{
  font-family:var(--mono);
  font-size:11px;
  color:rgba(255,255,255,.72);
  margin-top:2px;
  display:flex;
  gap:8px;
}

.citycard .status{
  display:inline-flex;
  align-items:center;
  gap:6px;
  font-family:var(--mono);
  font-size:11px;
  margin-top:11px;
  padding:4px 12px;
  border-radius:20px;
  border:1px solid rgba(255,255,255,.25);
  backdrop-filter:blur(4px);
}

.citycard .status .dot{
  width:7px;
  height:7px;
  border-radius:50%;
}

.citycard .status.open{
  color:#fff;
  background:rgba(0,221,0,.22);
  border-color:rgba(0,221,0,.5);
}

.citycard .status.open .dot{
  background:var(--lime);
  box-shadow:0 0 0 3px rgba(0,221,0,.3);
}

.citycard .status.closed{
  color:rgba(255,255,255,.76);
}

.citycard .status.closed .dot{
  background:rgba(255,255,255,.55);
}

/* ================================================================
   SHARED COMPONENTS
   ================================================================ */
main{
  max-width:1160px;
  margin:0 auto;
  padding:24px 22px 64px;
}

.panel{
  scroll-margin-top:100px;
}

.sec-head{
  display:flex;
  align-items:baseline;
  gap:14px;
  margin:22px 0 20px;
  flex-wrap:wrap;
}

.sec-head h2{
  font-family:var(--display);
  font-weight:700;
  font-size:25px;
  letter-spacing:-.025em;
}

.sec-head p{
  color:var(--muted);
  font-size:14px;
}

.card{
  background:var(--white);
  border:1px solid var(--line);
  border-radius:var(--radius);
  box-shadow:var(--shadow);
}

.field{
  margin-bottom:21px;
}

.field:last-child{
  margin-bottom:0;
}

.flabel{
  font-family:var(--display);
  font-weight:600;
  font-size:13px;
  letter-spacing:.01em;
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:9px;
}

.flabel .val{
  font-family:var(--mono);
  color:var(--lime-ink);
  font-weight:600;
}

.helper{
  margin-top:7px;
  font-size:11.5px;
  color:var(--muted);
}

input[type="range"]{
  width:100%;
  -webkit-appearance:none;
  appearance:none;
  height:4px;
  border-radius:4px;
  background:var(--line);
  outline:none;
  margin-top:4px;
}

input[type="range"]::-webkit-slider-thumb{
  -webkit-appearance:none;
  width:20px;
  height:20px;
  border-radius:50%;
  background:var(--lime);
  border:3px solid #fff;
  box-shadow:0 1px 5px rgba(10,19,11,.25);
  cursor:pointer;
}

input[type="range"]::-moz-range-thumb{
  width:20px;
  height:20px;
  border-radius:50%;
  background:var(--lime);
  border:3px solid #fff;
  box-shadow:0 1px 5px rgba(10,19,11,.25);
  cursor:pointer;
}

/* ================================================================
   COMPARADOR
   ================================================================ */
.grid{
  display:grid;
  grid-template-columns:350px 1fr;
  gap:22px;
  align-items:start;
}

.controls{
  padding:22px;
}

.seg{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:8px;
}

.seg button{
  font-family:var(--body);
  font-weight:500;
  font-size:13px;
  color:var(--ink-2);
  background:var(--panel);
  border:1px solid var(--line);
  border-radius:10px;
  padding:11px 10px;
  cursor:pointer;
  transition:.14s;
  text-align:left;
  line-height:1.25;
}

.seg button:hover{
  border-color:var(--line-strong);
}

.seg button[aria-pressed="true"]{
  background:var(--ink);
  color:#fff;
  border-color:var(--ink);
}

.presets{
  display:flex;
  gap:7px;
}

.presets button{
  flex:1;
  font-family:var(--mono);
  font-size:12px;
  color:var(--ink-2);
  background:var(--white);
  border:1px solid var(--line);
  border-radius:9px;
  padding:8px 6px;
  cursor:pointer;
  transition:.14s;
}

.presets button:hover{
  border-color:var(--lime);
  color:var(--lime-ink);
}

.presets button[aria-pressed="true"]{
  background:var(--lime-wash);
  border-color:var(--lime);
  color:var(--lime-ink);
  font-weight:600;
}

.chips{
  display:flex;
  flex-wrap:wrap;
  gap:7px;
}

.chip{
  appearance:none;
  font-size:12.5px;
  font-family:var(--body);
  color:var(--ink-2);
  background:var(--panel);
  border:1px solid var(--line);
  border-radius:20px;
  padding:7px 13px;
  cursor:pointer;
  transition:.14s;
  user-select:none;
}

.chip:hover{
  border-color:var(--line-strong);
}

.chip[aria-pressed="true"]{
  background:var(--lime-wash);
  border-color:var(--lime);
  color:var(--lime-ink);
  font-weight:600;
}

.chip.required{
  cursor:default;
  background:#EFF3EF;
  color:var(--muted);
}

.results{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:16px;
}

.mkt{
  padding:20px;
  position:relative;
  overflow:hidden;
  transition:
    transform .2s ease,
    box-shadow .2s ease;
}

.mkt:hover{
  transform:translateY(-2px);
  box-shadow:var(--shadow-hover);
}

.mkt::before{
  content:"";
  position:absolute;
  inset:0 auto 0 0;
  width:4px;
  background:var(--accent,var(--lime));
}

.mkt .mhead{
  display:flex;
  align-items:center;
  gap:9px;
  margin-bottom:4px;
}

.mkt .flag{
  font-size:20px;
}

.mkt .mcity{
  font-family:var(--display);
  font-weight:700;
  font-size:17px;
}

.mkt .mcountry{
  font-size:12px;
  color:var(--muted);
  margin-bottom:16px;
}

.mkt .range{
  font-family:var(--mono);
  font-weight:600;
  font-size:22px;
  font-variant-numeric:tabular-nums;
  line-height:1.15;
}

.mkt .range .to{
  color:var(--muted);
  font-weight:400;
  font-size:15px;
  margin:0 4px;
}

.mkt .note{
  font-size:11px;
  color:var(--muted);
  margin-top:7px;
  min-height:33px;
}

.mkt .relbar{
  margin-top:16px;
}

.mkt .relbar .track{
  height:7px;
  background:var(--panel);
  border-radius:6px;
  overflow:hidden;
}

.mkt .relbar .fill{
  height:100%;
  background:var(--accent,var(--lime));
  border-radius:6px;
  transition:width .45s cubic-bezier(.4,0,.2,1);
}

.mkt .relbar .cap{
  font-family:var(--mono);
  font-size:10.5px;
  color:var(--muted);
  margin-top:6px;
  display:flex;
  justify-content:space-between;
  gap:10px;
}

.disclaimer{
  grid-column:1/-1;
  font-size:12px;
  color:var(--muted);
  font-family:var(--mono);
  padding:14px 18px;
  background:var(--panel);
  border-radius:11px;
  border:1px dashed var(--line-strong);
  margin-top:2px;
  line-height:1.6;
}

.disclaimer b{
  color:var(--ink-2);
}

/* ================================================================
   SIMULADOR
   ================================================================ */
.sim-layout{
  display:grid;
  grid-template-columns:1fr 390px;
  gap:22px;
  align-items:start;
}

.sim-modules{
  display:flex;
  flex-direction:column;
  gap:18px;
}

.sim-module{
  padding:24px;
}

.sim-module .mod-head{
  display:flex;
  align-items:center;
  gap:10px;
  margin-bottom:6px;
}

.sim-module .mod-num{
  font-family:var(--mono);
  font-weight:600;
  font-size:11px;
  color:var(--lime-ink);
  background:var(--lime-wash);
  border:1px solid #CDEFCD;
  width:28px;
  height:28px;
  border-radius:8px;
  display:flex;
  align-items:center;
  justify-content:center;
  flex-shrink:0;
}

.sim-module h3{
  font-family:var(--display);
  font-weight:700;
  font-size:16px;
  letter-spacing:-.01em;
}

.sim-module .mod-sub{
  font-size:12.5px;
  color:var(--muted);
  margin-bottom:20px;
  padding-left:38px;
  max-width:78ch;
}

.sim-row{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:16px;
  margin-bottom:16px;
}

.sim-row.full{
  grid-template-columns:1fr;
}

.sim-row:last-child{
  margin-bottom:0;
}

.sim-input{
  display:flex;
  flex-direction:column;
  gap:5px;
}

.sim-input label{
  font-family:var(--display);
  font-weight:600;
  font-size:12.5px;
  color:var(--ink-2);
  display:flex;
  justify-content:space-between;
  align-items:baseline;
  gap:8px;
}

.sim-input label .unit{
  font-family:var(--mono);
  font-size:11px;
  color:var(--muted);
  font-weight:400;
  white-space:nowrap;
}

.sim-input input[type="number"]{
  font-family:var(--mono);
  font-size:15px;
  font-weight:500;
  color:var(--ink);
  border:1px solid var(--line);
  border-radius:10px;
  padding:10px 14px;
  outline:none;
  width:100%;
  background:var(--white);
  transition:.16s;
}

.sim-input input[type="number"]:focus{
  border-color:var(--lime);
  box-shadow:0 0 0 3px var(--lime-wash);
}

.sim-slider{
  display:flex;
  flex-direction:column;
  gap:5px;
}

.sim-slider .slider-head{
  display:flex;
  justify-content:space-between;
  align-items:baseline;
  gap:10px;
}

.sim-slider .slider-head label{
  font-family:var(--display);
  font-weight:600;
  font-size:12.5px;
  color:var(--ink-2);
}

.sim-slider .slider-head .readout{
  font-family:var(--mono);
  font-weight:600;
  font-size:14px;
  color:var(--lime-ink);
  white-space:nowrap;
}

.sim-slider .split-bar{
  display:flex;
  height:10px;
  border-radius:6px;
  overflow:hidden;
  margin-top:4px;
}

.sim-slider .split-bar .seg-a{
  background:var(--ink);
  transition:width .2s;
}

.sim-slider .split-bar .seg-b{
  background:var(--lime);
  transition:width .2s;
}

.sim-slider .split-labels{
  display:flex;
  justify-content:space-between;
  margin-top:4px;
  gap:12px;
}

.sim-slider .split-labels span{
  font-family:var(--mono);
  font-size:11px;
  color:var(--muted);
}

.sim-computed{
  display:flex;
  align-items:center;
  gap:8px;
  padding:10px 14px;
  background:var(--panel);
  border-radius:10px;
  border:1px solid var(--line);
  margin-top:4px;
}

.sim-computed .ic{
  font-size:16px;
  flex-shrink:0;
}

.sim-computed .ct{
  font-size:12.5px;
  color:var(--ink-2);
  flex:1;
}

.sim-computed .cv{
  font-family:var(--mono);
  font-weight:600;
  font-size:14px;
  text-align:right;
}

.dash{
  position:sticky;
  top:82px;
  display:flex;
  flex-direction:column;
  gap:16px;
}

.dash-card{
  padding:22px;
}

.dash-card h3{
  font-family:var(--display);
  font-weight:700;
  font-size:15px;
  margin-bottom:16px;
  display:flex;
  align-items:center;
  gap:8px;
  flex-wrap:wrap;
}

.dash-card h3 .badge{
  font-family:var(--mono);
  font-size:10px;
  font-weight:600;
  padding:3px 8px;
  border-radius:6px;
  text-transform:uppercase;
  letter-spacing:.06em;
}

.badge.green{
  background:var(--lime-wash);
  color:var(--lime-ink);
  border:1px solid #CDEFCD;
}

.badge.amber{
  background:var(--amber-wash);
  color:var(--amber);
  border:1px solid #F0E2B8;
}

.badge.red{
  background:var(--red-wash);
  color:var(--red);
  border:1px solid #F0C8C8;
}

.kpi-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  margin-bottom:14px;
}

.kpi{
  padding:12px;
  background:var(--panel);
  border-radius:10px;
  border:1px solid var(--line);
}

.kpi .kl{
  font-size:10.5px;
  color:var(--muted);
  font-family:var(--mono);
  margin-bottom:3px;
  text-transform:uppercase;
  letter-spacing:.05em;
}

.kpi .kv{
  font-family:var(--mono);
  font-weight:700;
  font-size:18px;
  font-variant-numeric:tabular-nums;
}

.kpi .kv.positive{
  color:var(--lime-ink);
}

.kpi .kv.negative{
  color:var(--red);
}

.waterfall{
  display:flex;
  flex-direction:column;
}

.wf-row{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:12px;
  padding:9px 0;
  border-bottom:1px solid var(--line);
  font-size:12.5px;
}

.wf-row:last-child{
  border-bottom:none;
}

.wf-row .wk{
  color:var(--ink-2);
  display:flex;
  align-items:center;
  gap:6px;
  min-width:0;
}

.wf-row .wk .dot{
  width:8px;
  height:8px;
  border-radius:3px;
  flex-shrink:0;
}

.wf-row .wv{
  font-family:var(--mono);
  font-weight:600;
  font-size:12.5px;
  font-variant-numeric:tabular-nums;
  white-space:nowrap;
}

.wf-row.total{
  border-top:2px solid var(--ink);
  padding-top:12px;
  margin-top:4px;
}

.wf-row.total .wk{
  font-weight:700;
  color:var(--ink);
}

.wf-row.total .wv{
  font-size:16px;
}

.split-vis{
  margin-top:5px;
}

.split-vis .sv-bar{
  display:flex;
  height:32px;
  border-radius:10px;
  overflow:hidden;
  margin-bottom:8px;
}

.split-vis .sv-bar .sv-a{
  background:var(--ink);
  display:flex;
  align-items:center;
  justify-content:center;
  color:#fff;
  font-family:var(--mono);
  font-size:12px;
  font-weight:600;
  transition:width .3s;
}

.split-vis .sv-bar .sv-b{
  background:var(--lime);
  display:flex;
  align-items:center;
  justify-content:center;
  color:var(--ink);
  font-family:var(--mono);
  font-size:12px;
  font-weight:600;
  transition:width .3s;
}

.split-vis .sv-legs{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
}

.split-vis .sv-leg{
  text-align:center;
}

.split-vis .sv-leg .sl-role{
  font-size:10.5px;
  color:var(--muted);
  font-family:var(--mono);
}

.split-vis .sv-leg .sl-val{
  font-family:var(--mono);
  font-weight:700;
  font-size:15px;
  margin-top:2px;
}

.ret-row{
  display:flex;
  justify-content:space-between;
  align-items:baseline;
  gap:12px;
  padding:8px 0;
  border-bottom:1px solid var(--line);
}

.ret-row:last-child{
  border-bottom:none;
}

.ret-row .rk{
  font-size:12px;
  color:var(--ink-2);
}

.ret-row .rv{
  font-family:var(--mono);
  font-weight:600;
  font-size:12.5px;
  white-space:nowrap;
}

.alert{
  padding:11px 13px;
  border-radius:10px;
  font-size:12px;
  margin-top:12px;
  line-height:1.5;
}

.alert.good{
  background:var(--lime-wash);
  border:1px solid #CDEFCD;
  color:var(--lime-ink);
}

.alert.warn{
  background:var(--amber-wash);
  border:1px solid #F0E2B8;
  color:#805A08;
}

.alert.bad{
  background:var(--red-wash);
  border:1px solid #F0C8C8;
  color:#9B2929;
}

/* ================================================================
   DATOS
   ================================================================ */
.stats{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:20px;
}

.stat{
  padding:22px;
}

.stat h3{
  font-family:var(--display);
  font-weight:600;
  font-size:15px;
  margin-bottom:3px;
}

.stat .sub{
  font-size:12px;
  color:var(--muted);
  font-family:var(--mono);
  margin-bottom:18px;
}

.barrow{
  display:flex;
  align-items:center;
  gap:12px;
  margin-bottom:13px;
}

.barrow .lbl{
  width:105px;
  flex-shrink:0;
  font-size:12.5px;
  display:flex;
  align-items:center;
  gap:6px;
}

.barrow .lbl .flag{
  font-size:14px;
}

.barrow .track{
  flex:1;
  height:26px;
  background:var(--panel);
  border-radius:7px;
  overflow:hidden;
}

.barrow .fill{
  height:100%;
  border-radius:7px;
  display:flex;
  align-items:center;
  justify-content:flex-end;
  padding-right:9px;
  color:#fff;
  font-family:var(--mono);
  font-size:12px;
  font-weight:600;
  min-width:38px;
  transition:width .6s cubic-bezier(.4,0,.2,1);
}

.fill.us{
  background:var(--ink);
}

.fill.sv{
  background:var(--lime-deep);
}

.fill.bo{
  background:var(--lime);
  color:var(--ink);
}

.fill.avg{
  background:#AAB7AC;
}

.datarow{
  display:flex;
  justify-content:space-between;
  gap:18px;
  padding:12px 0;
  border-bottom:1px solid var(--line);
  font-size:13.5px;
  align-items:center;
}

.datarow:last-child{
  border-bottom:none;
}

.datarow .k{
  color:var(--ink-2);
}

.datarow .v{
  font-family:var(--mono);
  font-weight:600;
  text-align:right;
}

.sketch{
  grid-column:1/-1;
  padding:24px;
}

.sketch h3{
  font-family:var(--display);
  font-weight:600;
  font-size:16px;
  margin-bottom:16px;
}

.sketch .cols{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:20px;
}

.sketch .col{
  padding-left:14px;
  border-left:3px solid var(--accent,var(--lime));
}

.sketch .col h4{
  font-family:var(--display);
  font-weight:600;
  font-size:14px;
  display:flex;
  align-items:center;
  gap:7px;
  margin-bottom:7px;
}

.sketch .col p{
  font-size:13px;
  color:var(--ink-2);
  line-height:1.58;
}

.data-note{
  grid-column:1/-1;
  padding:17px 20px;
  font-size:12px;
  color:var(--muted);
  line-height:1.65;
}

/* ================================================================
   GLOSARIO
   ================================================================ */
.glos-section{
  margin-bottom:24px;
  padding:24px;
}

.glos-section:last-child{
  margin-bottom:0;
}

.glos-section h3{
  font-family:var(--display);
  font-weight:700;
  font-size:18px;
  margin-bottom:18px;
  padding-bottom:12px;
  border-bottom:1px solid var(--line);
  color:var(--lime-ink);
}

.term-group{
  margin-bottom:18px;
}

.term-group:last-child{
  margin-bottom:0;
}

.term-title{
  font-family:var(--display);
  font-weight:600;
  font-size:15px;
  color:var(--ink);
  margin-bottom:4px;
  display:flex;
  align-items:center;
  gap:6px;
}

.term-def{
  font-size:14px;
  color:var(--ink-2);
  line-height:1.63;
}

/* ================================================================
   FOOTER
   ================================================================ */
footer{
  border-top:1px solid var(--line);
  background:var(--panel);
}

.foot{
  max-width:1160px;
  margin:0 auto;
  padding:22px;
  font-family:var(--mono);
  font-size:11.5px;
  color:var(--muted);
  line-height:1.75;
}

.foot b{
  color:var(--ink-2);
  font-weight:600;
}

/* ================================================================
   RESPONSIVE
   ================================================================ */
@media(max-width:980px){
  .sim-layout{
    grid-template-columns:1fr;
  }

  .dash{
    position:static;
  }
}

@media(max-width:880px){
  .grid{
    grid-template-columns:1fr;
  }

  .results,
  .wall,
  .sketch .cols{
    grid-template-columns:1fr;
  }

  .stats{
    grid-template-columns:1fr;
  }

  .sketch,
  .data-note{
    grid-column:auto;
  }

  .bar-clock{
    width:100%;
    order:3;
    margin-left:0;
  }

  .tabs{
    margin-left:auto;
    flex-wrap:wrap;
  }
}

@media(max-width:600px){
  .hero{
    padding-top:32px;
  }

  .bar{
    padding-inline:14px;
  }

  .hero,
  main{
    padding-left:16px;
    padding-right:16px;
  }

  .tabs{
    width:100%;
    order:4;
  }

  .tab{
    flex:1;
    padding-inline:7px;
  }

  .seg,
  .sim-row,
  .kpi-grid{
    grid-template-columns:1fr;
  }

  .presets{
    flex-direction:column;
  }

  .split-vis .sv-legs{
    grid-template-columns:1fr;
  }

  .citycard{
    min-height:300px;
  }
}

@media(prefers-reduced-motion:reduce){
  .beacon{
    animation:none;
  }

  *,
  *::before,
  *::after{
    scroll-behavior:auto !important;
    transition:none !important;
  }
}
</style>
</head>

<body>

<header>
  <div class="bar">
    <div class="wordmark">
      <span class="beacon" aria-hidden="true"></span>
      Comparador Web
      <small>3 mercados</small>
    </div>

    <div class="bar-clock" id="barClock" aria-label="Hora actual en La Paz">
      La Paz&nbsp;<b>--:--:--</b>
    </div>

    <div class="tabs" role="tablist" aria-label="Secciones">
      <button
        class="tab"
        id="tab-comparador"
        role="tab"
        aria-selected="true"
        aria-controls="comparador"
        tabindex="0"
        data-tab="comparador">
        Comparador
      </button>

      <button
        class="tab"
        id="tab-simulador"
        role="tab"
        aria-selected="false"
        aria-controls="simulador"
        tabindex="-1"
        data-tab="simulador">
        Simulador
      </button>

      <button
        class="tab"
        id="tab-datos"
        role="tab"
        aria-selected="false"
        aria-controls="datos"
        tabindex="-1"
        data-tab="datos">
        Datos
      </button>

      <button
        class="tab"
        id="tab-glosario"
        role="tab"
        aria-selected="false"
        aria-controls="glosario"
        tabindex="-1"
        data-tab="glosario">
        Glosario
      </button>
    </div>
  </div>
</header>

<section class="hero">
  <div class="eyebrow">Arbitraje geográfico · diseño &amp; desarrollo web</div>

  <h1>
    Tres mercados,<br>
    <em>un solo panel.</em>
  </h1>

  <p class="lede">
    Compara precios orientativos, modela la rentabilidad de captar clientes en
    Los Ángeles y ejecutar producción en La Paz, y analiza el efecto de costos,
    eficiencia, retainers y reparto de utilidades.
  </p>

  <div class="wall" id="wall" aria-label="Hora local de los tres mercados"></div>
</section>

<main>

  <!-- ============================================================
       COMPARADOR
       ============================================================ -->
  <section
    class="panel"
    id="comparador"
    role="tabpanel"
    aria-labelledby="tab-comparador">

    <div class="sec-head">
      <h2>Comparador de precios</h2>
      <p>Configura un proyecto y compara su posición relativa entre mercados.</p>
    </div>

    <div class="grid">

      <div class="card controls">

        <div class="field">
          <div class="flabel">Tipo de proyecto</div>
          <div class="seg" id="typeSeg"></div>
        </div>

        <div class="field">
          <div class="flabel">Perfil rápido</div>

          <div class="presets" id="presets">
            <button type="button" data-preset="basico" aria-pressed="false">
              Básico
            </button>

            <button type="button" data-preset="intermedio" aria-pressed="true">
              Intermedio
            </button>

            <button type="button" data-preset="avanzado" aria-pressed="false">
              Avanzado
            </button>
          </div>
        </div>

        <div class="field">
          <label class="flabel" for="pages">
            Nº de páginas
            <span class="val" id="pageVal">6</span>
          </label>

          <input
            type="range"
            id="pages"
            min="1"
            max="30"
            value="6"
            aria-describedby="pageHelp">

          <div class="helper" id="pageHelp">
            La complejidad se calcula respecto al tamaño típico de cada tipo de proyecto.
          </div>
        </div>

        <div class="field">
          <div class="flabel">Funciones e integraciones</div>
          <div class="chips" id="featChips"></div>
        </div>

      </div>

      <div class="results" id="results" aria-live="polite"></div>
    </div>
  </section>

  <!-- ============================================================
       SIMULADOR
       ============================================================ -->
  <section
    class="panel"
    id="simulador"
    role="tabpanel"
    aria-labelledby="tab-simulador"
    hidden>

    <div class="sec-head">
      <h2>Simulador de rentabilidad</h2>
      <p>Modelo económico configurable: venta en California, producción en Bolivia.</p>
    </div>

    <div class="sim-layout">

      <div class="sim-modules">

        <!-- 01 -->
        <div class="card sim-module">

          <div class="mod-head">
            <span class="mod-num">01</span>
            <h3>Venta y reparto societario</h3>
          </div>

          <p class="mod-sub">
            Define el precio del proyecto, las horas previstas antes de automatización
            y cómo se repartirá la utilidad neta entre captación comercial y ejecución.
          </p>

          <div class="sim-row">

            <div class="sim-input">
              <label for="salePrice">
                Precio de venta
                <span class="unit">USD</span>
              </label>

              <input
                type="number"
                id="salePrice"
                value="5000"
                min="0"
                step="100">
            </div>

            <div class="sim-input">
              <label for="baseHours">
                Horas presupuestadas
                <span class="unit">hrs</span>
              </label>

              <input
                type="number"
                id="baseHours"
                value="80"
                min="1"
                step="1">
            </div>

          </div>

          <div class="sim-row full">

            <div class="sim-slider">

              <div class="slider-head">
                <label for="splitSlider">Split de utilidad neta</label>
                <span class="readout" id="splitReadout">50 / 50</span>
              </div>

              <input
                type="range"
                id="splitSlider"
                min="10"
                max="90"
                value="50"
                step="5">

              <div class="split-bar" aria-hidden="true">
                <div class="seg-a" id="splitBarA" style="width:50%"></div>
                <div class="seg-b" id="splitBarB" style="width:50%"></div>
              </div>

              <div class="split-labels">
                <span>🇺🇸 Captación / ventas</span>
                <span>🇧🇴 Ejecución / producción</span>
              </div>

            </div>
          </div>

        </div>

        <!-- 02 -->
        <div class="card sim-module">

          <div class="mod-head">
            <span class="mod-num">02</span>
            <h3>Costos de producción</h3>
          </div>

          <p class="mod-sub">
            Separa costos globales del proyecto de la mano de obra variable.
            El costo laboral se calcula sobre las horas efectivas después de aplicar eficiencia.
          </p>

          <div class="sim-row">

            <div class="sim-input">
              <label for="infraCost">
                Infraestructura
                <span class="unit">USD/proyecto</span>
              </label>

              <input
                type="number"
                id="infraCost"
                value="120"
                min="0"
                step="10">
            </div>

            <div class="sim-input">
              <label for="lpRate">
                Costo interno de producción
                <span class="unit">USD/hr</span>
              </label>

              <input
                type="number"
                id="lpRate"
                value="10"
                min="0"
                step="1">
            </div>

          </div>

          <div class="sim-computed" id="compLabor">
            <span class="ic">🧑‍💻</span>
            <span class="ct">Mano de obra efectiva</span>
            <span class="cv">$560</span>
          </div>

          <div class="sim-computed" id="compTotal" style="margin-top:6px">
            <span class="ic">📦</span>
            <span class="ct">Costo total de producción</span>
            <span class="cv">$680</span>
          </div>

        </div>

        <!-- 03 -->
        <div class="card sim-module">

          <div class="mod-head">
            <span class="mod-num">03</span>
            <h3>Fricción comercial y de cobro</h3>
          </div>

          <p class="mod-sub">
            Modela comisiones por cobro, conversión, procesamiento, bancos y transferencias.
            No se presenta como una estimación fiscal: impuestos y obligaciones legales
            deben modelarse por separado según la estructura real del negocio.
          </p>

          <div class="sim-row">

            <div class="sim-input">
              <label for="frictionPct">
                Comisión variable
                <span class="unit">% venta</span>
              </label>

              <input
                type="number"
                id="frictionPct"
                value="4"
                min="0"
                max="30"
                step="0.25">
            </div>

            <div class="sim-input">
              <label for="frictionFlat">
                Comisión fija
                <span class="unit">USD</span>
              </label>

              <input
                type="number"
                id="frictionFlat"
                value="35"
                min="0"
                step="5">
            </div>

          </div>

          <div class="sim-computed" id="compFriction">
            <span class="ic">🏦</span>
            <span class="ct">Fricción total estimada</span>
            <span class="cv">$235</span>
          </div>

        </div>

        <!-- 04 -->
        <div class="card sim-module">

          <div class="mod-head">
            <span class="mod-num">04</span>
            <h3>Retainers · ingreso recurrente</h3>
          </div>

          <p class="mod-sub">
            Proyecta mantenimiento, hosting gestionado, soporte y cambios menores
            posteriores al lanzamiento.
          </p>

          <div class="sim-row">

            <div class="sim-input">
              <label for="retainerPrice">
                Retainer mensual
                <span class="unit">USD/cliente</span>
              </label>

              <input
                type="number"
                id="retainerPrice"
                value="350"
                min="0"
                step="25">
            </div>

            <div class="sim-input">
              <label for="retainerCost">
                Costo mensual
                <span class="unit">USD/cliente</span>
              </label>

              <input
                type="number"
                id="retainerCost"
                value="60"
                min="0"
                step="10">
            </div>

          </div>

          <div class="sim-row">

            <div class="sim-input">
              <label for="retainerMonths">
                Retención promedio
                <span class="unit">meses</span>
              </label>

              <input
                type="number"
                id="retainerMonths"
                value="12"
                min="1"
                max="60"
                step="1">
            </div>

            <div class="sim-input">
              <label for="retainerClients">
                Clientes activos
                <span class="unit">clientes</span>
              </label>

              <input
                type="number"
                id="retainerClients"
                value="3"
                min="1"
                max="100"
                step="1">
            </div>

          </div>

          <div class="sim-computed" id="compRetMargin">
            <span class="ic">💰</span>
            <span class="ct">Margen mensual por cliente</span>
            <span class="cv">$290/mes</span>
          </div>

          <div class="sim-computed" id="compRetLTV" style="margin-top:6px">
            <span class="ic">📈</span>
            <span class="ct">Contribución acumulada proyectada</span>
            <span class="cv">$10,440</span>
          </div>

        </div>

        <!-- 05 -->
        <div class="card sim-module">

          <div class="mod-head">
            <span class="mod-num">05</span>
            <h3>Eficiencia por IA y automatización</h3>
          </div>

          <p class="mod-sub">
            Reduce las horas internas requeridas sin cambiar automáticamente el precio
            cobrado. El modelo muestra cuánto costo laboral se evita.
          </p>

          <div class="sim-row full">

            <div class="sim-slider">

              <div class="slider-head">
                <label for="aiSlider">Reducción de horas</label>
                <span class="readout" id="aiReadout">30% reducción</span>
              </div>

              <input
                type="range"
                id="aiSlider"
                min="0"
                max="70"
                value="30"
                step="5">

            </div>
          </div>

          <div class="sim-computed" id="compAiHours">
            <span class="ic">⚡</span>
            <span class="ct">Horas efectivas</span>
            <span class="cv">56 hrs</span>
          </div>

          <div class="sim-computed" id="compAiSaved" style="margin-top:6px">
            <span class="ic">🎯</span>
            <span class="ct">Costo laboral evitado</span>
            <span class="cv">$240</span>
          </div>

        </div>

        <!-- 06 -->
        <div class="card sim-module">

          <div class="mod-head">
            <span class="mod-num">06</span>
            <h3>Referencia de mercado</h3>
          </div>

          <p class="mod-sub">
            La tarifa de referencia de Los Ángeles se usa solo como benchmark.
            No altera directamente la ganancia del proyecto.
          </p>

          <div class="sim-row">

            <div class="sim-input">
              <label for="laReferenceRate">
                Tarifa referencia LA
                <span class="unit">USD/hr</span>
              </label>

              <input
                type="number"
                id="laReferenceRate"
                value="55"
                min="1"
                step="1">
            </div>

            <div class="sim-input">
              <label for="salesHours">
                Horas comerciales LA
                <span class="unit">hrs/proyecto</span>
              </label>

              <input
                type="number"
                id="salesHours"
                value="10"
                min="0"
                step="1">
            </div>

          </div>

          <div class="sim-computed" id="compEconomicHours">
            <span class="ic">⏱️</span>
            <span class="ct">Horas totales del sistema</span>
            <span class="cv">66 hrs</span>
          </div>

        </div>

      </div>

      <!-- DASHBOARD -->
      <aside class="dash" id="dash">

        <div class="card dash-card">

          <h3>
            P&amp;L del proyecto
            <span class="badge green" id="marginBadge">viable</span>
          </h3>

          <div class="kpi-grid">

            <div class="kpi">
              <div class="kl">Margen neto</div>
              <div class="kv positive" id="kpiMarginPct">—</div>
            </div>

            <div class="kpi">
              <div class="kl">Utilidad neta</div>
              <div class="kv positive" id="kpiMarginAbs">—</div>
            </div>

            <div class="kpi">
              <div class="kl">Ingreso / hora total</div>
              <div class="kv" id="kpiEffRate">—</div>
            </div>

            <div class="kpi">
              <div class="kl">Vs tarifa ref. LA</div>
              <div class="kv" id="kpiMultiplier">—</div>
            </div>

          </div>

          <div class="waterfall" id="waterfall"></div>
          <div id="profitAlert"></div>
        </div>

        <div class="card dash-card">
          <h3>Split societario</h3>
          <div class="split-vis" id="splitVis"></div>
        </div>

        <div class="card dash-card">
          <h3>Recurrente mensual</h3>
          <div id="retainerDash"></div>
        </div>

      </aside>
    </div>
  </section>

  <!-- ============================================================
       DATOS
       ============================================================ -->
  <section
    class="panel"
    id="datos"
    role="tabpanel"
    aria-labelledby="tab-datos"
    hidden>

    <div class="sec-head">
      <h2>Datos y supuestos</h2>
      <p>Referencias internas utilizadas por el modelo; no equivalen a una cotización.</p>
    </div>

    <div class="stats">

      <div class="card stat">
        <h3>Tarifa por hora de referencia</h3>
        <div class="sub">benchmark configurable · USD/h</div>
        <div id="hourlyBars"></div>
      </div>

      <div class="card stat">
        <h3>Índice de costo del proyecto</h3>
        <div class="sub">sitio corporativo · Los Ángeles = 100</div>
        <div id="indexBars"></div>
      </div>

      <div class="card stat">
        <h3>Tiempo de entrega orientativo</h3>
        <div class="sub">del brief a la publicación</div>
        <div id="deliveryRows"></div>
      </div>

      <div class="card stat">
        <h3>Lectura de brecha de mercado</h3>
        <div class="sub">basada en los rangos cargados en el comparador</div>
        <div id="gapRows"></div>
      </div>

      <div class="card sketch">
        <h3>Interpretación por mercado</h3>
        <div class="cols" id="sketchCols"></div>
      </div>

      <div class="card data-note">
        <b>Importante:</b> los rangos del panel son parámetros de planeación.
        No deben interpretarse como tarifas oficiales ni como promedios estadísticos universales.
        En la práctica el precio depende de posicionamiento, nicho, portfolio, alcance, estrategia,
        complejidad técnica, soporte, copywriting, branding, adquisición del cliente, garantías,
        impuestos y estructura contractual.
      </div>

    </div>
  </section>

  <!-- ============================================================
       GLOSARIO
       ============================================================ -->
  <section
    class="panel"
    id="glosario"
    role="tabpanel"
    aria-labelledby="tab-glosario"
    hidden>

    <div class="sec-head">
      <h2>Glosario de términos</h2>
      <p>Conceptos utilizados en el comparador y el simulador financiero.</p>
    </div>

    <div class="card glos-section">

      <h3>Tipos de proyecto</h3>

      <div class="term-group">
        <div class="term-title">Landing / One-page</div>
        <div class="term-def">
          Sitio de una sola página orientado a una propuesta concreta, campaña, producto,
          servicio o captación de leads. Normalmente concentra propuesta de valor,
          prueba social, información comercial y llamada a la acción en un solo recorrido.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Sitio corporativo</div>
        <div class="term-def">
          Presencia institucional multipágina para una empresa establecida.
          Puede incluir inicio, empresa, servicios, equipo, casos, blog, contacto,
          formularios y gestión de contenido.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">E-commerce / Tienda</div>
        <div class="term-def">
          Sitio con funciones transaccionales: catálogo, productos, carrito, checkout,
          pagos, inventario, pedidos, notificaciones y potencialmente cuentas de clientes,
          impuestos, envíos e integraciones externas.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">App web a medida</div>
        <div class="term-def">
          Software web construido para una necesidad específica. Puede incorporar
          autenticación, roles, bases de datos, dashboards, lógica de negocio,
          automatización e integraciones mediante API.
        </div>
      </div>

    </div>

    <div class="card glos-section">

      <h3>Perfiles de complejidad</h3>

      <div class="term-group">
        <div class="term-title">Básico</div>
        <div class="term-def">
          Alcance reducido y cercano al mínimo funcional del tipo de proyecto.
          Utiliza pocas páginas y pocas integraciones.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Intermedio</div>
        <div class="term-def">
          Configuración representativa de un proyecto estándar: tamaño razonable,
          funciones habituales y personalización suficiente para una empresa profesional.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Avanzado</div>
        <div class="term-def">
          Mayor arquitectura de contenido y varias funcionalidades complejas,
          integraciones externas o requisitos especiales.
        </div>
      </div>

    </div>

    <div class="card glos-section">

      <h3>Funciones e integraciones</h3>

      <div class="term-group">
        <div class="term-title">CMS autoadministrable</div>
        <div class="term-def">
          Sistema que permite al cliente actualizar contenido sin modificar código.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">E-commerce / pagos</div>
        <div class="term-def">
          Infraestructura necesaria para catálogo, carrito, checkout y procesamiento
          de pagos.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Reservas / turnos</div>
        <div class="term-def">
          Sistema para programar citas, consultas, clases, servicios o disponibilidad.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Multilenguaje</div>
        <div class="term-def">
          Arquitectura para publicar y navegar el sitio en dos o más idiomas.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">SEO avanzado</div>
        <div class="term-def">
          Trabajo adicional sobre indexabilidad, contenido, arquitectura,
          rendimiento, metadatos, datos estructurados y estrategia de búsqueda.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Integraciones / API</div>
        <div class="term-def">
          Comunicación con CRM, ERP, automatización, facturación, mensajería,
          bases de datos, herramientas de marketing u otros servicios externos.
        </div>
      </div>

    </div>

    <div class="card glos-section">

      <h3>Modelo económico</h3>

      <div class="term-group">
        <div class="term-title">Arbitraje geográfico</div>
        <div class="term-def">
          Modelo que aprovecha diferencias entre el mercado donde se vende y el mercado
          donde se ejecuta el trabajo. La ventaja solo existe si la diferencia supera
          los costos adicionales de coordinación, ventas, control de calidad, cobro
          y operación internacional.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Split societario</div>
        <div class="term-def">
          Distribución de la utilidad neta del proyecto entre las partes.
          En este modelo el reparto ocurre después de restar producción y fricción.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Costo interno de producción</div>
        <div class="term-def">
          Valor económico asignado a una hora de trabajo de ejecución.
          Puede representar salario, honorarios, pago a contratistas o costo interno.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Fricción comercial y de cobro</div>
        <div class="term-def">
          Costos derivados de procesar pagos, mover fondos, convertir moneda,
          utilizar intermediarios financieros o gestionar operaciones transfronterizas.
          No sustituye un cálculo fiscal.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Retainer</div>
        <div class="term-def">
          Contrato recurrente por mantenimiento, soporte, optimización,
          hosting gestionado, analítica, cambios o servicios posteriores al lanzamiento.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Contribución acumulada</div>
        <div class="term-def">
          Margen estimado que los retainers generan durante el período de retención
          modelado. No representa necesariamente LTV financiero completo porque
          no incluye churn probabilístico, CAC, descuento temporal ni impuestos.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Eficiencia por IA</div>
        <div class="term-def">
          Reducción de horas internas atribuida a automatización, reutilización,
          asistentes de código, generación de contenido, plantillas o flujos de IA.
          Debe modelarse como una hipótesis operativa, no como un ahorro garantizado.
        </div>
      </div>

      <div class="term-group">
        <div class="term-title">Margen neto del proyecto</div>
        <div class="term-def">
          Precio de venta menos infraestructura, costo de producción y fricción.
          Este panel utiliza “neto” en sentido operativo interno y no como utilidad
          fiscal después de impuestos.
        </div>
      </div>

    </div>

  </section>

</main>

<footer>
  <div class="foot">
    <b>Modelo interno de planeación.</b>
    Todas las cifras monetarias están expresadas en USD.
    Los rangos son hipótesis editables y no cotizaciones, tarifas oficiales
    ni asesoría financiera, tributaria o legal.<br>
    <b>Bolivia:</b> cuando se requiera convertir a bolivianos, el tipo de cambio
    debe ingresarse o actualizarse según el canal de pago realmente utilizado;
    el modelo no presupone un único tipo de cambio como verdad universal.
  </div>
</footer>

<script>
'use strict';

/* ================================================================
   CONFIGURACIÓN
   ================================================================ */

const CITIES = [
  {
    id:'US',
    city:'Los Ángeles',
    country:'Estados Unidos',
    flag:'🇺🇸',
    tz:'America/Los_Angeles',
    biz:[9,18],
    accent:'#0A130B',
    photo:'cedric-letsch-UZVlSjrIJ3o-unsplash.jpg'
  },
  {
    id:'BO',
    city:'La Paz',
    country:'Bolivia',
    flag:'🇧🇴',
    tz:'America/La_Paz',
    biz:[9,18],
    accent:'#00DD00',
    photo:'snowscat-ahAHZzVEEjo-unsplash.jpg'
  },
  {
    id:'SV',
    city:'San Salvador',
    country:'El Salvador',
    flag:'🇸🇻',
    tz:'America/El_Salvador',
    biz:[8,17],
    accent:'#00A300',
    photo:'luis-rodriguez-WcwxSLIRxbM-unsplash.jpg'
  }
];

/*
  Los valores siguientes son SUPUESTOS EDITABLES del modelo.
  No se presentan como estadísticas oficiales.

  La lógica separa:
  - rango base del mercado;
  - tamaño típico;
  - tamaño máximo razonable antes de aproximarse al techo;
  - funciones obligatorias.
*/

const TYPES = {
  landing:{
    label:'Landing / One-page',
    standardPages:1,
    maxModelPages:4,
    required:[],
    base:{
      US:[1000,5000],
      BO:[100,700],
      SV:[250,1000]
    }
  },

  corporate:{
    label:'Sitio corporativo',
    standardPages:6,
    maxModelPages:18,
    required:['CMS autoadministrable'],
    base:{
      US:[4000,18000],
      BO:[300,1800],
      SV:[800,4000]
    }
  },

  ecommerce:{
    label:'E-commerce / Tienda',
    standardPages:8,
    maxModelPages:22,
    required:[
      'CMS autoadministrable',
      'E-commerce / pagos'
    ],
    base:{
      US:[6000,30000],
      BO:[600,3500],
      SV:[1500,8000]
    }
  },

  custom:{
    label:'App web / a medida',
    standardPages:10,
    maxModelPages:30,
    required:['Integraciones / API'],
    base:{
      US:[15000,60000],
      BO:[1800,10000],
      SV:[3500,15000]
    }
  }
};

const FEATURES = [
  'CMS autoadministrable',
  'E-commerce / pagos',
  'Reservas / turnos',
  'Multilenguaje',
  'SEO avanzado',
  'Integraciones / API'
];

/*
  Peso relativo por feature.
  Las integraciones/API y e-commerce afectan más la complejidad
  que CMS o SEO.
*/
const FEATURE_WEIGHTS = {
  'CMS autoadministrable':0.70,
  'E-commerce / pagos':1.35,
  'Reservas / turnos':0.90,
  'Multilenguaje':0.80,
  'SEO avanzado':0.75,
  'Integraciones / API':1.50
};

const MARKET_HOURLY_REFERENCE = {
  US:55,
  SV:17,
  BO:10,
  LATAM:16
};

let state = {
  type:'corporate',
  pages:6,
  feats:new Set([
    'CMS autoadministrable',
    'SEO avanzado'
  ]),
  preset:'intermedio'
};

/* ================================================================
   UTILIDADES
   ================================================================ */

const $ = id => document.getElementById(id);

const clamp = (value,min,max) =>
  Math.min(max,Math.max(min,value));

const pad = n =>
  String(n).padStart(2,'0');

const roundTo = (value,step) =>
  Math.round(value / step) * step;

function money(n){
  const absolute = Math.abs(Number(n) || 0);
  const step = absolute >= 10000 ? 100 : absolute >= 1000 ? 50 : 10;
  const rounded = roundTo(absolute,step);

  return '$' + rounded.toLocaleString('en-US');
}

function fmt(n){
  const num = Number(n) || 0;
  const sign = num < 0 ? '−' : '';
  return sign + '$' + Math.abs(Math.round(num)).toLocaleString('en-US');
}

function pct(n,digits=1){
  return `${Number(n || 0).toFixed(digits)}%`;
}

/* ================================================================
   TIMEZONE ENGINE
   Evita new Date(toLocaleString(...)), que puede producir errores
   y comportamientos inconsistentes entre Safari/Chrome.
   ================================================================ */

function timeParts(tz){
  try{
    const formatter = new Intl.DateTimeFormat('en-US',{
      timeZone:tz,
      weekday:'short',
      hour:'2-digit',
      minute:'2-digit',
      second:'2-digit',
      hourCycle:'h23'
    });

    const values = {};

    for(const part of formatter.formatToParts(new Date())){
      if(part.type !== 'literal'){
        values[part.type] = part.value;
      }
    }

    const h24 = Number(values.hour);
    const minute = Number(values.minute);
    const second = Number(values.second);

    return {
      h24,
      h:h24 % 12 || 12,
      m:minute,
      s:second,
      wd:values.weekday
    };

  }catch(error){
    const d = new Date();

    return {
      h24:d.getHours(),
      h:d.getHours() % 12 || 12,
      m:d.getMinutes(),
      s:d.getSeconds(),
      wd:['Sun','Mon','Tue','Wed','Thu','Fri','Sat'][d.getDay()]
    };
  }
}

function gmtOffsetMinutes(tz,date=new Date()){
  try{
    /*
      shortOffset produce, por ejemplo:
      GMT-7
      GMT-04:00
      GMT+5:30
    */
    const formatter = new Intl.DateTimeFormat('en-US',{
      timeZone:tz,
      timeZoneName:'shortOffset'
    });

    const tzName = formatter
      .formatToParts(date)
      .find(p => p.type === 'timeZoneName')
      ?.value;

    if(!tzName || tzName === 'GMT'){
      return 0;
    }

    const match = tzName.match(/GMT([+-])(\d{1,2})(?::(\d{2}))?/);

    if(!match){
      return 0;
    }

    const sign = match[1] === '+' ? 1 : -1;
    const hours = Number(match[2]);
    const minutes = Number(match[3] || 0);

    return sign * (hours * 60 + minutes);

  }catch(error){
    return 0;
  }
}

function formatOffset(minutes){
  const sign = minutes >= 0 ? '+' : '−';
  const absolute = Math.abs(minutes);
  const hours = Math.floor(absolute / 60);
  const mins = absolute % 60;

  return mins
    ? `GMT${sign}${hours}:${pad(mins)}`
    : `GMT${sign}${hours}`;
}

function formatRelativeOffset(minutes){
  if(minutes === 0){
    return 'misma hora que La Paz';
  }

  const sign = minutes > 0 ? '+' : '−';
  const absolute = Math.abs(minutes);
  const hours = Math.floor(absolute / 60);
  const mins = absolute % 60;

  if(mins){
    return `${sign}${hours}h ${mins}m vs La Paz`;
  }

  return `${sign}${hours}h vs La Paz`;
}

/* ================================================================
   CLOCK WALL
   ================================================================ */

function clockFace(){
  let ticks = '';

  for(let i=0;i<12;i++){
    const angle = i * 30;
    const major = i % 3 === 0;

    ticks += `
      <line
        x1="50"
        y1="${major ? 7 : 9}"
        x2="50"
        y2="${major ? 14 : 13}"
        transform="rotate(${angle} 50 50)"
        stroke="${major ? '#fff' : 'rgba(255,255,255,.5)'}"
        stroke-width="${major ? 2.4 : 1.4}"
        stroke-linecap="round"
      />
    `;
  }

  return `
    <svg viewBox="0 0 100 100" aria-hidden="true">
      <circle
        cx="50"
        cy="50"
        r="47"
        fill="rgba(255,255,255,.10)"
        stroke="rgba(255,255,255,.38)"
        stroke-width="1.4"
      />

      ${ticks}

      <line
        class="hh"
        x1="50"
        y1="52"
        x2="50"
        y2="28"
        stroke="#fff"
        stroke-width="3.4"
        stroke-linecap="round"
      />

      <line
        class="mh"
        x1="50"
        y1="53"
        x2="50"
        y2="18"
        stroke="#fff"
        stroke-width="2.4"
        stroke-linecap="round"
      />

      <line
        class="sh"
        x1="50"
        y1="57"
        x2="50"
        y2="14"
        stroke="#00DD00"
        stroke-width="1.5"
        stroke-linecap="round"
      />

      <circle
        cx="50"
        cy="50"
        r="3.2"
        fill="#00DD00"
        stroke="#fff"
        stroke-width="1.2"
      />
    </svg>
  `;
}

function buildWall(){
  const wall = $('wall');

  if(!wall){
    return;
  }

  const boOffset = gmtOffsetMinutes('America/La_Paz');

  wall.innerHTML = CITIES.map(city => {

    const offset = gmtOffsetMinutes(city.tz);
    const relative = offset - boOffset;

    const relativeText =
      city.id === 'BO'
        ? 'hora base'
        : formatRelativeOffset(relative);

    return `
      <article
        class="citycard"
        data-tz="${city.tz}"
        data-biz-open="${city.biz[0]}"
        data-biz-close="${city.biz[1]}"
        aria-label="${city.city}, ${city.country}"
      >
        <img
          src="${city.photo}"
          class="bg"
          alt=""
          loading="lazy"
        >

        <div class="tint"></div>
        <div class="grad"></div>

        <div class="content">

          ${clockFace()}

          <div class="city">${city.city}</div>

          <div class="country">
            ${city.flag} ${city.country}
          </div>

          <div class="digital">--:--:--</div>

          <div class="meta">
            <span>${formatOffset(offset)}</span>
            <span>·</span>
            <span>${relativeText}</span>
          </div>

          <div class="status closed">
            <span class="dot"></span>
            <span class="stxt">—</span>
          </div>

        </div>
      </article>
    `;
  }).join('');
}

function tick(){
  const laPaz = timeParts('America/La_Paz');

  const barClock = $('barClock')?.querySelector('b');

  if(barClock){
    barClock.textContent =
      `${pad(laPaz.h24)}:${pad(laPaz.m)}:${pad(laPaz.s)}`;
  }

  document.querySelectorAll('.citycard').forEach(card => {

    const parts = timeParts(card.dataset.tz);

    const secondAngle = parts.s * 6;
    const minuteAngle = parts.m * 6 + parts.s * 0.1;
    const hourAngle = (parts.h + parts.m / 60) * 30;

    card
      .querySelector('.sh')
      ?.setAttribute(
        'transform',
        `rotate(${secondAngle} 50 50)`
      );

    card
      .querySelector('.mh')
      ?.setAttribute(
        'transform',
        `rotate(${minuteAngle} 50 50)`
      );

    card
      .querySelector('.hh')
      ?.setAttribute(
        'transform',
        `rotate(${hourAngle} 50 50)`
      );

    const digital = card.querySelector('.digital');

    if(digital){
      digital.textContent =
        `${pad(parts.h24)}:${pad(parts.m)}:${pad(parts.s)}`;
    }

    const openHour = Number(card.dataset.bizOpen);
    const closeHour = Number(card.dataset.bizClose);

    const workday = !['Sat','Sun'].includes(parts.wd);

    const isOpen =
      workday &&
      parts.h24 >= openHour &&
      parts.h24 < closeHour;

    const status = card.querySelector('.status');
    const statusText = card.querySelector('.stxt');

    if(status){
      status.className =
        'status ' + (isOpen ? 'open' : 'closed');
    }

    if(statusText){
      statusText.textContent =
        isOpen
          ? 'Horario laboral'
          : workday
            ? 'Fuera de horario'
            : 'Fin de semana';
    }
  });
}

/* ================================================================
   COMPARADOR
   ================================================================ */

function currentType(){
  return TYPES[state.type];
}

function requiredFeatures(){
  return new Set(currentType().required);
}

function ensureRequiredFeatures(){
  for(const feature of currentType().required){
    state.feats.add(feature);
  }
}

function pageComplexity(){
  const type = currentType();

  /*
    0.00 = proyecto mínimo
    ~0.45 = tamaño estándar
    1.00 = tamaño grande para ese tipo
  */

  if(type.maxModelPages <= 1){
    return 0.35;
  }

  const raw =
    (state.pages - 1) /
    (type.maxModelPages - 1);

  return clamp(raw,0,1);
}

function featureComplexity(){
  const maxWeight =
    FEATURES.reduce(
      (sum,f) => sum + FEATURE_WEIGHTS[f],
      0
    );

  const selectedWeight =
    [...state.feats].reduce(
      (sum,f) => sum + (FEATURE_WEIGHTS[f] || 0),
      0
    );

  return clamp(
    selectedWeight / maxWeight,
    0,
    1
  );
}

function complexityScore(){
  /*
    Diseño del índice:
    - 10% base por gestión del proyecto.
    - 42% páginas/alcance.
    - 48% funcionalidades.

    Así una landing de 1 página sin features no empieza exactamente
    en cero, pero permanece cerca del piso del rango.
  */

  const score =
    0.10 +
    pageComplexity() * 0.42 +
    featureComplexity() * 0.48;

  return clamp(score,0,1);
}

function estimateMarketRange(marketId){
  const type = currentType();
  const [low,high] = type.base[marketId];

  const complexity = complexityScore();

  /*
    El "centro" se desplaza dentro del rango.

    Un proyecto de baja complejidad se aproxima al piso.
    Uno complejo se aproxima al techo.

    A su alrededor se genera una banda ±12%.
  */

  const center =
    low +
    complexity * (high - low);

  const min =
    clamp(
      center * 0.88,
      low,
      high
    );

  const max =
    clamp(
      center * 1.12,
      low,
      high
    );

  return [min,max];
}

function computeMarketComparison(){
  const us = estimateMarketRange('US');

  const usMid =
    (us[0] + us[1]) / 2 || 1;

  return CITIES.map(city => {

    const range =
      estimateMarketRange(city.id);

    const midpoint =
      (range[0] + range[1]) / 2;

    return {
      city,
      min:range[0],
      max:range[1],
      relative:
        midpoint / usMid * 100
    };
  });
}

function renderResults(){
  const results = $('results');

  if(!results){
    return;
  }

  const comparison =
    computeMarketComparison();

  results.innerHTML =
    comparison
      .map(result => {

        const city = result.city;

        let note = '';

        if(city.id === 'US'){
          note =
            'Mercado de venta premium; el alcance, posicionamiento y tipo de cliente pueden mover ampliamente el precio.';
        }

        if(city.id === 'BO'){
          note =
            'Rango interno de planeación para producción local; no presupone un tipo de cambio específico.';
        }

        if(city.id === 'SV'){
          note =
            'Mercado dolarizado utilizado aquí como referencia intermedia regional.';
        }

        const relative =
          Math.round(result.relative);

        return `
          <article
            class="card mkt"
            style="--accent:${city.accent}"
          >
            <div class="mhead">
              <span class="flag">${city.flag}</span>
              <span class="mcity">${city.city}</span>
            </div>

            <div class="mcountry">
              ${city.country}
            </div>

            <div class="range">
              ${money(result.min)}
              <span class="to">–</span>
              ${money(result.max)}
            </div>

            <div class="note">
              ${note}
            </div>

            <div class="relbar">

              <div class="track">
                <div
                  class="fill"
                  style="width:${Math.min(100,relative)}%">
                </div>
              </div>

              <div class="cap">
                <span>índice relativo a Los Ángeles</span>
                <span>${relative}%</span>
              </div>

            </div>

          </article>
        `;
      })
      .join('') +

    `
      <div class="disclaimer">
        Modelo actual:
        <b>${currentType().label}</b> ·
        ${state.pages} pág. ·
        ${state.feats.size} función${state.feats.size === 1 ? '' : 'es'} ·
        índice de complejidad
        <b>${Math.round(complexityScore() * 100)}/100</b>.
        Los valores son parámetros comparativos de planeación y no cotizaciones.
      </div>
    `;
}

function buildControls(){
  const typeSeg = $('typeSeg');

  if(typeSeg){
    typeSeg.innerHTML =
      Object.entries(TYPES)
        .map(([key,type]) => `
          <button
            type="button"
            data-type="${key}"
            aria-pressed="${state.type === key}"
          >
            ${type.label}
          </button>
        `)
        .join('');
  }

  syncFeatureControls();
  syncPages();
}

function syncFeatureControls(){
  const container = $('featChips');

  if(!container){
    return;
  }

  ensureRequiredFeatures();

  const required =
    requiredFeatures();

  container.innerHTML =
    FEATURES.map(feature => {

      const selected =
        state.feats.has(feature);

      const locked =
        required.has(feature);

      return `
        <button
          type="button"
          class="chip ${locked ? 'required' : ''}"
          data-feat="${feature}"
          aria-pressed="${selected}"
          ${locked ? 'aria-disabled="true"' : ''}
          title="${locked ? 'Requerido para este tipo de proyecto' : ''}"
        >
          ${feature}${locked ? ' · requerido' : ''}
        </button>
      `;
    }).join('');
}

function syncPages(){
  const pages = $('pages');
  const label = $('pageVal');

  const type =
    currentType();

  const max =
    Math.max(
      25,
      type.maxModelPages
    );

  if(pages){
    pages.max = String(max);
    pages.value = String(state.pages);
  }

  if(label){
    label.textContent =
      String(state.pages);
  }
}

function applyPreset(preset){
  const type =
    currentType();

  state.preset = preset;

  if(preset === 'basico'){

    state.pages =
      Math.max(
        1,
        Math.round(
          type.standardPages * 0.65
        )
      );

    state.feats =
      new Set(type.required);

    if(
      state.type === 'corporate' &&
      !state.feats.has('CMS autoadministrable')
    ){
      state.feats.add(
        'CMS autoadministrable'
      );
    }
  }

  if(preset === 'intermedio'){

    state.pages =
      type.standardPages;

    state.feats =
      new Set(type.required);

    if(
      state.type !== 'custom'
    ){
      state.feats.add(
        'CMS autoadministrable'
      );
    }

    if(
      state.type !== 'ecommerce'
    ){
      state.feats.add(
        'SEO avanzado'
      );
    }

    if(
      state.type === 'ecommerce'
    ){
      state.feats.add(
        'SEO avanzado'
      );
    }
  }

  if(preset === 'avanzado'){

    state.pages =
      Math.min(
        type.maxModelPages,
        Math.max(
          type.standardPages + 2,
          Math.round(
            type.standardPages * 1.7
          )
        )
      );

    state.feats =
      new Set([
        ...type.required,
        'CMS autoadministrable',
        'SEO avanzado',
        'Multilenguaje',
        'Integraciones / API'
      ]);

    if(state.type === 'ecommerce'){
      state.feats.add(
        'E-commerce / pagos'
      );
    }
  }

  ensureRequiredFeatures();
  refreshComparator();
}

function clearPreset(){
  state.preset = '';
}

function refreshComparator(){

  document
    .querySelectorAll('#typeSeg button')
    .forEach(button => {

      button.setAttribute(
        'aria-pressed',
        String(
          button.dataset.type ===
          state.type
        )
      );
    });

  document
    .querySelectorAll('#presets button')
    .forEach(button => {

      button.setAttribute(
        'aria-pressed',
        String(
          button.dataset.preset ===
          state.preset
        )
      );
    });

  syncPages();
  syncFeatureControls();
  renderResults();
}

/* ================================================================
   COMPARATOR EVENTS
   ================================================================ */

$('typeSeg')?.addEventListener(
  'click',
  event => {

    const button =
      event.target.closest('button');

    if(!button){
      return;
    }

    state.type =
      button.dataset.type;

    applyPreset(
      state.preset ||
      'intermedio'
    );
  }
);

$('presets')?.addEventListener(
  'click',
  event => {

    const button =
      event.target.closest('button');

    if(!button){
      return;
    }

    applyPreset(
      button.dataset.preset
    );
  }
);

$('pages')?.addEventListener(
  'input',
  event => {

    state.pages =
      Number(event.target.value);

    clearPreset();

    if($('pageVal')){
      $('pageVal').textContent =
        String(state.pages);
    }

    refreshComparator();
  }
);

$('featChips')?.addEventListener(
  'click',
  event => {

    const chip =
      event.target.closest('.chip');

    if(!chip){
      return;
    }

    const feature =
      chip.dataset.feat;

    if(
      requiredFeatures()
        .has(feature)
    ){
      return;
    }

    if(state.feats.has(feature)){
      state.feats.delete(feature);
    }else{
      state.feats.add(feature);
    }

    clearPreset();
    refreshComparator();
  }
);

/* ================================================================
   TABS
   ================================================================ */

const TAB_IDS = [
  'comparador',
  'simulador',
  'datos',
  'glosario'
];

function activateTab(tab){
  if(!tab){
    return;
  }

  const target =
    tab.dataset.tab;

  document
    .querySelectorAll('.tab')
    .forEach(button => {

      const selected =
        button === tab;

      button.setAttribute(
        'aria-selected',
        String(selected)
      );

      button.tabIndex =
        selected ? 0 : -1;
    });

  TAB_IDS.forEach(id => {

    const panel =
      $(id);

    if(panel){
      panel.hidden =
        id !== target;
    }
  });

  const wall =
    $('wall');

  if(wall){
    wall.style.display =
      target === 'comparador'
        ? 'grid'
        : 'none';
  }

  if(target === 'datos'){
    renderDatos();
  }

  if(target === 'simulador'){
    simCalc();
  }
}

document
  .querySelector('.tabs')
  ?.addEventListener(
    'click',
    event => {

      const tab =
        event.target.closest('.tab');

      activateTab(tab);
    }
  );

document
  .querySelector('.tabs')
  ?.addEventListener(
    'keydown',
    event => {

      if(
        ![
          'ArrowLeft',
          'ArrowRight',
          'Home',
          'End'
        ].includes(event.key)
      ){
        return;
      }

      event.preventDefault();

      const tabs =
        [...document.querySelectorAll('.tab')];

      const activeIndex =
        tabs.indexOf(document.activeElement);

      let nextIndex =
        activeIndex;

      if(event.key === 'ArrowRight'){
        nextIndex =
          (activeIndex + 1) %
          tabs.length;
      }

      if(event.key === 'ArrowLeft'){
        nextIndex =
          (activeIndex - 1 + tabs.length) %
          tabs.length;
      }

      if(event.key === 'Home'){
        nextIndex = 0;
      }

      if(event.key === 'End'){
        nextIndex =
          tabs.length - 1;
      }

      tabs[nextIndex].focus();
      activateTab(
        tabs[nextIndex]
      );
    }
  );

/* ================================================================
   DATOS
   ================================================================ */

let datosDone = false;

function bar(
  cls,
  label,
  flag,
  value,
  max,
  display
){
  const width =
    Math.max(
      6,
      value / max * 100
    );

  return `
    <div class="barrow">

      <div class="lbl">
        ${flag
          ? `<span class="flag">${flag}</span>`
          : ''
        }
        ${label}
      </div>

      <div class="track">
        <div
          class="fill ${cls}"
          style="width:0"
          data-w="${width}"
        >
          ${display}
        </div>
      </div>

    </div>
  `;
}

function renderDatos(){

  if(datosDone){
    animateBars();
    return;
  }

  datosDone = true;

  const hourly =
    $('hourlyBars');

  if(hourly){
    hourly.innerHTML =
      bar(
        'us',
        'Los Ángeles',
        '🇺🇸',
        MARKET_HOURLY_REFERENCE.US,
        MARKET_HOURLY_REFERENCE.US,
        `$${MARKET_HOURLY_REFERENCE.US}`
      ) +
      bar(
        'avg',
        'Prom. LatAm',
        '',
        MARKET_HOURLY_REFERENCE.LATAM,
        MARKET_HOURLY_REFERENCE.US,
        `$${MARKET_HOURLY_REFERENCE.LATAM}`
      ) +
      bar(
        'sv',
        'San Salvador',
        '🇸🇻',
        MARKET_HOURLY_REFERENCE.SV,
        MARKET_HOURLY_REFERENCE.US,
        `$${MARKET_HOURLY_REFERENCE.SV}`
      ) +
      bar(
        'bo',
        'La Paz',
        '🇧🇴',
        MARKET_HOURLY_REFERENCE.BO,
        MARKET_HOURLY_REFERENCE.US,
        `$${MARKET_HOURLY_REFERENCE.BO}`
      );
  }

  const midpoint = market => {
    const values =
      TYPES.corporate.base[market];

    return (
      values[0] +
      values[1]
    ) / 2;
  };

  const us =
    midpoint('US');

  const sv =
    Math.round(
      midpoint('SV') /
      us *
      100
    );

  const bo =
    Math.round(
      midpoint('BO') /
      us *
      100
    );

  const index =
    $('indexBars');

  if(index){
    index.innerHTML =
      bar(
        'us',
        'Los Ángeles',
        '🇺🇸',
        100,
        100,
        '100'
      ) +
      bar(
        'sv',
        'San Salvador',
        '🇸🇻',
        sv,
        100,
        String(sv)
      ) +
      bar(
        'bo',
        'La Paz',
        '🇧🇴',
        bo,
        100,
        String(bo)
      );
  }

  const delivery =
    $('deliveryRows');

  if(delivery){
    delivery.innerHTML =
      [
        [
          'Landing / One-page',
          '3–7 días'
        ],
        [
          'Sitio corporativo',
          '1–3 semanas'
        ],
        [
          'E-commerce / Tienda',
          '3–8 semanas'
        ],
        [
          'App web / a medida',
          '6 semanas +'
        ]
      ]
      .map(([key,value]) => `
        <div class="datarow">
          <span class="k">${key}</span>
          <span class="v">${value}</span>
        </div>
      `)
      .join('');
  }

  const gap =
    $('gapRows');

  if(gap){

    const svFactor =
      us / midpoint('SV');

    const boFactor =
      us / midpoint('BO');

    gap.innerHTML =
      [
        [
          'San Salvador',
          `≈ ${svFactor.toFixed(1)}× menor`
        ],
        [
          'La Paz',
          `≈ ${boFactor.toFixed(1)}× menor`
        ],
        [
          'Tarifa ref. San Salvador',
          `$${MARKET_HOURLY_REFERENCE.SV}/h`
        ],
        [
          'Tarifa ref. La Paz',
          `$${MARKET_HOURLY_REFERENCE.BO}/h`
        ]
      ]
      .map(([key,value]) => `
        <div class="datarow">
          <span class="k">${key}</span>
          <span class="v">${value}</span>
        </div>
      `)
      .join('');
  }

  const sketch =
    $('sketchCols');

  if(sketch){
    sketch.innerHTML =
      [
        {
          flag:'🇺🇸',
          color:'#0A130B',
          title:'Los Ángeles',
          text:
            'Mercado de venta de alto valor. La ventaja no depende únicamente del desarrollo técnico: estrategia, confianza, comunicación, especialización, ventas y capacidad de demostrar retorno pueden justificar precios muy superiores al costo de producción.'
        },

        {
          flag:'🇧🇴',
          color:'#00DD00',
          title:'La Paz',
          text:
            'Mercado de ejecución con costos laborales potencialmente menores. Para que el arbitraje funcione, la calidad, los procesos, la supervisión y los tiempos de respuesta deben mantenerse al nivel esperado por el cliente del mercado de venta.'
        },

        {
          flag:'🇸🇻',
          color:'#00A300',
          title:'San Salvador',
          text:
            'Referencia regional intermedia y dolarizada. Puede funcionar tanto como mercado de producción como de venta según el nicho, especialmente para pymes, comercio electrónico, mantenimiento y servicios digitales recurrentes.'
        }
      ]
      .map(item => `
        <div
          class="col"
          style="--accent:${item.color}"
        >
          <h4>
            <span>${item.flag}</span>
            ${item.title}
          </h4>

          <p>${item.text}</p>
        </div>
      `)
      .join('');
  }

  requestAnimationFrame(
    () =>
      requestAnimationFrame(
        animateBars
      )
  );
}

function animateBars(){
  document
    .querySelectorAll(
      '#datos .fill[data-w]'
    )
    .forEach(fill => {
      fill.style.width =
        `${fill.dataset.w}%`;
    });
}

/* ================================================================
   SIMULADOR
   ================================================================ */

function numericValue(id,fallback=0){
  const element =
    $(id);

  if(!element){
    return fallback;
  }

  const value =
    Number(element.value);

  return Number.isFinite(value)
    ? value
    : fallback;
}

function updateComputed(
  id,
  text
){
  const element =
    $(id)?.querySelector('.cv');

  if(element){
    element.textContent =
      text;
  }
}

function simCalc(){

  const salePrice =
    Math.max(
      0,
      numericValue(
        'salePrice',
        0
      )
    );

  const baseHours =
    Math.max(
      1,
      numericValue(
        'baseHours',
        1
      )
    );

  const infraCost =
    Math.max(
      0,
      numericValue(
        'infraCost',
        0
      )
    );

  const lpRate =
    Math.max(
      0,
      numericValue(
        'lpRate',
        0
      )
    );

  const frictionPct =
    clamp(
      numericValue(
        'frictionPct',
        0
      ),
      0,
      100
    );

  const frictionFlat =
    Math.max(
      0,
      numericValue(
        'frictionFlat',
        0
      )
    );

  const splitLA =
    clamp(
      numericValue(
        'splitSlider',
        50
      ),
      0,
      100
    );

  const splitLP =
    100 - splitLA;

  const aiReduction =
    clamp(
      numericValue(
        'aiSlider',
        0
      ),
      0,
      95
    );

  const retainerPrice =
    Math.max(
      0,
      numericValue(
        'retainerPrice',
        0
      )
    );

  const retainerCost =
    Math.max(
      0,
      numericValue(
        'retainerCost',
        0
      )
    );

  const retainerMonths =
    Math.max(
      1,
      numericValue(
        'retainerMonths',
        1
      )
    );

  const retainerClients =
    Math.max(
      1,
      numericValue(
        'retainerClients',
        1
      )
    );

  const laReferenceRate =
    Math.max(
      1,
      numericValue(
        'laReferenceRate',
        55
      )
    );

  const salesHours =
    Math.max(
      0,
      numericValue(
        'salesHours',
        0
      )
    );

  /*
    No redondeamos las horas internamente.
    El redondeo se hace solo para presentación.
  */
  const effectiveHours =
    Math.max(
      0.1,
      baseHours *
      (1 - aiReduction / 100)
    );

  const hoursSaved =
    Math.max(
      0,
      baseHours -
      effectiveHours
    );

  const productionLabor =
    effectiveHours *
    lpRate;

  const productionCost =
    infraCost +
    productionLabor;

  const aiSavings =
    hoursSaved *
    lpRate;

  const variableFriction =
    salePrice *
    frictionPct /
    100;

  const totalFriction =
    variableFriction +
    frictionFlat;

  const contributionBeforeFriction =
    salePrice -
    productionCost;

  const netProfit =
    contributionBeforeFriction -
    totalFriction;

  const marginPct =
    salePrice > 0
      ? netProfit /
        salePrice *
        100
      : 0;

  /*
    Incluimos las horas comerciales para evitar presentar el precio
    dividido solo entre horas de producción como si fuera productividad
    económica total del negocio.
  */
  const totalSystemHours =
    effectiveHours +
    salesHours;

  const revenuePerSystemHour =
    totalSystemHours > 0
      ? salePrice /
        totalSystemHours
      : 0;

  /*
    Benchmark:
    >1 significa que el ingreso bruto generado por hora total del sistema
    supera la tarifa horaria de referencia de LA.
  */
  const referenceMultiplier =
    laReferenceRate > 0
      ? revenuePerSystemHour /
        laReferenceRate
      : 0;

  /*
    Solo distribuimos utilidad positiva.
    Si hay pérdida, no mostramos "splits negativos" como pagos.
  */
  const distributableProfit =
    Math.max(
      0,
      netProfit
    );

  const splitLAAmount =
    distributableProfit *
    splitLA /
    100;

  const splitLPAmount =
    distributableProfit *
    splitLP /
    100;

  const retainerMargin =
    retainerPrice -
    retainerCost;

  const retainerRevenueMonthly =
    retainerPrice *
    retainerClients;

  const retainerCostMonthly =
    retainerCost *
    retainerClients;

  const retainerMarginMonthly =
    retainerMargin *
    retainerClients;

  const retainerContribution =
    retainerMarginMonthly *
    retainerMonths;

  /* ---------- UI readouts ---------- */

  if($('splitReadout')){
    $('splitReadout').textContent =
      `${splitLA} / ${splitLP}`;
  }

  if($('splitBarA')){
    $('splitBarA').style.width =
      `${splitLA}%`;
  }

  if($('splitBarB')){
    $('splitBarB').style.width =
      `${splitLP}%`;
  }

  if($('aiReadout')){
    $('aiReadout').textContent =
      `${aiReduction}% reducción`;
  }

  updateComputed(
    'compLabor',
    fmt(productionLabor)
  );

  updateComputed(
    'compTotal',
    fmt(productionCost)
  );

  updateComputed(
    'compFriction',
    fmt(totalFriction)
  );

  updateComputed(
    'compAiHours',
    `${effectiveHours.toFixed(1)} hrs`
  );

  updateComputed(
    'compAiSaved',
    fmt(aiSavings)
  );

  updateComputed(
    'compRetMargin',
    `${fmt(retainerMargin)}/mes`
  );

  updateComputed(
    'compRetLTV',
    fmt(retainerContribution)
  );

  updateComputed(
    'compEconomicHours',
    `${totalSystemHours.toFixed(1)} hrs`
  );

  /* ---------- KPIs ---------- */

  const marginClass =
    marginPct >= 35
      ? 'positive'
      : marginPct < 10
        ? 'negative'
        : '';

  if($('kpiMarginPct')){
    $('kpiMarginPct').textContent =
      pct(marginPct);

    $('kpiMarginPct').className =
      `kv ${marginClass}`;
  }

  if($('kpiMarginAbs')){
    $('kpiMarginAbs').textContent =
      fmt(netProfit);

    $('kpiMarginAbs').className =
      `kv ${
        netProfit >= 0
          ? 'positive'
          : 'negative'
      }`;
  }

  if($('kpiEffRate')){
    $('kpiEffRate').textContent =
      `${fmt(revenuePerSystemHour)}/h`;
  }

  if($('kpiMultiplier')){
    $('kpiMultiplier').textContent =
      `${referenceMultiplier.toFixed(2)}×`;
  }

  /* ---------- Badge ---------- */

  const badge =
    $('marginBadge');

  if(badge){

    if(marginPct >= 50){
      badge.textContent =
        'margen alto';

      badge.className =
        'badge green';
    }

    else if(marginPct >= 30){
      badge.textContent =
        'saludable';

      badge.className =
        'badge green';
    }

    else if(marginPct >= 15){
      badge.textContent =
        'moderado';

      badge.className =
        'badge amber';
    }

    else if(marginPct >= 0){
      badge.textContent =
        'ajustado';

      badge.className =
        'badge amber';
    }

    else{
      badge.textContent =
        'pérdida';

      badge.className =
        'badge red';
    }
  }

  /* ---------- Waterfall ---------- */

  const waterfall =
    $('waterfall');

  if(waterfall){

    const rows = [
      {
        label:'Ingreso por proyecto',
        value:fmt(salePrice),
        dot:'#0A130B'
      },

      {
        label:'Infraestructura',
        value:'−' + fmt(infraCost).replace('−',''),
        dot:'#77857A'
      },

      {
        label:
          `Producción (${effectiveHours.toFixed(1)}h × $${lpRate})`,
        value:'−' + fmt(productionLabor).replace('−',''),
        dot:'#00DD00'
      },

      {
        label:
          `Cobro/fricción (${frictionPct}% + $${frictionFlat})`,
        value:'−' + fmt(totalFriction).replace('−',''),
        dot:'#C98508'
      }
    ];

    waterfall.innerHTML =
      rows
        .map(row => `
          <div class="wf-row">

            <span class="wk">
              <span
                class="dot"
                style="background:${row.dot}">
              </span>
              ${row.label}
            </span>

            <span class="wv">
              ${row.value}
            </span>

          </div>
        `)
        .join('') +

      `
        <div class="wf-row total">

          <span class="wk">
            Utilidad operativa
          </span>

          <span
            class="wv"
            style="
              color:${
                netProfit >= 0
                  ? 'var(--lime-ink)'
                  : 'var(--red)'
              }
            ">
            ${fmt(netProfit)}
          </span>

        </div>
      `;
  }

  /* ---------- Profit alert ---------- */

  const profitAlert =
    $('profitAlert');

  if(profitAlert){

    let className =
      'good';

    let text =
      '';

    if(netProfit < 0){

      className =
        'bad';

      text =
        `El proyecto pierde ${fmt(Math.abs(netProfit))}. Debes subir el precio, reducir costos u horas, o disminuir fricción.`;
    }

    else if(marginPct < 15){

      className =
        'warn';

      text =
        `El proyecto es positivo, pero un margen de ${pct(marginPct)} deja poco espacio para revisiones, retrabajo, adquisición del cliente, impuestos u otros costos no modelados.`;
    }

    else if(marginPct < 30){

      className =
        'warn';

      text =
        `El margen es funcional, aunque todavía conviene reservar capacidad para costos comerciales, revisiones y contingencias no incluidas.`;
    }

    else{

      className =
        'good';

      text =
        `El modelo produce ${fmt(netProfit)} de utilidad operativa antes de impuestos y otros gastos empresariales no incluidos.`;
    }

    profitAlert.innerHTML =
      `<div class="alert ${className}">${text}</div>`;
  }

  /* ---------- Split ---------- */

  const splitVis =
    $('splitVis');

  if(splitVis){

    splitVis.innerHTML = `
      <div class="sv-bar">

        <div
          class="sv-a"
          style="width:${splitLA}%">
          ${splitLA}%
        </div>

        <div
          class="sv-b"
          style="width:${splitLP}%">
          ${splitLP}%
        </div>

      </div>

      <div class="sv-legs">

        <div class="sv-leg">
          <div class="sl-role">
            🇺🇸 Captación / ventas
          </div>

          <div class="sl-val">
            ${fmt(splitLAAmount)}
          </div>
        </div>

        <div class="sv-leg">
          <div class="sl-role">
            🇧🇴 Ejecución / producción
          </div>

          <div class="sl-val">
            ${fmt(splitLPAmount)}
          </div>
        </div>

      </div>

      ${
        netProfit < 0
          ? `
            <div class="alert bad">
              No se distribuye utilidad porque el proyecto está en pérdida.
            </div>
          `
          : ''
      }
    `;
  }

  /* ---------- Retainers ---------- */

  const retainerDash =
    $('retainerDash');

  if(retainerDash){

    const retainerRows = [
      {
        key:'Facturación mensual',
        value:fmt(retainerRevenueMonthly)
      },

      {
        key:'Costo mensual',
        value:fmt(retainerCostMonthly)
      },

      {
        key:'Contribución mensual',
        value:fmt(retainerMarginMonthly)
      },

      {
        key:
          `Contribución ${retainerMonths}m`,
        value:
          fmt(retainerContribution)
      }
    ];

    retainerDash.innerHTML =
      retainerRows
        .map(row => `
          <div class="ret-row">
            <span class="rk">
              ${row.key}
            </span>

            <span class="rv">
              ${row.value}
            </span>
          </div>
        `)
        .join('');
  }
}

/* ================================================================
   SIMULATOR EVENTS
   ================================================================ */

[
  'salePrice',
  'baseHours',
  'infraCost',
  'lpRate',
  'frictionPct',
  'frictionFlat',
  'splitSlider',
  'aiSlider',
  'retainerPrice',
  'retainerCost',
  'retainerMonths',
  'retainerClients',
  'laReferenceRate',
  'salesHours'
].forEach(id => {

  const element =
    $(id);

  if(element){
    element.addEventListener(
      'input',
      simCalc
    );
  }
});

/* ================================================================
   INIT
   ================================================================ */

buildWall();
buildControls();
renderResults();
simCalc();
tick();

setInterval(
  tick,
  1000
);
</script>

</body>
</html>