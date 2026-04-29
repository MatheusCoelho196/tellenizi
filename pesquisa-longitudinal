<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pesquisa Longitudinal — Explorador Interativo</title>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,600;0,9..144,800;1,9..144,300&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
:root {
  --ink: #0f1117;
  --paper: #f5f2eb;
  --cream: #ede9de;
  --blue: #1a3a6b;
  --blue-lt: #2d5be3;
  --teal: #0d6e6e;
  --amber: #c17a1a;
  --red: #b83232;
  --green: #1a6b3c;
  --muted: #6b6757;
  --border: rgba(15,17,23,0.12);
  --card: #fff;
  --r: 12px;
}
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--paper);
  color: var(--ink);
  min-height: 100vh;
  overflow-x: hidden;
}

/* ── HERO ── */
.hero {
  position: relative;
  padding: 80px 40px 60px;
  background: var(--blue);
  overflow: hidden;
}
.hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse 80% 60% at 70% 50%, #2d4fa0 0%, transparent 70%);
}
.hero-grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,.04) 1px, transparent 1px);
  background-size: 40px 40px;
}
.hero-content { position: relative; max-width: 860px; margin: 0 auto; }
.hero-tag {
  display: inline-block;
  font-size: 11px;
  font-weight: 500;
  letter-spacing: .12em;
  text-transform: uppercase;
  color: #a8c4e8;
  border: 1px solid rgba(168,196,232,.3);
  padding: 5px 14px;
  border-radius: 20px;
  margin-bottom: 24px;
}
.hero h1 {
  font-family: 'Fraunces', serif;
  font-size: clamp(42px, 7vw, 80px);
  font-weight: 800;
  color: #fff;
  line-height: 1.0;
  letter-spacing: -.02em;
  margin-bottom: 20px;
}
.hero h1 em {
  font-style: italic;
  font-weight: 300;
  color: #a8c4e8;
}
.hero-sub {
  font-size: 16px;
  color: #8ba8cc;
  max-width: 520px;
  line-height: 1.7;
  margin-bottom: 36px;
}
.hero-stats {
  display: flex;
  gap: 32px;
  flex-wrap: wrap;
}
.hero-stat { color: #fff; }
.hero-stat .n { font-family: 'Fraunces', serif; font-size: 32px; font-weight: 600; }
.hero-stat .l { font-size: 12px; color: #8ba8cc; margin-top: 2px; }

/* ── NAV ── */
.nav {
  background: var(--paper);
  border-bottom: 1px solid var(--border);
  position: sticky;
  top: 0;
  z-index: 100;
}
.nav-inner {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  gap: 0;
  overflow-x: auto;
}
.nav-btn {
  padding: 16px 24px;
  font-family: 'DM Sans', sans-serif;
  font-size: 13px;
  font-weight: 400;
  color: var(--muted);
  background: transparent;
  border: none;
  border-bottom: 2px solid transparent;
  cursor: pointer;
  white-space: nowrap;
  transition: all .2s;
}
.nav-btn:hover { color: var(--ink); }
.nav-btn.active { color: var(--blue); border-bottom-color: var(--blue); font-weight: 500; }

/* ── MAIN ── */
.main { max-width: 1000px; margin: 0 auto; padding: 40px 24px 80px; }

.section { display: none; }
.section.active { display: block; }

/* ── TYPOGRAPHY ── */
.sec-label {
  font-size: 11px;
  font-weight: 500;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 8px;
}
.sec-title {
  font-family: 'Fraunces', serif;
  font-size: clamp(28px, 4vw, 40px);
  font-weight: 600;
  color: var(--ink);
  line-height: 1.15;
  margin-bottom: 16px;
}
.sec-desc {
  font-size: 15px;
  color: var(--muted);
  line-height: 1.75;
  max-width: 620px;
  margin-bottom: 40px;
}

/* ── CARDS ── */
.card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--r);
  padding: 24px;
}
.card-grid { display: grid; gap: 16px; }
.card-grid.cols2 { grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); }
.card-grid.cols3 { grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); }

/* ── DIVIDER ── */
.divider { border: none; border-top: 1px solid var(--border); margin: 40px 0; }

/* ── CONCEPT SECTION ── */
.concept-hero {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
  margin-bottom: 32px;
}
@media(max-width:620px){ .concept-hero { grid-template-columns: 1fr; } }

.analogy-card {
  border: 1px solid var(--border);
  border-radius: var(--r);
  padding: 28px;
  position: relative;
  overflow: hidden;
}
.analogy-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
}
.analogy-card.photo::before { background: var(--muted); }
.analogy-card.film::before { background: var(--blue-lt); }
.analogy-icon {
  font-size: 32px;
  margin-bottom: 12px;
  display: block;
}
.analogy-card h3 {
  font-family: 'Fraunces', serif;
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 8px;
}
.analogy-card p { font-size: 14px; color: var(--muted); line-height: 1.7; }

.elements-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 12px;
  margin-bottom: 32px;
}
.element-item {
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 16px;
  border-left: 3px solid var(--blue-lt);
}
.element-item h4 { font-size: 13px; font-weight: 500; margin-bottom: 4px; }
.element-item p { font-size: 12px; color: var(--muted); line-height: 1.6; }

.callout {
  background: #eef3fb;
  border: 1px solid #c0d4f0;
  border-radius: var(--r);
  padding: 20px 24px;
  display: flex;
  gap: 14px;
  align-items: flex-start;
  margin-bottom: 24px;
}
.callout-icon { font-size: 20px; flex-shrink: 0; margin-top: 2px; }
.callout-text { font-size: 14px; color: var(--ink); line-height: 1.7; }
.callout-text strong { color: var(--blue); }

/* ── TIMELINE SECTION ── */
.timeline-controls {
  display: flex;
  gap: 12px;
  align-items: center;
  margin-bottom: 32px;
  flex-wrap: wrap;
}
.btn {
  padding: 10px 22px;
  border-radius: 8px;
  font-family: 'DM Sans', sans-serif;
  font-size: 13px;
  font-weight: 500;
  cursor: pointer;
  border: 1px solid var(--border);
  background: var(--card);
  color: var(--ink);
  transition: all .15s;
}
.btn:hover { background: var(--cream); }
.btn.primary { background: var(--blue); color: #fff; border-color: var(--blue); }
.btn.primary:hover { background: #1e47a0; }
.btn:disabled { opacity: .5; cursor: default; }

.wave-track {
  display: flex;
  align-items: flex-start;
  gap: 0;
  margin-bottom: 40px;
  position: relative;
}
.wave-node {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex: 1;
}
.wave-circle {
  width: 52px;
  height: 52px;
  border-radius: 50%;
  border: 2px solid var(--border);
  background: var(--card);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Fraunces', serif;
  font-size: 14px;
  font-weight: 600;
  color: var(--muted);
  transition: all .5s cubic-bezier(.34,1.56,.64,1);
  position: relative;
  z-index: 2;
}
.wave-circle.active {
  background: var(--blue);
  border-color: var(--blue);
  color: #fff;
  transform: scale(1.15);
  box-shadow: 0 0 0 8px rgba(45,91,227,.12);
}
.wave-circle.done {
  background: var(--blue-lt);
  border-color: var(--blue-lt);
  color: #fff;
  transform: scale(1.0);
}
.wave-label {
  font-size: 11px;
  color: var(--muted);
  text-align: center;
  margin-top: 8px;
  max-width: 80px;
  line-height: 1.4;
}
.wave-label strong { display: block; font-size: 12px; color: var(--ink); font-weight: 500; }
.wave-line {
  flex: 1;
  height: 2px;
  background: var(--border);
  margin-top: 25px;
  transition: background .5s;
  position: relative;
  z-index: 1;
}
.wave-line.filled { background: var(--blue-lt); }

.participants-area { margin-bottom: 28px; }
.participant-track {
  display: flex;
  align-items: center;
  gap: 4px;
  margin-bottom: 8px;
}
.p-label { font-size: 11px; color: var(--muted); width: 28px; flex-shrink: 0; }
.p-bubble {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: 1.5px solid var(--border);
  background: var(--cream);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 10px;
  font-weight: 500;
  color: var(--muted);
  flex-shrink: 0;
  transition: all .4s;
  position: relative;
}
.p-bubble.measured {
  border-width: 2px;
  font-size: 11px;
}
.p-bubble.lost { opacity: .25; }
.p-connector {
  flex: 1;
  height: 1px;
  background: var(--border);
  transition: background .4s;
}
.p-connector.filled { background: currentColor; }

.stats-row {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
  margin-bottom: 20px;
}
@media(max-width:500px){ .stats-row { grid-template-columns: repeat(2,1fr); } }
.stat-block {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 14px 16px;
}
.stat-block .val {
  font-family: 'Fraunces', serif;
  font-size: 28px;
  font-weight: 600;
  color: var(--ink);
  line-height: 1;
}
.stat-block .lbl { font-size: 11px; color: var(--muted); margin-top: 4px; }

.wave-msg {
  font-size: 13px;
  color: var(--blue-lt);
  font-weight: 500;
  min-height: 20px;
  transition: opacity .3s;
}

/* ── SIMULATOR ── */
.sim-controls {
  display: flex;
  gap: 20px;
  margin-bottom: 28px;
  flex-wrap: wrap;
  align-items: flex-end;
}
.slider-field { display: flex; flex-direction: column; gap: 6px; flex: 1; min-width: 140px; }
.slider-field label { font-size: 12px; color: var(--muted); }
.slider-field input[type=range] { width: 100%; accent-color: var(--blue); }
.slider-val { font-size: 12px; font-weight: 500; color: var(--ink); }
.chart-wrap { background: var(--card); border: 1px solid var(--border); border-radius: var(--r); padding: 24px; margin-bottom: 20px; }
.chart-wrap canvas { max-height: 300px; }
.legend-row { display: flex; gap: 12px; flex-wrap: wrap; margin-bottom: 16px; }
.leg-item { display: flex; align-items: center; gap: 5px; font-size: 12px; color: var(--muted); }
.leg-dot { width: 10px; height: 10px; border-radius: 50%; }
.insight { background: var(--cream); border: 1px solid var(--border); border-radius: var(--r); padding: 16px 20px; font-size: 13px; color: var(--muted); line-height: 1.7; }
.insight strong { color: var(--ink); font-weight: 500; }

/* ── COMPARE ── */
.compare-top {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  margin-bottom: 28px;
}
@media(max-width:580px){ .compare-top { grid-template-columns: 1fr; } }
.compare-card {
  border: 1px solid var(--border);
  border-radius: var(--r);
  overflow: hidden;
}
.compare-card.featured { border-color: var(--blue-lt); border-width: 2px; }
.compare-head {
  padding: 16px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.compare-head h3 { font-family: 'Fraunces', serif; font-size: 18px; font-weight: 600; }
.badge { font-size: 10px; font-weight: 500; padding: 3px 10px; border-radius: 20px; }
.compare-vis {
  background: var(--cream);
  height: 130px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 16px;
}
.compare-desc { padding: 16px 20px; font-size: 13px; color: var(--muted); line-height: 1.7; }

.table-compare { width: 100%; border-collapse: collapse; font-size: 13px; }
.table-compare th {
  background: var(--blue);
  color: #fff;
  padding: 10px 14px;
  text-align: left;
  font-weight: 500;
  font-size: 12px;
}
.table-compare th:first-child { border-radius: 8px 0 0 0; }
.table-compare th:last-child { border-radius: 0 8px 0 0; }
.table-compare td { padding: 10px 14px; border-bottom: 1px solid var(--border); color: var(--muted); }
.table-compare td:first-child { font-weight: 500; color: var(--ink); }
.table-compare td.pos { color: var(--green); font-weight: 500; }
.table-compare tr:last-child td { border-bottom: none; }
.table-compare tr:nth-child(even) td { background: #fafaf8; }

/* ── EXEMPLOS ── */
.example-list { display: flex; flex-direction: column; gap: 12px; }
.ex-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--r);
  padding: 0;
  overflow: hidden;
  cursor: pointer;
  transition: box-shadow .2s, transform .15s;
}
.ex-card:hover { box-shadow: 0 4px 20px rgba(0,0,0,.07); transform: translateY(-1px); }
.ex-top { display: flex; align-items: stretch; }
.ex-accent { width: 5px; flex-shrink: 0; }
.ex-body { padding: 18px 20px; flex: 1; }
.ex-meta { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 6px; }
.ex-title { font-family: 'Fraunces', serif; font-size: 17px; font-weight: 600; }
.ex-tag { font-size: 10px; font-weight: 500; padding: 3px 10px; border-radius: 20px; margin-left: 8px; white-space: nowrap; }
.ex-country { font-size: 11px; color: var(--muted); margin-bottom: 8px; }
.ex-desc { font-size: 13px; color: var(--muted); line-height: 1.65; margin-bottom: 12px; }
.ex-bar-wrap { display: flex; align-items: center; gap: 10px; }
.ex-bar-bg { flex: 1; height: 4px; background: var(--cream); border-radius: 2px; overflow: hidden; }
.ex-bar-fill { height: 100%; border-radius: 2px; transition: width 1.2s ease; width: 0; }
.ex-years { font-size: 11px; color: var(--muted); white-space: nowrap; }

/* ── MODALIDADES ── */
.mod-tabs { display: flex; gap: 6px; margin-bottom: 20px; flex-wrap: wrap; }
.mod-tab { padding: 8px 16px; border-radius: 20px; border: 1px solid var(--border); font-size: 13px; cursor: pointer; background: var(--card); color: var(--muted); transition: all .15s; }
.mod-tab.active { background: var(--blue); color: #fff; border-color: var(--blue); }
.mod-content { display: none; }
.mod-content.active { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
@media(max-width:580px){ .mod-content.active { grid-template-columns: 1fr; } }
.mod-info { }
.mod-info h3 { font-family: 'Fraunces', serif; font-size: 22px; font-weight: 600; margin-bottom: 10px; }
.mod-info p { font-size: 14px; color: var(--muted); line-height: 1.75; margin-bottom: 14px; }
.mod-info ul { padding-left: 18px; display: flex; flex-direction: column; gap: 6px; }
.mod-info li { font-size: 13px; color: var(--muted); line-height: 1.6; }
.mod-vis { background: var(--cream); border-radius: var(--r); padding: 20px; display: flex; align-items: center; justify-content: center; min-height: 200px; }

/* ── ROTEIRO ── */
.roteiro-list { display: flex; flex-direction: column; gap: 1px; }
.roteiro-item {
  display: grid;
  grid-template-columns: 56px 1fr;
  gap: 0;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 0;
  overflow: hidden;
}
.roteiro-item:first-child { border-radius: var(--r) var(--r) 0 0; }
.roteiro-item:last-child { border-radius: 0 0 var(--r) var(--r); }
.rot-num {
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Fraunces', serif;
  font-size: 20px;
  font-weight: 800;
  padding: 20px 0;
}
.rot-body { padding: 18px 20px; border-left: 1px solid var(--border); }
.rot-head { display: flex; align-items: center; gap: 10px; margin-bottom: 6px; }
.rot-head h4 { font-size: 14px; font-weight: 500; }
.rot-time { font-size: 11px; padding: 2px 8px; border-radius: 20px; background: var(--cream); color: var(--muted); }
.rot-text { font-size: 13px; color: var(--muted); line-height: 1.65; margin-bottom: 8px; }
.rot-tip { font-size: 12px; color: var(--amber); background: #fef3dc; padding: 6px 10px; border-radius: 6px; border-left: 3px solid var(--amber); }

/* ── SCROLL ANIMATION ── */
.fade-in { opacity: 0; transform: translateY(16px); transition: opacity .5s, transform .5s; }
.fade-in.visible { opacity: 1; transform: none; }
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-tag">Metodologia Científica</div>
    <h1>Pesquisa<br><em>Longitudinal</em></h1>
    <p class="hero-sub">Um explorador interativo completo — do conceito fundamental aos exemplos reais que mudaram a ciência.</p>
    <div class="hero-stats">
      <div class="hero-stat"><div class="n">5</div><div class="l">estudos reais</div></div>
      <div class="hero-stat"><div class="n">80+</div><div class="l">anos de ciência</div></div>
    </div>
  </div>
</div>

<!-- NAV -->
<nav class="nav">
  <div class="nav-inner">
    <button class="nav-btn active" onclick="goTo('timeline')">Linha do Tempo</button>
    <button class="nav-btn" onclick="goTo('simulador')">Simulador</button>
    <button class="nav-btn" onclick="goTo('comparador')">Comparador</button>
    <button class="nav-btn" onclick="goTo('modalidades')">Modalidades</button>
  </div>
</nav>

<!-- MAIN -->
<div class="main">

<!-- ══════════ SEÇÃO: CONCEITO ══════════ -->
<!-- ══════════ SEÇÃO: MODALIDADES ══════════ -->
<section class="section" id="s-modalidades">
  <div class="fade-in">
    <div class="sec-label">Seção 02</div>
    <h2 class="sec-title">Modalidades</h2>
    <p class="sec-desc">A pesquisa longitudinal não é um método único. Ela engloba diferentes designs que variam na forma como as unidades de análise são definidas e acompanhadas ao longo do tempo.</p>
  </div>

  <div class="mod-tabs fade-in">
    <button class="mod-tab active" onclick="switchMod(0)">Estudo de Painel</button>
    <button class="mod-tab" onclick="switchMod(1)">Estudo de Coorte</button>
    <button class="mod-tab" onclick="switchMod(2)">Série Temporal</button>
    <button class="mod-tab" onclick="switchMod(3)">Estudo de Tendência</button>
  </div>

  <!-- Painel -->
  <div class="mod-content active" id="mod0">
    <div class="mod-info">
      <h3>Estudo de Painel</h3>
      <p>Os <strong>mesmos indivíduos</strong> são medidos repetidamente ao longo do tempo. É o design mais robusto para inferência causal, pois controla características estáveis dos participantes.</p>
      <p>Cada participante serve como seu próprio controle — o que elimina automaticamente variáveis de confusão fixas como gênero, origem familiar e genética.</p>
      <ul>
        <li>Design mais comum em psicologia e saúde</li>
        <li>Permite modelos de efeito fixo (controla heterogeneidade individual)</li>
        <li>Mais vulnerável ao atrito amostral ao longo do tempo</li>
      </ul>
      <div style="margin-top:16px;background:#eef3fb;border-radius:8px;padding:14px 16px;">
        <div style="font-size:11px;color:var(--blue);font-weight:500;margin-bottom:4px;">EXEMPLO REAL</div>
        <div style="font-size:13px;color:var(--muted);line-height:1.6">Acompanhar os <em>mesmos</em> estudantes universitários do 1º ao 4º ano medindo saúde mental a cada semestre.</div>
      </div>
    </div>
    <div class="mod-vis">
      <svg width="100%" viewBox="0 0 280 180" style="max-width:280px">
        <defs><marker id="arr" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto"><path d="M2 1L8 5L2 9" fill="none" stroke="#1a3a6b" stroke-width="1.5" stroke-linecap="round"/></marker></defs>
        <!-- Time axis -->
        <line x1="30" y1="160" x2="260" y2="160" stroke="#c8c4b8" stroke-width="1.5" marker-end="url(#arr)"/>
        <text x="145" y="175" text-anchor="middle" font-size="10" fill="#6b6757" font-family="sans-serif">Tempo</text>
        <!-- Wave labels -->
        <text x="60" y="155" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">T0</text>
        <text x="140" y="155" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">T1</text>
        <text x="220" y="155" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">T2</text>
        <!-- Participant A -->
        <circle cx="60" cy="50" r="14" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
        <circle cx="140" cy="40" r="14" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
        <circle cx="220" cy="60" r="14" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
        <line x1="74" y1="50" x2="126" y2="42" stroke="#1a3a6b" stroke-width="1" stroke-dasharray="4 2"/>
        <line x1="154" y1="42" x2="206" y2="58" stroke="#1a3a6b" stroke-width="1" stroke-dasharray="4 2"/>
        <text x="60" y="54" text-anchor="middle" font-size="9" fill="#1a3a6b" font-family="sans-serif">A</text>
        <text x="140" y="44" text-anchor="middle" font-size="9" fill="#1a3a6b" font-family="sans-serif">A</text>
        <text x="220" y="64" text-anchor="middle" font-size="9" fill="#1a3a6b" font-family="sans-serif">A</text>
        <!-- Participant B -->
        <circle cx="60" cy="100" r="14" fill="#9fe1cb" stroke="#0d6e6e" stroke-width="1.5"/>
        <circle cx="140" cy="90" r="14" fill="#9fe1cb" stroke="#0d6e6e" stroke-width="1.5"/>
        <circle cx="220" cy="110" r="14" fill="#9fe1cb" stroke="#0d6e6e" stroke-width="1.5"/>
        <line x1="74" y1="100" x2="126" y2="92" stroke="#0d6e6e" stroke-width="1" stroke-dasharray="4 2"/>
        <line x1="154" y1="92" x2="206" y2="108" stroke="#0d6e6e" stroke-width="1" stroke-dasharray="4 2"/>
        <text x="60" y="104" text-anchor="middle" font-size="9" fill="#0d6e6e" font-family="sans-serif">B</text>
        <text x="140" y="94" text-anchor="middle" font-size="9" fill="#0d6e6e" font-family="sans-serif">B</text>
        <text x="220" y="114" text-anchor="middle" font-size="9" fill="#0d6e6e" font-family="sans-serif">B</text>
        <text x="10" y="54" font-size="9" fill="#6b6757" font-family="sans-serif">Mesmos</text>
        <text x="10" y="66" font-size="9" fill="#6b6757" font-family="sans-serif">sujeitos</text>
      </svg>
    </div>
  </div>

  <!-- Coorte -->
  <div class="mod-content" id="mod1">
    <div class="mod-info">
      <h3>Estudo de Coorte</h3>
      <p>Um grupo que compartilha uma <strong>característica comum</strong> (ano de nascimento, exposição a um evento, início de um curso) é acompanhado ao longo do tempo.</p>
      <p>Pode ou não coletar dados dos exatos mesmos indivíduos — em coortes abertas, novos membros podem entrar ao longo do tempo.</p>
      <ul>
        <li>Muito usado em epidemiologia e saúde pública</li>
        <li>Permite comparar coortes de diferentes gerações</li>
        <li>Ideal para estudar efeitos de geração versus de envelhecimento</li>
      </ul>
      <div style="margin-top:16px;background:#eef3fb;border-radius:8px;padding:14px 16px;">
        <div style="font-size:11px;color:var(--blue);font-weight:500;margin-bottom:4px;">EXEMPLO REAL</div>
        <div style="font-size:13px;color:var(--muted);line-height:1.6">Coorte de Nascimentos de Pelotas — todos os bebês nascidos em 1982 em Pelotas/RS, acompanhados por décadas.</div>
      </div>
    </div>
    <div class="mod-vis">
      <svg width="100%" viewBox="0 0 280 180" style="max-width:280px">
        <rect x="20" y="20" width="240" height="130" rx="10" fill="#eef3fb" stroke="#c0d4f0" stroke-width="1"/>
        <text x="140" y="38" text-anchor="middle" font-size="10" font-weight="500" fill="#1a3a6b" font-family="sans-serif">Coorte: nascidos em 1982</text>
        <circle cx="60" cy="80" r="12" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
        <circle cx="100" cy="90" r="12" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
        <circle cx="140" cy="70" r="12" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
        <circle cx="180" cy="85" r="12" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
        <circle cx="220" cy="75" r="12" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
        <text x="60" y="84" text-anchor="middle" font-size="8" fill="#1a3a6b" font-family="sans-serif">1</text>
        <text x="100" y="94" text-anchor="middle" font-size="8" fill="#1a3a6b" font-family="sans-serif">2</text>
        <text x="140" y="74" text-anchor="middle" font-size="8" fill="#1a3a6b" font-family="sans-serif">3</text>
        <text x="180" y="89" text-anchor="middle" font-size="8" fill="#1a3a6b" font-family="sans-serif">4</text>
        <text x="220" y="79" text-anchor="middle" font-size="8" fill="#1a3a6b" font-family="sans-serif">5</text>
        <text x="140" y="125" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">Acompanhados por décadas →</text>
        <text x="140" y="138" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">1982 ·· 1993 ·· 2004 ·· 2015</text>
      </svg>
    </div>
  </div>

  <!-- Série temporal -->
  <div class="mod-content" id="mod2">
    <div class="mod-info">
      <h3>Série Temporal</h3>
      <p>Medições repetidas de <strong>variáveis agregadas</strong> em intervalos regulares, geralmente sem foco em indivíduos específicos. Muito usada em economia, epidemiologia e ciências ambientais.</p>
      <p>Não rastreia as mesmas pessoas, mas monitora como um indicador populacional evolui ao longo do tempo.</p>
      <ul>
        <li>Ideal para tendências e ciclos de longo prazo</li>
        <li>Permite análise de sazonalidade e autocorrelação</li>
        <li>Base de modelos como ARIMA e análises de intervenção</li>
      </ul>
      <div style="margin-top:16px;background:#eef3fb;border-radius:8px;padding:14px 16px;">
        <div style="font-size:11px;color:var(--blue);font-weight:500;margin-bottom:4px;">EXEMPLO</div>
        <div style="font-size:13px;color:var(--muted);line-height:1.6">Taxa de desemprego mensal no Brasil medida por 20 anos consecutivos pelo IBGE.</div>
      </div>
    </div>
    <div class="mod-vis">
      <svg width="100%" viewBox="0 0 280 160" style="max-width:280px">
        <polyline points="20,120 50,100 80,110 110,80 140,90 170,60 200,70 240,40" fill="none" stroke="#1a3a6b" stroke-width="2" stroke-linejoin="round"/>
        <circle cx="20" cy="120" r="4" fill="#1a3a6b"/>
        <circle cx="50" cy="100" r="4" fill="#1a3a6b"/>
        <circle cx="80" cy="110" r="4" fill="#1a3a6b"/>
        <circle cx="110" cy="80" r="4" fill="#1a3a6b"/>
        <circle cx="140" cy="90" r="4" fill="#1a3a6b"/>
        <circle cx="170" cy="60" r="4" fill="#1a3a6b"/>
        <circle cx="200" cy="70" r="4" fill="#1a3a6b"/>
        <circle cx="240" cy="40" r="4" fill="#1a3a6b"/>
        <line x1="20" y1="130" x2="250" y2="130" stroke="#c8c4b8" stroke-width="1"/>
        <text x="135" y="148" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">T1 · T2 · T3 · T4 · T5 · T6 · T7 · T8</text>
        <text x="14" y="15" font-size="9" fill="#6b6757" font-family="sans-serif" transform="rotate(-90,14,15)">Variável</text>
      </svg>
    </div>
  </div>

  <!-- Tendência -->
  <div class="mod-content" id="mod3">
    <div class="mod-info">
      <h3>Estudo de Tendência</h3>
      <p><strong>Amostras diferentes</strong> são coletadas em momentos distintos dentro de uma mesma população. Não acompanha os mesmos indivíduos, mas permite identificar mudanças populacionais ao longo do tempo.</p>
      <p>É menos robusto que o painel, pois não controla diferenças individuais — mas é muito mais viável logisticamente para populações grandes.</p>
      <ul>
        <li>Muito usado em pesquisas de opinião e eleitorais</li>
        <li>Identifica mudanças culturais e sociais de longo prazo</li>
        <li>Custo menor que o painel; mais fácil de executar</li>
      </ul>
      <div style="margin-top:16px;background:#eef3fb;border-radius:8px;padding:14px 16px;">
        <div style="font-size:11px;color:var(--blue);font-weight:500;margin-bottom:4px;">EXEMPLO</div>
        <div style="font-size:13px;color:var(--muted);line-height:1.6">Pesquisa aplicada a diferentes amostras da população brasileira a cada 2 anos para medir confiança nas instituições.</div>
      </div>
    </div>
    <div class="mod-vis">
      <svg width="100%" viewBox="0 0 280 170" style="max-width:280px">
        <text x="70" y="20" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">2010</text>
        <text x="170" y="20" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">2020</text>
        <circle cx="55" cy="70" r="10" fill="#d3d1c7" stroke="#888780" stroke-width="1"/>
        <circle cx="70" cy="55" r="10" fill="#d3d1c7" stroke="#888780" stroke-width="1"/>
        <circle cx="85" cy="80" r="10" fill="#d3d1c7" stroke="#888780" stroke-width="1"/>
        <circle cx="55" cy="95" r="10" fill="#d3d1c7" stroke="#888780" stroke-width="1"/>
        <text x="70" y="115" text-anchor="middle" font-size="8" fill="#6b6757" font-family="sans-serif">Amostra diferente</text>
        <circle cx="155" cy="75" r="10" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1"/>
        <circle cx="170" cy="60" r="10" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1"/>
        <circle cx="185" cy="85" r="10" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1"/>
        <circle cx="155" cy="100" r="10" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1"/>
        <text x="170" y="120" text-anchor="middle" font-size="8" fill="#1a3a6b" font-family="sans-serif">Amostra diferente</text>
        <text x="140" y="148" text-anchor="middle" font-size="8" fill="#6b6757" font-family="sans-serif">Mesma população, amostras diferentes em cada onda</text>
        <line x1="105" y1="80" x2="145" y2="80" stroke="#c8c4b8" stroke-width="1" stroke-dasharray="4 2"/>
      </svg>
    </div>
  </div>
</section>

<!-- ══════════ SEÇÃO: LINHA DO TEMPO ANIMADA ══════════ -->
<section class="section active" id="s-timeline">
  <div class="fade-in">
    <div class="sec-label">Seção 03</div>
    <h2 class="sec-title">Linha do Tempo Interativa</h2>
    <p class="sec-desc">Veja como uma pesquisa longitudinal se desenvolve onda a onda — com coleta de dados, atrito amostral e estatísticas em tempo real.</p>
  </div>

  <div class="timeline-controls fade-in">
    <button class="btn primary" id="btnPlay" onclick="playTimeline()">▶ Iniciar estudo</button>
    <button class="btn" onclick="resetTimeline()">↺ Reiniciar</button>
    <div class="wave-msg" id="waveMsg"></div>
  </div>

  <div class="wave-track fade-in" id="waveTrack"></div>
  <div class="participants-area fade-in" id="participantsArea"></div>

  <div class="stats-row fade-in">
    <div class="stat-block"><div class="val" id="stWave">—</div><div class="lbl">Onda atual</div></div>
    <div class="stat-block"><div class="val" id="stN">10</div><div class="lbl">Participantes ativos</div></div>
    <div class="stat-block"><div class="val" id="stLoss">0%</div><div class="lbl">Atrito amostral</div></div>
    <div class="stat-block"><div class="val" id="stYears">0</div><div class="lbl">Anos de estudo</div></div>
  </div>
</section>

<!-- ══════════ SEÇÃO: SIMULADOR ══════════ -->
<section class="section" id="s-simulador">
  <div class="fade-in">
    <div class="sec-label">Seção 04</div>
    <h2 class="sec-title">Simulador Estatístico</h2>
    <p class="sec-desc">Simule trajetórias individuais de participantes ao longo das ondas. Ajuste os parâmetros e observe o impacto do atrito amostral nos resultados.</p>
  </div>

  <div class="sim-controls fade-in">
    <div class="slider-field">
      <label>Participantes</label>
      <input type="range" min="5" max="25" value="12" id="slN" step="1" oninput="updateSim()">
      <span class="slider-val" id="lblN">12</span>
    </div>
    <div class="slider-field">
      <label>Ondas de coleta</label>
      <input type="range" min="2" max="6" value="4" id="slW" step="1" oninput="updateSim()">
      <span class="slider-val" id="lblW">4</span>
    </div>
    <div class="slider-field">
      <label>Atrito por onda (%)</label>
      <input type="range" min="0" max="30" value="12" id="slA" step="1" oninput="updateSim()">
      <span class="slider-val" id="lblA">12%</span>
    </div>
    <button class="btn primary" onclick="genSim()">Gerar nova amostra</button>
  </div>

  <div class="chart-wrap fade-in">
    <div class="legend-row" id="simLegend"></div>
    <canvas id="simChart" role="img" aria-label="Trajetórias individuais dos participantes ao longo das ondas de coleta"></canvas>
  </div>
  <div class="insight fade-in" id="simInsight">Configure os parâmetros acima e clique em <strong>Gerar nova amostra</strong>.</div>
</section>

<!-- ══════════ SEÇÃO: COMPARADOR ══════════ -->
<section class="section" id="s-comparador">
  <div class="fade-in">
    <div class="sec-label">Seção 05</div>
    <h2 class="sec-title">Longitudinal vs. Transversal</h2>
    <p class="sec-desc">Entender a pesquisa longitudinal exige compará-la com seu principal rival metodológico. Cada design responde a tipos diferentes de perguntas científicas.</p>
  </div>

  <div class="compare-top fade-in">
    <div class="compare-card">
      <div class="compare-head" style="background:var(--cream)">
        <h3>Estudo Transversal</h3>
      </div>
      <div class="compare-vis">
        <svg width="220" viewBox="0 0 220 100">
          <rect x="10" y="30" width="180" height="40" rx="8" fill="#d3d1c7" stroke="#888780" stroke-width="1"/>
          <text x="100" y="55" text-anchor="middle" font-size="11" fill="#444441" font-family="sans-serif">Todos medidos no mesmo instante</text>
          <line x1="100" y1="78" x2="100" y2="90" stroke="#888" stroke-width="1"/>
          <text x="100" y="98" text-anchor="middle" font-size="9" fill="#6b6757" font-family="sans-serif">Um único ponto no tempo</text>
        </svg>
      </div>
      <div class="compare-desc">Captura grupos diferentes num único momento. Rápido e barato — mas não distingue correlação de causalidade, nem revela trajetórias.</div>
    </div>
    <div class="compare-card featured">
      <div class="compare-head" style="background:#eef3fb;">
        <h3 style="color:var(--blue)">Pesquisa Longitudinal</h3>
        <span class="badge" style="background:#dce8fb;color:var(--blue)">Mais robusto</span>
      </div>
      <div class="compare-vis">
        <svg width="220" viewBox="0 0 220 100">
          <circle cx="30" cy="30" r="12" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
          <circle cx="90" cy="30" r="12" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
          <circle cx="150" cy="30" r="12" fill="#b5d4f4" stroke="#1a3a6b" stroke-width="1.5"/>
          <circle cx="30" cy="70" r="12" fill="#9fe1cb" stroke="#0d6e6e" stroke-width="1.5"/>
          <circle cx="90" cy="70" r="12" fill="#9fe1cb" stroke="#0d6e6e" stroke-width="1.5"/>
          <circle cx="150" cy="70" r="12" fill="#9fe1cb" stroke="#0d6e6e" stroke-width="1.5"/>
          <line x1="42" y1="30" x2="78" y2="30" stroke="#1a3a6b" stroke-width="1" stroke-dasharray="4 2"/>
          <line x1="102" y1="30" x2="138" y2="30" stroke="#1a3a6b" stroke-width="1" stroke-dasharray="4 2"/>
          <line x1="42" y1="70" x2="78" y2="70" stroke="#0d6e6e" stroke-width="1" stroke-dasharray="4 2"/>
          <line x1="102" y1="70" x2="138" y2="70" stroke="#0d6e6e" stroke-width="1" stroke-dasharray="4 2"/>
          <text x="30" y="97" text-anchor="middle" font-size="8" fill="#6b6757" font-family="sans-serif">T0</text>
          <text x="90" y="97" text-anchor="middle" font-size="8" fill="#6b6757" font-family="sans-serif">T1</text>
          <text x="150" y="97" text-anchor="middle" font-size="8" fill="#6b6757" font-family="sans-serif">T2</text>
        </svg>
      </div>
      <div class="compare-desc">Acompanha os <strong>mesmos indivíduos</strong> ao longo do tempo. Revela trajetórias, mudanças e estabelece precedência temporal para inferência causal.</div>
    </div>
  </div>

  <div class="fade-in" style="overflow-x:auto;">
    <table class="table-compare">
      <thead>
        <tr>
          <th>Critério</th>
          <th>Estudo Transversal</th>
          <th>Pesquisa Longitudinal</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Dimensão temporal</td><td>Um único momento</td><td class="pos">Múltiplos momentos</td></tr>
        <tr><td>Participantes</td><td>Grupos diferentes</td><td class="pos">Mesmos indivíduos</td></tr>
        <tr><td>Mudança observada</td><td>Inferida/estimada</td><td class="pos">Diretamente observada</td></tr>
        <tr><td>Causalidade</td><td>Correlação apenas</td><td class="pos">Precedência temporal possível</td></tr>
        <tr><td>Custo</td><td class="pos">Baixo a moderado</td><td>Alto (anos de coleta)</td></tr>
        <tr><td>Duração</td><td class="pos">Dias a semanas</td><td>Meses a décadas</td></tr>
        <tr><td>Atrito amostral</td><td class="pos">Não se aplica</td><td>Problema real e relevante</td></tr>
        <tr><td>Ideal para</td><td>Prevalência, diagnósticos</td><td class="pos">Trajetórias, desenvolvimento</td></tr>
      </tbody>
    </table>
  </div>
</section>

<!-- ══════════ SEÇÃO: EXEMPLOS ══════════ -->

</div><!-- /main -->

<script>
// ── NAVIGATION ──
const sections = ['timeline','simulador','comparador','modalidades'];
function goTo(id) {
  document.querySelectorAll('.nav-btn').forEach((b,i) => b.classList.toggle('active', sections[i]===id));
  document.querySelectorAll('.section').forEach(s => s.classList.toggle('active', s.id==='s-'+id));
  window.scrollTo({top: document.querySelector('.nav').offsetTop, behavior:'smooth'});
  if(id==='simulador' && !simReady) initSim();
  observeFade();
}

// ── FADE IN ON SCROLL ──
function observeFade() {
  const els = document.querySelectorAll('.section.active .fade-in');
  els.forEach((el,i) => {
    setTimeout(() => el.classList.add('visible'), i*60);
  });
}
observeFade();

// ── MODALIDADES ──
function switchMod(i) {
  document.querySelectorAll('.mod-tab').forEach((t,j) => t.classList.toggle('active', i===j));
  document.querySelectorAll('.mod-content').forEach((c,j) => c.classList.toggle('active', i===j));
}

// ── TIMELINE ──
const waveData = [
  {label:'Baseline', sub:'T0 — Recrutamento', year:0},
  {label:'1ª Onda', sub:'T1 — Follow-up', year:1},
  {label:'2ª Onda', sub:'T2 — Follow-up', year:3},
  {label:'3ª Onda', sub:'T3 — Final', year:5},
];
const pColors = ['#1a3a6b','#0d6e6e','#b83232','#c17a1a','#7c3aed','#1a6b3c','#953d5a','#185fa5','#3b6d11','#634808'];
let participants = [];
let curWave = -1;
let tlPlaying = false;

function buildTrack() {
  const track = document.getElementById('waveTrack');
  track.innerHTML = '';
  waveData.forEach((w,i) => {
    const node = document.createElement('div');
    node.className = 'wave-node';
    node.innerHTML = `<div class="wave-circle" id="wc${i}">${i===0?'T0':'T'+i}</div>
      <div class="wave-label"><strong>${w.label}</strong>${w.sub}</div>`;
    track.appendChild(node);
    if(i < waveData.length-1) {
      const line = document.createElement('div');
      line.className = 'wave-line';
      line.id = 'wl'+i;
      track.appendChild(line);
    }
  });
}

function buildParticipants() {
  participants = pColors.slice(0,10).map((c,i) => ({id:i, color:c, label:'P'+(i+1), measured:[], lost:-1}));
  renderParticipants();
}

function renderParticipants() {
  const area = document.getElementById('participantsArea');
  area.innerHTML = '';
  participants.forEach(p => {
    const row = document.createElement('div');
    row.className = 'participant-track';
    const lbl = document.createElement('div');
    lbl.className = 'p-label';
    lbl.textContent = p.label;
    row.appendChild(lbl);
    waveData.forEach((w,wi) => {
      const bubble = document.createElement('div');
      bubble.className = 'p-bubble';
      const measured = p.measured.includes(wi);
      const lost = p.lost !== -1 && wi >= p.lost;
      if(measured) {
        bubble.style.borderColor = p.color;
        bubble.style.background = p.color+'18';
        bubble.style.color = p.color;
        bubble.className = 'p-bubble measured';
        bubble.innerHTML = '✓';
      } else if(lost) {
        bubble.className = 'p-bubble lost';
        bubble.innerHTML = '×';
      } else {
        bubble.innerHTML = '·';
      }
      row.appendChild(bubble);
      if(wi < waveData.length-1) {
        const conn = document.createElement('div');
        conn.className = 'p-connector';
        if(measured && p.measured.includes(wi+1)) {
          conn.style.background = p.color;
          conn.className = 'p-connector filled';
        }
        row.appendChild(conn);
      }
    });
    const info = document.createElement('div');
    info.style = 'font-size:11px;color:var(--muted);margin-left:10px;min-width:80px';
    info.textContent = p.lost !== -1 && curWave >= p.lost ? 'Saiu em T'+p.lost : (p.measured.length>0 ? p.measured.length+' medições' : '');
    row.appendChild(info);
    area.appendChild(row);
  });
}

function updateTLStats() {
  const active = participants.filter(p => p.lost===-1 || p.lost > curWave).length;
  const total = participants.length;
  document.getElementById('stWave').textContent = curWave >= 0 ? 'T'+curWave : '—';
  document.getElementById('stN').textContent = active;
  document.getElementById('stLoss').textContent = Math.round((1-active/total)*100)+'%';
  document.getElementById('stYears').textContent = curWave >= 0 ? waveData[curWave].year : 0;
}

async function playTimeline() {
  if(tlPlaying) return;
  tlPlaying = true;
  document.getElementById('btnPlay').disabled = true;
  const msgs = ['Aplicando questionários baseline…','Primeiro follow-up — dados coletados…','Segunda onda concluída — padrões emergindo…','Estudo finalizado — análise completa!'];
  for(let w=0; w<4; w++) {
    curWave = w;
    for(let d=0; d<4; d++) {
      const el = document.getElementById('wc'+d);
      if(d < w) el.className='wave-circle done';
      else if(d===w) el.className='wave-circle active';
      else el.className='wave-circle';
      const ln = document.getElementById('wl'+d);
      if(ln) ln.classList.toggle('filled', d < w);
    }
    document.getElementById('waveMsg').textContent = msgs[w];
    participants.forEach((p,i) => {
      if(p.lost !== -1 && p.lost <= w) return;
      if(w > 0 && p.lost === -1 && Math.random() < 0.12 && i < 4) {
        p.lost = w;
      } else {
        p.measured.push(w);
      }
    });
    renderParticipants();
    updateTLStats();
    await new Promise(r => setTimeout(r,1600));
  }
  tlPlaying = false;
}

function resetTimeline() {
  curWave = -1; tlPlaying = false;
  document.getElementById('btnPlay').disabled = false;
  document.getElementById('waveMsg').textContent = '';
  for(let d=0;d<4;d++){
    const el = document.getElementById('wc'+d);
    if(el) el.className='wave-circle';
    const ln = document.getElementById('wl'+d);
    if(ln) ln.classList.remove('filled');
  }
  buildParticipants();
  updateTLStats();
}

buildTrack();
buildParticipants();

// ── SIMULATOR ──
let simChart = null;
let simReady = false;
const SIM_COLORS = ['#1a3a6b','#0d6e6e','#b83232','#c17a1a','#7c3aed','#1a6b3c','#953d5a','#185fa5','#3b6d11','#634808','#0f766e','#b45309','#553d5a'];

function updateSim() {
  document.getElementById('lblN').textContent = document.getElementById('slN').value;
  document.getElementById('lblW').textContent = document.getElementById('slW').value;
  document.getElementById('lblA').textContent = document.getElementById('slA').value+'%';
}

function initSim() {
  simReady = true;
  const ctx = document.getElementById('simChart').getContext('2d');
  simChart = new Chart(ctx, {
    type:'line',
    data:{ labels:[], datasets:[] },
    options:{
      responsive:true,
      maintainAspectRatio:false,
      plugins:{ legend:{ display:false }, tooltip:{ mode:'index', intersect:false } },
      scales:{
        x:{ title:{ display:true, text:'Onda de coleta', font:{size:11} }, ticks:{font:{size:11}} },
        y:{ title:{ display:true, text:'Valor medido (0–100)', font:{size:11} }, min:0, max:100, ticks:{font:{size:11}} }
      },
      animation:{ duration:500 }
    }
  });
  genSim();
}

function genSim() {
  if(!simChart) return;
  updateSim();
  const n = +document.getElementById('slN').value;
  const w = +document.getElementById('slW').value;
  const a = +document.getElementById('slA').value/100;
  const labels = Array.from({length:w},(_,i)=>'T'+i);
  const datasets = [];
  let totalLost = 0;

  for(let i=0;i<n;i++){
    const color = SIM_COLORS[i%SIM_COLORS.length];
    let v = 25+Math.random()*55;
    let trend = (Math.random()-.45)*7;
    const data = [];
    let lost=false;
    for(let wi=0;wi<w;wi++){
      if(lost){ data.push(null); continue; }
      if(wi>0 && Math.random()<a){ lost=true; totalLost++; data.push(null); continue; }
      v = Math.min(100,Math.max(0,v+trend+(Math.random()-.5)*8));
      data.push(Math.round(v));
    }
    datasets.push({ label:'P'+(i+1), data, borderColor:color, backgroundColor:color+'15', borderWidth:1.5, pointRadius:3.5, spanGaps:false, tension:.3 });
  }

  simChart.data.labels = labels;
  simChart.data.datasets = datasets;
  simChart.update();

  const legend = document.getElementById('simLegend');
  legend.innerHTML = datasets.slice(0,10).map(d=>`<div class="leg-item"><div class="leg-dot" style="background:${d.borderColor}"></div>${d.label}</div>`).join('')+(n>10?`<div class="leg-item">+ ${n-10} mais</div>`:'');

  const finalActive = datasets.filter(d=>d.data[w-1]!==null).length;
  const lossRate = Math.round(totalLost/n*100);
  document.getElementById('simInsight').innerHTML = `<strong>Resultados da simulação:</strong> De <strong>${n} participantes</strong>, <strong>${totalLost} abandonaram</strong> o estudo (atrito total de ${lossRate}%). Apenas <strong>${finalActive} completaram todas as ${w} ondas</strong>. Isso exemplifica o desafio real do atrito amostral — quem abandona pode ser sistematicamente diferente de quem permanece, criando viés nos resultados.`;
}

// ── EXEMPLOS ──
const exData = [
  { name:'Framingham Heart Study', country:'EUA · 1948 – hoje', years:76, color:'#b83232', tag:'Cardiologia',
    desc:'O mais longevo estudo cardiovascular do mundo. Acompanha gerações de habitantes de Framingham/MA e revelou que colesterol elevado, hipertensão e tabagismo causam doenças cardíacas — base de toda a cardiologia preventiva moderna.' },
  { name:'Harvard Study of Adult Development', country:'EUA · 1938 – hoje', years:86, color:'#1a3a6b', tag:'Psicologia',
    desc:'Um dos estudos mais longos sobre felicidade e bem-estar humano. Acompanhou centenas de homens desde a adolescência. Conclusão central: a qualidade dos relacionamentos é o principal preditor de saúde e felicidade na velhice — não riqueza nem status.' },
  { name:'Estudo de Dunedin', country:'Nova Zelândia · 1972 – hoje', years:52, color:'#0d6e6e', tag:'Desenvolvimento',
    desc:'Acompanha mais de 1.000 pessoas nascidas em 1972-73 em Dunedin. Revelou como temperamento na infância prediz saúde mental adulta, trajetórias profissionais e bem-estar ao longo da vida.' },
  { name:'Coorte de Nascimentos de Pelotas', country:'Brasil · 1982 – hoje', years:42, color:'#7c3aed', tag:'Epidemiologia',
    desc:'Quatro coortes de bebês nascidos em Pelotas/RS, acompanhadas por décadas. Uma das pesquisas longitudinais mais respeitadas fora do eixo anglofônico. Estudou nutrição, cognição, saúde mental e mobilidade social ao longo da vida.' },
  { name:'ELSA-Brasil', country:'Brasil · 2008 – hoje', years:16, color:'#c17a1a', tag:'Saúde Pública',
    desc:'Estudo Longitudinal de Saúde do Adulto com 15.000 servidores públicos de 6 estados. Investiga fatores de risco para diabetes, hipertensão e doenças cardiovasculares considerando especificidades da população brasileira.' },
];

function initExamples() {
  const el = document.getElementById('exList');
  if(el.children.length>0){ setTimeout(animateBars,100); return; }
  el.innerHTML = exData.map((e,i)=>`
    <div class="ex-card" style="animation-delay:${i*60}ms">
      <div class="ex-top">
        <div class="ex-accent" style="background:${e.color}"></div>
        <div class="ex-body">
          <div class="ex-meta">
            <span class="ex-title">${e.name}</span>
            <span class="ex-tag" style="background:${e.color}18;color:${e.color}">${e.tag}</span>
          </div>
          <div class="ex-country">${e.country}</div>
          <div class="ex-desc">${e.desc}</div>
          <div class="ex-bar-wrap">
            <div class="ex-bar-bg"><div class="ex-bar-fill" style="background:${e.color}" data-w="${Math.round(e.years/86*100)}"></div></div>
            <div class="ex-years">${e.years} anos</div>
          </div>
        </div>
      </div>
    </div>`).join('');
  setTimeout(animateBars, 200);
}

function animateBars() {
  document.querySelectorAll('.ex-bar-fill').forEach(el => {
    el.style.width = el.dataset.w+'%';
  });
}
</script>
</body>
</html>
