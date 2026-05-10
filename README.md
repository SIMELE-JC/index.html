<!DOCTYPE html>

<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simulateur d'importation – Europe → Guadeloupe</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–navy:    #0b1b2e;
–navy2:   #112440;
–navy3:   #183059;
–teal:    #0ec8c0;
–teal2:   #07a39c;
–gold:    #f5c842;
–coral:   #ff6b52;
–light:   #e8f4f8;
–muted:   #7a9ab5;
–border:  rgba(14,200,192,.18);
–card-bg: rgba(17,36,64,.75);
–mono:    ‘IBM Plex Mono’, monospace;
–sans:    ‘IBM Plex Sans’, sans-serif;
–serif:   ‘Playfair Display’, serif;
}

html { scroll-behavior: smooth; }

body {
font-family: var(–sans);
background: var(–navy);
color: var(–light);
min-height: 100vh;
overflow-x: hidden;
}

/* ─── Background ─────────────────────────────── */
body::before {
content: ‘’;
position: fixed; inset: 0;
background:
radial-gradient(ellipse 80% 60% at 15% 0%, rgba(14,200,192,.12) 0%, transparent 60%),
radial-gradient(ellipse 60% 50% at 90% 100%, rgba(245,200,66,.07) 0%, transparent 55%),
radial-gradient(ellipse 50% 80% at 50% 50%, rgba(11,27,46,1) 0%, transparent 100%);
pointer-events: none; z-index: 0;
}

/* grid lines */
body::after {
content: ‘’;
position: fixed; inset: 0;
background-image:
linear-gradient(rgba(14,200,192,.04) 1px, transparent 1px),
linear-gradient(90deg, rgba(14,200,192,.04) 1px, transparent 1px);
background-size: 48px 48px;
pointer-events: none; z-index: 0;
}

main { position: relative; z-index: 1; max-width: 860px; margin: 0 auto; padding: 48px 24px 80px; }

/* ─── Header ─────────────────────────────────── */
header { text-align: center; margin-bottom: 48px; }

.flag-badge {
display: inline-flex; align-items: center; gap: 10px;
background: var(–card-bg);
border: 1px solid var(–border);
border-radius: 40px;
padding: 6px 18px 6px 10px;
font-family: var(–mono); font-size: .75rem;
color: var(–teal); letter-spacing: .12em;
margin-bottom: 20px;
backdrop-filter: blur(8px);
}

.flag-badge span { font-size: 1.2rem; }

h1 {
font-family: var(–serif); font-size: clamp(1.8rem, 5vw, 2.8rem);
font-weight: 700; line-height: 1.15;
color: #fff;
}

h1 em {
font-style: normal;
background: linear-gradient(135deg, var(–teal), var(–gold));
-webkit-background-clip: text; -webkit-text-fill-color: transparent;
background-clip: text;
}

.subtitle {
margin-top: 12px; color: var(–muted);
font-size: .9rem; letter-spacing: .03em;
}

/* ─── Cards ──────────────────────────────────── */
.card {
background: var(–card-bg);
border: 1px solid var(–border);
border-radius: 16px;
padding: 28px 32px;
backdrop-filter: blur(12px);
margin-bottom: 20px;
position: relative;
overflow: hidden;
transition: border-color .25s;
}
.card:hover { border-color: rgba(14,200,192,.35); }
.card::before {
content: ‘’;
position: absolute; top: 0; left: 0; right: 0; height: 2px;
background: linear-gradient(90deg, transparent, var(–teal), transparent);
opacity: .6;
}

.section-label {
font-family: var(–mono); font-size: .7rem;
letter-spacing: .18em; color: var(–teal);
text-transform: uppercase; margin-bottom: 20px;
display: flex; align-items: center; gap: 10px;
}
.section-label::after {
content: ‘’; flex: 1; height: 1px;
background: linear-gradient(90deg, var(–border), transparent);
}

/* ─── Form ───────────────────────────────────── */
.grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.grid-3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; }

@media (max-width: 560px) {
.grid-2, .grid-3 { grid-template-columns: 1fr; }
.card { padding: 20px; }
}

.field { display: flex; flex-direction: column; gap: 6px; }

label {
font-size: .78rem; letter-spacing: .05em; color: var(–muted);
font-weight: 500;
}

.input-wrap { position: relative; }

.input-wrap .currency {
position: absolute; left: 14px; top: 50%; transform: translateY(-50%);
font-family: var(–mono); color: var(–teal); font-size: .9rem; pointer-events: none;
}

.input-wrap .pct {
position: absolute; right: 14px; top: 50%; transform: translateY(-50%);
font-family: var(–mono); color: var(–muted); font-size: .85rem; pointer-events: none;
}

input[type=number], input[type=text], select {
width: 100%;
background: rgba(11,27,46,.8);
border: 1px solid rgba(14,200,192,.2);
border-radius: 10px;
padding: 11px 14px 11px 36px;
color: #fff;
font-family: var(–mono); font-size: .9rem;
outline: none;
transition: border-color .2s, box-shadow .2s;
-moz-appearance: textfield;
}

input.no-prefix { padding-left: 14px; }
input[type=number]::-webkit-inner-spin-button { -webkit-appearance: none; }

input:focus, select:focus {
border-color: var(–teal);
box-shadow: 0 0 0 3px rgba(14,200,192,.12);
}

input::placeholder { color: rgba(122,154,181,.5); }

/* Argus row */
.argus-row {
display: flex; align-items: flex-end; gap: 10px;
}
.argus-row .field { flex: 1; }

.btn-argus {
display: inline-flex; align-items: center; gap: 7px;
background: rgba(14,200,192,.1);
border: 1px solid rgba(14,200,192,.3);
border-radius: 10px;
padding: 10px 16px;
color: var(–teal); font-size: .78rem; font-family: var(–mono);
text-decoration: none; white-space: nowrap;
transition: all .2s; cursor: pointer;
letter-spacing: .06em;
}
.btn-argus:hover {
background: rgba(14,200,192,.2);
border-color: var(–teal);
transform: translateY(-1px);
}

.note {
font-size: .73rem; color: var(–muted); margin-top: 4px;
line-height: 1.5;
}
.note a { color: var(–teal); text-decoration: none; }
.note a:hover { text-decoration: underline; }

/* ─── Toggle ──────────────────────────────────── */
.toggle-row {
display: flex; align-items: center; gap: 12px;
font-size: .82rem; color: var(–muted); cursor: pointer;
user-select: none; margin-top: 4px;
}
.toggle {
position: relative; width: 40px; height: 22px;
background: rgba(14,200,192,.15); border-radius: 11px;
border: 1px solid var(–border); transition: background .2s;
flex-shrink: 0;
}
.toggle.active { background: rgba(14,200,192,.35); border-color: var(–teal); }
.toggle::after {
content: ‘’; position: absolute;
top: 3px; left: 3px; width: 14px; height: 14px;
background: var(–muted); border-radius: 50%;
transition: transform .2s, background .2s;
}
.toggle.active::after { transform: translateX(18px); background: var(–teal); }

/* ─── CTA Button ──────────────────────────────── */
.btn-calc {
display: block; width: 100%;
background: linear-gradient(135deg, var(–teal2), var(–teal));
border: none; border-radius: 12px;
padding: 16px; color: var(–navy);
font-family: var(–mono); font-size: 1rem; font-weight: 600;
letter-spacing: .08em; cursor: pointer;
transition: all .25s;
box-shadow: 0 4px 24px rgba(14,200,192,.25);
}
.btn-calc:hover {
transform: translateY(-2px);
box-shadow: 0 8px 32px rgba(14,200,192,.4);
}
.btn-calc:active { transform: translateY(0); }

/* ─── Results ─────────────────────────────────── */
#results { display: none; animation: fadeUp .4s ease both; }

@keyframes fadeUp {
from { opacity: 0; transform: translateY(16px); }
to   { opacity: 1; transform: translateY(0); }
}

.result-table { width: 100%; border-collapse: collapse; }

.result-table tr { border-bottom: 1px solid rgba(14,200,192,.08); }
.result-table tr:last-child { border-bottom: none; }

.result-table td {
padding: 10px 4px;
font-family: var(–mono); font-size: .85rem;
}

.result-table td:first-child { color: var(–muted); flex: 1; }
.result-table td:last-child { text-align: right; color: #fff; font-weight: 500; }

.result-table .sub { padding-left: 20px; }
.result-table .sub td:first-child { font-size: .78rem; }

.result-table tr.divider td {
padding-top: 16px; padding-bottom: 4px;
font-size: .7rem; letter-spacing: .14em; color: var(–teal);
text-transform: uppercase;
}

.result-table tr.highlight td {
padding-top: 14px; padding-bottom: 14px;
font-size: 1.05rem; font-weight: 600;
}
.result-table tr.highlight td:last-child {
color: var(–teal);
font-size: 1.15rem;
}

.result-table tr.grand-total td {
padding-top: 18px; border-top: 1px solid var(–border);
}
.result-table tr.grand-total td:first-child { font-size: .9rem; color: var(–light); }
.result-table tr.grand-total td:last-child {
color: var(–gold);
font-size: 1.35rem; font-weight: 700;
}

.disclaimer {
margin-top: 16px;
background: rgba(245,200,66,.06);
border: 1px solid rgba(245,200,66,.2);
border-radius: 10px; padding: 14px 16px;
font-size: .75rem; color: rgba(245,200,66,.8);
line-height: 1.6;
}
.disclaimer strong { color: var(–gold); }

/* ─── Footer ─────────────────────────────────── */
footer {
text-align: center; margin-top: 48px;
font-size: .72rem; color: rgba(122,154,181,.5);
font-family: var(–mono);
}
</style>

</head>
<body>
<main>

  <header>
    <div class="flag-badge">
      <span>🇪🇺</span> EUROPE → <span>🇬🇵</span> GUADELOUPE
    </div>
    <h1>Simulateur d'<em>importation</em><br>de véhicule</h1>
    <p class="subtitle">Estimez vos frais de douane · Octroi de mer · TVA · Dédouanement</p>
  </header>

  <!-- VALEUR DU VÉHICULE -->

  <div class="card">
    <div class="section-label">01 — Valeur du véhicule</div>

```
<div class="argus-row">
  <div class="field">
    <label>Valeur Argus / Déclarée (€)</label>
    <div class="input-wrap">
      <span class="currency">€</span>
      <input type="number" id="argus" placeholder="Ex : 12 500" min="0" step="100">
    </div>
    <p class="note">
      Pour un véhicule d'occasion, la douane se base sur la <strong>cote Argus</strong>.
      Consultez la valeur sur
      <a href="https://www.largus.fr/cote-voiture/" target="_blank" rel="noopener">L'Argus</a>
      ou <a href="https://www.lacentrale.fr/cote-voiture.php" target="_blank" rel="noopener">La Centrale</a>.
    </p>
  </div>
  <a class="btn-argus" href="https://www.largus.fr/cote-voiture/" target="_blank" rel="noopener">
    ↗ Cote Argus
  </a>
</div>
```

  </div>

  <!-- FRAIS DE TRANSPORT -->

  <div class="card">
    <div class="section-label">02 — Frais de transport &amp; assurance</div>

```
<div class="grid-2">
  <div class="field">
    <label>Frais d'envoi / Fret maritime (€)</label>
    <div class="input-wrap">
      <span class="currency">€</span>
      <input type="number" id="fret" placeholder="Ex : 1 800" min="0" step="50">
    </div>
  </div>
  <div class="field">
    <label>Assurance transport (€)</label>
    <div class="input-wrap">
      <span class="currency">€</span>
      <input type="number" id="assurance" placeholder="Optionnel" min="0" step="10">
    </div>
  </div>
</div>
<p class="note" style="margin-top:12px">
  Ces frais sont intégrés à la <strong>valeur CIF</strong> (Cost, Insurance &amp; Freight) — base de calcul des taxes douanières.
</p>
```

  </div>

  <!-- TAUX & OPTIONS -->

  <div class="card">
    <div class="section-label">03 — Taux &amp; paramètres fiscaux</div>

```
<div class="grid-3">
  <div class="field">
    <label>Octroi de mer (%)</label>
    <div class="input-wrap">
      <input type="number" id="octroi" class="no-prefix" value="12" min="0" max="100" step="0.5">
      <span class="pct">%</span>
    </div>
    <p class="note">Taux variable selon catégorie. Défaut : 12 %</p>
  </div>
  <div class="field">
    <label>TVA Guadeloupe (%)</label>
    <div class="input-wrap">
      <input type="number" id="tva" class="no-prefix" value="8.5" min="0" max="30" step="0.5">
      <span class="pct">%</span>
    </div>
    <p class="note">Taux réduit applicable en Guadeloupe</p>
  </div>
  <div class="field">
    <label>Frais de dédouanement (€)</label>
    <div class="input-wrap">
      <span class="currency">€</span>
      <input type="number" id="dedouanement" placeholder="Ex : 250" value="250" min="0" step="10">
    </div>
    <p class="note">Honoraires du commissionnaire en douane</p>
  </div>
</div>

<div style="margin-top:20px; display:flex; gap:32px; flex-wrap:wrap;">
  <label class="toggle-row" onclick="toggleOption('toggle-carte-grise')">
    <div class="toggle" id="toggle-carte-grise"></div>
    Inclure frais de carte grise estimatifs
  </label>
  <label class="toggle-row" onclick="toggleOption('toggle-malus')">
    <div class="toggle" id="toggle-malus"></div>
    Inclure malus CO₂ (si applicable)
  </label>
</div>

<!-- Carte grise -->
<div id="block-carte-grise" style="display:none; margin-top:16px;">
  <div class="grid-2">
    <div class="field">
      <label>Nombre de CV fiscaux</label>
      <div class="input-wrap">
        <input type="number" id="cv" class="no-prefix" placeholder="Ex : 6" min="1" max="50" step="1">
      </div>
    </div>
    <div class="field">
      <label>Tarif par cheval fiscal (€)</label>
      <div class="input-wrap">
        <span class="currency">€</span>
        <input type="number" id="tarif-cv" value="43" min="0" step="1">
      </div>
      <p class="note">Tarif régional moyen — vérifiez sur service-public.fr</p>
    </div>
  </div>
</div>

<!-- Malus -->
<div id="block-malus" style="display:none; margin-top:16px;">
  <div class="field" style="max-width:260px">
    <label>Montant malus CO₂ estimé (€)</label>
    <div class="input-wrap">
      <span class="currency">€</span>
      <input type="number" id="malus" placeholder="Ex : 900" min="0" step="50">
    </div>
    <p class="note">
      Simulez votre malus sur
      <a href="https://www.service-public.fr/particuliers/vosdroits/F10‐malus" target="_blank" rel="noopener">service-public.fr</a>
    </p>
  </div>
</div>
```

  </div>

  <!-- BOUTON CALCULER -->

  <button class="btn-calc" onclick="calculer()">
    ▶ &nbsp;CALCULER LES FRAIS D'IMPORTATION
  </button>

  <!-- RÉSULTATS -->

  <div id="results">
    <div class="card" style="margin-top:20px;">
      <div class="section-label">Détail du calcul</div>

```
  <table class="result-table">
    <tbody id="detail-table"></tbody>
  </table>

  <div class="disclaimer">
    <strong>⚠ Estimation indicative uniquement.</strong>
    Ce simulateur ne remplace pas les renseignements officiels de la direction des douanes de Guadeloupe
    (<a href="https://www.douane.gouv.fr" target="_blank" style="color:var(--gold)">douane.gouv.fr</a>).
    Les taux d'octroi de mer varient selon le code NC du véhicule, son âge et sa cylindrée.
    Consultez un commissionnaire agréé pour un calcul définitif.
  </div>
</div>
```

  </div>

</main>

<footer>
  Simulateur indicatif · Données fiscales 2024–2025 · Aucune garantie de conformité douanière
</footer>

<script>
  const toggleStates = {};

  function toggleOption(id) {
    toggleStates[id] = !toggleStates[id];
    const toggle = document.getElementById(id);
    toggle.classList.toggle('active', toggleStates[id]);
    const block = document.getElementById('block-' + id.replace('toggle-', ''));
    if (block) block.style.display = toggleStates[id] ? 'block' : 'none';
  }

  function fmt(val) {
    return val.toLocaleString('fr-FR', { minimumFractionDigits: 2, maximumFractionDigits: 2 }) + ' €';
  }

  function row(label, value, cls = '') {
    return `<tr class="${cls}"><td>${label}</td><td>${fmt(value)}</td></tr>`;
  }

  function divider(label) {
    return `<tr class="divider"><td colspan="2">${label}</td></tr>`;
  }

  function calculer() {
    const argus        = parseFloat(document.getElementById('argus').value)        || 0;
    const fret         = parseFloat(document.getElementById('fret').value)         || 0;
    const assurance    = parseFloat(document.getElementById('assurance').value)    || 0;
    const tauxOctroi   = parseFloat(document.getElementById('octroi').value)       / 100 || 0.12;
    const tauxTVA      = parseFloat(document.getElementById('tva').value)          / 100 || 0.085;
    const dedouanement = parseFloat(document.getElementById('dedouanement').value) || 0;

    if (argus === 0) {
      document.getElementById('argus').focus();
      document.getElementById('argus').style.borderColor = 'var(--coral)';
      setTimeout(() => document.getElementById('argus').style.borderColor = '', 2000);
      return;
    }

    // ── Base CIF ──────────────────────────────────────────────────
    const baseCIF = argus + fret + assurance;

    // ── Octroi de mer ─────────────────────────────────────────────
    const montantOctroi = baseCIF * tauxOctroi;

    // ── Base TVA = CIF + octroi de mer ───────────────────────────
    const baseTVA = baseCIF + montantOctroi;

    // ── TVA ───────────────────────────────────────────────────────
    const montantTVA = baseTVA * tauxTVA;

    // ── Carte grise ───────────────────────────────────────────────
    let carteGrise = 0;
    const withCG = toggleStates['toggle-carte-grise'];
    if (withCG) {
      const cv     = parseFloat(document.getElementById('cv').value)      || 0;
      const tarifCV = parseFloat(document.getElementById('tarif-cv').value) || 43;
      carteGrise = cv * tarifCV;
    }

    // ── Malus CO₂ ─────────────────────────────────────────────────
    let malus = 0;
    const withMalus = toggleStates['toggle-malus'];
    if (withMalus) malus = parseFloat(document.getElementById('malus').value) || 0;

    // ── Totaux ────────────────────────────────────────────────────
    const totalFraisFiscaux = montantOctroi + montantTVA;
    const totalFraisFixes   = dedouanement + carteGrise + malus;
    const coutTotal         = baseCIF + totalFraisFiscaux + totalFraisFixes;

    // ── Rendu HTML ────────────────────────────────────────────────
    let html = '';

    html += divider('① Base taxable — Valeur CIF');
    html += row('Valeur Argus / déclarée du véhicule', argus);
    html += row('Frais de fret maritime', fret, 'sub');
    html += row('Assurance transport', assurance, 'sub');
    html += row('Base CIF (valeur douanière)', baseCIF, 'highlight');

    html += divider('② Octroi de mer');
    html += row(`Octroi de mer (${(tauxOctroi * 100).toFixed(1)} % × base CIF)`, montantOctroi, 'highlight');

    html += divider('③ TVA Guadeloupe');
    html += row(`Base TVA (CIF + octroi de mer)`, baseTVA, 'sub');
    html += row(`TVA (${(tauxTVA * 100).toFixed(1)} % × base TVA)`, montantTVA, 'highlight');

    html += divider('④ Frais fixes');
    html += row('Dédouanement (commissionnaire en douane)', dedouanement);
    if (withCG)    html += row('Carte grise (immatriculation)', carteGrise);
    if (withMalus) html += row('Malus CO₂ (estimé)', malus);

    html += `<tr class="grand-total">
      <td>💰 COÛT TOTAL ESTIMÉ (véhicule inclus)</td>
      <td>${fmt(coutTotal)}</td>
    </tr>`;

    // Récap frais seuls
    html += `<tr style="border-top: none;">
      <td style="font-size:.78rem; color:var(--muted); padding-top:6px; font-family:var(--mono)">
        dont frais d'importation uniquement
      </td>
      <td style="text-align:right; font-size:.78rem; color:var(--muted); font-family:var(--mono); padding-top:6px;">
        ${fmt(totalFraisFiscaux + totalFraisFixes)}
      </td>
    </tr>`;

    document.getElementById('detail-table').innerHTML = html;

    const results = document.getElementById('results');
    results.style.display = 'block';
    // re-trigger animation
    results.style.animation = 'none';
    void results.offsetHeight;
    results.style.animation = '';
    results.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }
</script>

</body>
</html>
