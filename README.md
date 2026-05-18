<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>NovaCampus ERP — Wireframes</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Caveat:wght@500;700&family=Kalam:wght@300;400;700&family=Architects+Daughter&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --paper: #f6f1e4;
    --paper-2: #efe8d6;
    --ink: #2a2620;
    --ink-soft: #5a5247;
    --ink-faint: #a89e8a;
    --accent: oklch(0.66 0.16 55);     /* warm amber */
    --accent-2: oklch(0.55 0.13 200);  /* dusty teal */
    --rule: rgba(42,38,32,0.55);
    --rule-soft: rgba(42,38,32,0.28);
    --grid: rgba(42,38,32,0.07);
    --hand: "Kalam", "Patrick Hand", "Comic Sans MS", system-ui, sans-serif;
    --title: "Caveat", "Kalam", cursive;
    --note: "Architects Daughter", "Kalam", cursive;
    --mono: "JetBrains Mono", ui-monospace, monospace;
  }
  * { box-sizing: border-box; }
  html, body { margin: 0; padding: 0; }
  body {
    font-family: var(--hand);
    color: var(--ink);
    background:
      radial-gradient(1200px 800px at 20% -10%, rgba(255,255,255,0.6), transparent 60%),
      radial-gradient(900px 700px at 110% 110%, rgba(0,0,0,0.04), transparent 60%),
      repeating-linear-gradient(0deg, transparent 0 31px, rgba(42,38,32,0.06) 31px 32px),
      var(--paper);
    min-height: 100vh;
  }
  body.no-lines {
    background:
      radial-gradient(1200px 800px at 20% -10%, rgba(255,255,255,0.6), transparent 60%),
      radial-gradient(900px 700px at 110% 110%, rgba(0,0,0,0.04), transparent 60%),
      var(--paper);
  }
  body.no-annot .annot { display: none; }

  header.masthead {
    padding: 28px 40px 8px;
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 24px;
    border-bottom: 1px dashed var(--rule-soft);
  }
  .mast-title {
    font-family: var(--title);
    font-size: 56px;
    line-height: 0.95;
    margin: 0;
    letter-spacing: 0.5px;
  }
  .mast-sub {
    font-family: var(--note);
    color: var(--ink-soft);
    font-size: 18px;
    margin-top: 6px;
    max-width: 760px;
  }
  .mast-stamp {
    font-family: var(--note);
    font-size: 12px;
    color: var(--ink-soft);
    border: 1.5px dashed var(--rule);
    padding: 10px 14px;
    transform: rotate(2.5deg);
    background: rgba(255,255,255,0.4);
    text-align: center;
    min-width: 180px;
  }
  .mast-stamp b { font-size: 14px; display:block; color: var(--ink); font-family: var(--hand); }

  nav.tabs {
    display: flex;
    flex-wrap: wrap;
    gap: 4px;
    padding: 16px 36px 0;
    border-bottom: 2px solid var(--ink);
    position: sticky; top: 0; z-index: 10;
    background:
      linear-gradient(to bottom, var(--paper) 60%, rgba(246,241,228,0.85));
    backdrop-filter: blur(4px);
  }
  nav.tabs button {
    font-family: var(--hand);
    font-size: 18px;
    background: transparent;
    border: 2px solid var(--ink);
    border-bottom: none;
    color: var(--ink);
    padding: 8px 18px 10px;
    cursor: pointer;
    border-radius: 14px 14px 0 0;
    margin-right: 2px;
    transform: translateY(2px);
    transition: transform .15s, background .15s;
  }
  nav.tabs button:hover { background: rgba(255,255,255,0.4); }
  nav.tabs button.active {
    background: var(--paper);
    transform: translateY(2px);
    font-weight: 700;
    box-shadow: 0 -2px 0 var(--accent) inset;
  }
  nav.tabs .spacer { flex: 1; }
  nav.tabs .lot {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--ink-soft);
    align-self: center;
    padding-right: 4px;
  }
  nav.tabs .ltag {
    font-family: var(--mono);
    font-size: 9px;
    background: var(--ink);
    color: var(--paper);
    padding: 1px 4px;
    border-radius: 3px;
    margin-right: 6px;
    vertical-align: middle;
    letter-spacing: 0.5px;
  }
  nav.tabs button.active .ltag { background: var(--accent); }

  main { padding: 28px 40px 80px; }

  .tab-pane { display: none; }
  .tab-pane.active { display: block; }

  .pane-head {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 24px;
    margin-bottom: 14px;
  }
  .pane-head h2 {
    font-family: var(--title);
    font-size: 48px;
    margin: 0 0 4px;
  }
  .pane-head p {
    font-family: var(--note);
    margin: 0;
    color: var(--ink-soft);
    font-size: 16px;
    max-width: 720px;
  }
  .pane-head .legend {
    font-family: var(--note);
    font-size: 13px;
    color: var(--ink-soft);
    border-left: 2px dashed var(--rule-soft);
    padding: 6px 0 6px 14px;
    min-width: 220px;
  }
  .pane-head .legend b { color: var(--ink); font-family: var(--hand); }
  .legend .sw { display:inline-block; width:12px; height:12px; border:1.5px solid var(--ink); margin-right:6px; vertical-align:middle; }
  .legend .sw.acc { background: var(--accent); }
  .legend .sw.ai { background: repeating-linear-gradient(45deg, var(--accent) 0 4px, #fff 4px 8px); }

  .variants {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 22px;
  }
  @media (max-width: 1280px) { .variants { grid-template-columns: 1fr; } }

  .wf {
    position: relative;
    background: rgba(255,255,255,0.55);
    border: 2px solid var(--ink);
    border-radius: 6px;
    padding: 14px 14px 16px;
    box-shadow: 4px 5px 0 rgba(42,38,32,0.12);
  }
  .wf::before {
    /* paper tape */
    content: "";
    position: absolute;
    top: -14px; left: 20px;
    width: 70px; height: 22px;
    background: rgba(220, 200, 140, 0.55);
    border: 1px dashed rgba(0,0,0,0.15);
    transform: rotate(-3deg);
  }
  .wf .wf-tag {
    position: absolute;
    top: -10px; right: 12px;
    background: var(--paper);
    padding: 0 8px;
    font-family: var(--note);
    font-size: 12px;
    color: var(--ink-soft);
    border: 1.5px dashed var(--rule-soft);
  }
  .wf h3 {
    font-family: var(--title);
    font-size: 28px;
    margin: 2px 0 2px;
    line-height: 1;
  }
  .wf .wf-sub {
    font-family: var(--note);
    color: var(--ink-soft);
    font-size: 13px;
    margin-bottom: 10px;
    border-bottom: 1px dashed var(--rule-soft);
    padding-bottom: 8px;
  }
  .wf .pros {
    font-family: var(--note);
    font-size: 13px;
    color: var(--ink-soft);
    margin-top: 10px;
    border-top: 1px dashed var(--rule-soft);
    padding-top: 8px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
  }
  .pros b { color: var(--ink); font-family: var(--hand); font-size: 13px; }
  .pros .plus::before { content: "+ "; color: oklch(0.55 0.12 140); }
  .pros .minus::before { content: "− "; color: oklch(0.55 0.12 30); }

  /* sketchy primitives */
  .frame {
    border: 1.8px solid var(--ink);
    border-radius: 4px;
    background: rgba(255,255,255,0.5);
    position: relative;
  }
  .frame.dashed { border-style: dashed; }
  .frame.thin { border-width: 1.2px; }
  .frame.fill { background: rgba(42,38,32,0.06); }
  .frame.accent { border-color: var(--accent); }
  .frame.ai {
    border-color: var(--accent);
    background: repeating-linear-gradient(45deg, rgba(217, 119, 60, 0.10) 0 6px, transparent 6px 12px);
  }
  .lbl {
    font-family: var(--hand);
    font-size: 13px;
    color: var(--ink);
  }
  .lbl.sm { font-size: 11px; color: var(--ink-soft); }
  .lbl.mono { font-family: var(--mono); font-size: 10.5px; letter-spacing: 0; color: var(--ink-soft); }
  .lbl.big { font-family: var(--title); font-size: 22px; line-height: 1; }
  .lbl.h { font-family: var(--title); font-size: 18px; }
  .annot {
    font-family: var(--note);
    font-size: 12px;
    color: var(--accent);
    position: absolute;
  }
  .arrow-svg { position:absolute; overflow: visible; pointer-events: none; }

  /* generic stack helpers */
  .row { display: flex; gap: 8px; }
  .col { display: flex; flex-direction: column; gap: 8px; }
  .pad { padding: 8px; }
  .pad-sm { padding: 6px; }
  .grow { flex: 1; }

  /* skeletons */
  .skeleton-line { height: 8px; background: rgba(42,38,32,0.15); border-radius: 2px; }
  .skeleton-line.short { width: 40%; }
  .skeleton-line.mid { width: 65%; }
  .skeleton-line.full { width: 100%; }
  .skeleton-line.dark { background: rgba(42,38,32,0.3); }

  /* chip */
  .chip {
    display: inline-block;
    border: 1.5px solid var(--ink);
    border-radius: 999px;
    padding: 1px 8px;
    font-family: var(--hand);
    font-size: 11px;
    background: rgba(255,255,255,0.5);
  }
  .chip.acc { border-color: var(--accent); color: var(--accent); }
  .chip.fill { background: var(--ink); color: var(--paper); }

  /* SVG accents */
  .scribble { color: var(--ink); }
  .scribble.acc { color: var(--accent); }

  /* persona row */
  .personas {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 14px;
    margin: 18px 0 6px;
  }
  .persona {
    border: 1.6px solid var(--ink);
    border-radius: 6px;
    padding: 10px 12px;
    background: rgba(255,255,255,0.4);
  }
  .persona h4 { margin: 0; font-family: var(--title); font-size: 26px; line-height: 1; }
  .persona .needs { font-family: var(--note); font-size: 12.5px; color: var(--ink-soft); margin-top: 4px; }
  .persona .needs li { margin-bottom: 2px; }
  .persona ul { padding-left: 16px; margin: 6px 0 0; }

  footer.foot {
    margin-top: 32px;
    border-top: 1px dashed var(--rule-soft);
    padding-top: 10px;
    font-family: var(--note);
    font-size: 12px;
    color: var(--ink-soft);
    display: flex; justify-content: space-between;
  }

  /* Tweaks panel */
  #tweaks {
    position: fixed;
    right: 18px;
    bottom: 18px;
    width: 240px;
    background: var(--paper-2);
    border: 2px solid var(--ink);
    border-radius: 8px;
    padding: 12px 14px 14px;
    font-family: var(--hand);
    box-shadow: 4px 5px 0 rgba(42,38,32,0.18);
    z-index: 20;
    display: none;
  }
  #tweaks.open { display: block; }
  #tweaks h5 { margin: 0 0 8px; font-family: var(--title); font-size: 22px; line-height: 1; display:flex; justify-content:space-between; align-items:center; }
  #tweaks h5 button { all: unset; cursor: pointer; font-size: 18px; }
  #tweaks .group { margin-bottom: 10px; }
  #tweaks .group label { display:block; font-size: 12px; color: var(--ink-soft); margin-bottom: 4px; font-family: var(--note); }
  #tweaks .row-opts { display:flex; gap: 4px; flex-wrap: wrap; }
  #tweaks .row-opts button {
    font-family: var(--hand);
    font-size: 13px;
    background: rgba(255,255,255,0.5);
    border: 1.5px solid var(--ink);
    padding: 3px 8px;
    border-radius: 4px;
    cursor: pointer;
  }
  #tweaks .row-opts button.on { background: var(--accent); color: white; border-color: var(--accent); }
  #tweaks .swatches { display: flex; gap: 6px; }
  #tweaks .sw {
    width: 24px; height: 24px; border-radius: 50%;
    border: 1.5px solid var(--ink); cursor: pointer;
  }
  #tweaks .sw.on { box-shadow: 0 0 0 2px var(--paper-2), 0 0 0 4px var(--ink); }

  /* arrow */
  svg.arrow path { stroke: var(--ink); stroke-width: 1.6; fill: none; stroke-linecap: round; }
  svg.arrow.acc path { stroke: var(--accent); stroke-width: 1.8; }

  /* utility small */
  .grid-2 { display:grid; grid-template-columns: 1fr 1fr; gap: 8px; }
  .grid-3 { display:grid; grid-template-columns: repeat(3, 1fr); gap: 8px; }
  .grid-4 { display:grid; grid-template-columns: repeat(4, 1fr); gap: 8px; }

  .tile {
    border: 1.6px solid var(--ink);
    border-radius: 4px;
    padding: 6px 8px;
    background: rgba(255,255,255,0.5);
    min-height: 44px;
    position: relative;
  }
  .tile.dashed { border-style: dashed; }
  .tile.fill { background: rgba(42,38,32,0.06); }
  .tile.ai { border-color: var(--accent); background: repeating-linear-gradient(45deg, rgba(217, 119, 60, 0.10) 0 6px, transparent 6px 12px); }

  .kpi {
    border: 1.6px solid var(--ink); border-radius: 4px;
    padding: 8px; background: rgba(255,255,255,0.5);
    display:flex; flex-direction: column; gap: 2px;
  }
  .kpi .v { font-family: var(--title); font-size: 28px; line-height: 1; }
  .kpi .k { font-family: var(--note); font-size: 11px; color: var(--ink-soft); }

  .sidebar {
    border: 1.6px solid var(--ink); border-radius: 4px;
    padding: 8px; background: rgba(42,38,32,0.05);
    display: flex; flex-direction: column; gap: 6px; min-width: 110px;
  }
  .sidebar .item { font-family: var(--hand); font-size: 13px; padding: 3px 4px; border-radius: 3px; }
  .sidebar .item.on { background: var(--ink); color: var(--paper); }

  .topbar {
    height: 28px; border: 1.4px solid var(--ink); border-radius: 3px;
    display: flex; align-items: center; padding: 0 8px; gap: 6px;
    background: rgba(255,255,255,0.6);
  }
  .topbar .crumbs { font-family: var(--hand); font-size: 12px; }
  .topbar .right { margin-left: auto; display: flex; gap: 6px; align-items: center; }
  .topbar .pill { width: 18px; height: 18px; border:1.4px solid var(--ink); border-radius: 50%; background: rgba(255,255,255,0.5); }

  /* timetable grid */
  .ttgrid {
    display: grid;
    grid-template-columns: 30px repeat(5, 1fr);
    gap: 3px;
    font-size: 9px;
    font-family: var(--mono);
  }
  .ttgrid > div {
    border: 1.2px solid var(--ink);
    min-height: 18px;
    padding: 2px 3px;
    background: rgba(255,255,255,0.5);
    border-radius: 2px;
  }
  .ttgrid .head { background: rgba(42,38,32,0.08); text-align: center; }
  .ttgrid .blk { background: rgba(42,38,32,0.18); }
  .ttgrid .acc { background: rgba(217,119,60,0.25); border-color: var(--accent); }
  .ttgrid .ai { background: repeating-linear-gradient(45deg, rgba(217,119,60,0.18) 0 4px, transparent 4px 8px); border-color: var(--accent); }
  .ttgrid .empty { background: transparent; border: none; }

  /* chat */
  .bubble {
    border: 1.4px solid var(--ink); border-radius: 8px;
    padding: 5px 8px; font-family: var(--hand); font-size: 12px;
    background: rgba(255,255,255,0.6); max-width: 90%;
  }
  .bubble.me { background: var(--ink); color: var(--paper); align-self: flex-end; border-color: var(--ink); }
  .bubble.ai { border-color: var(--accent); background: rgba(217,119,60,0.12); }

  .stickers {
    position: absolute; top: -14px; right: 60px;
    transform: rotate(-4deg);
    font-family: var(--note); font-size: 11px;
    background: oklch(0.92 0.10 95);
    border: 1px dashed rgba(0,0,0,0.25);
    padding: 2px 8px;
  }
</style>
</head>
<body>

<header class="masthead">
  <div>
    <h1 class="mast-title">NovaCampus ERP — lo-fi wireframes</h1>
    <div class="mast-sub">Exploration sketches for Deliverable 5 (UX/UI) + supporting diagrams for Deliverable 1 (Business Analysis). Four roles, three layout directions each, plus an AI-agent placement study.</div>
  </div>
  <div class="mast-stamp">
    <b>DRAFT v0.1</b>
    Shaping Tomorrow's Minds<br>
    Internal — review only
  </div>
</header>

<nav class="tabs" id="tabs">
  <button data-tab="context" class="active"><span class="ltag">L1</span> Context</button>
  <button data-tab="backlog"><span class="ltag">L2</span> Backlog</button>
  <button data-tab="arch"><span class="ltag">L3</span> Architecture</button>
  <button data-tab="tech"><span class="ltag">L5</span> Tech</button>
  <button data-tab="foundations"><span class="ltag">L6</span> Foundations</button>
  <button data-tab="student"><span class="ltag">L6</span> Student</button>
  <button data-tab="teacher"><span class="ltag">L6</span> Teacher</button>
  <button data-tab="admin"><span class="ltag">L6</span> Admin</button>
  <button data-tab="mgmt"><span class="ltag">L6</span> Mgmt</button>
  <button data-tab="ai"><span class="ltag">L6</span> AI</button>
  <button data-tab="decisions"><span class="ltag">L7</span> Decisions</button>
  <button data-tab="security"><span class="ltag">L8</span> Security</button>
  <button data-tab="story"><span class="ltag">★</span> Story</button>
  <button data-tab="pitch"><span class="ltag">L9</span> Pitch</button>
  <div class="spacer"></div>
  <button id="open-tweaks" style="border-style:dashed">⚙ Tweaks</button>
</nav>

<main id="main">

<!-- ============ CONTEXT ============ -->
<section class="tab-pane active" data-pane="context">
  <div class="pane-head">
    <div>
      <h2>Context · stakeholders · system boundary</h2>
      <p>Four roles, four campuses, one fragmented toolchain today. These sketches frame <i>who</i> we're designing for and <i>what</i> the ERP must cover before the screens get specific.</p>
    </div>
    <div class="legend">
      <b>Legend</b><br>
      <span class="sw"></span> standard element<br>
      <span class="sw acc"></span> accent / primary action<br>
      <span class="sw ai"></span> AI agent surface
    </div>
  </div>

  <div class="personas">
    <div class="persona">
      <h4>Student</h4>
      <ul class="needs">
        <li>timetable + changes</li>
        <li>grades, absences</li>
        <li>academic history</li>
        <li>push notifications</li>
      </ul>
    </div>
    <div class="persona">
      <h4>Teacher</h4>
      <ul class="needs">
        <li>create / manage courses</li>
        <li>enter grades + absences</li>
        <li>book rooms / resources</li>
        <li>class history</li>
      </ul>
    </div>
    <div class="persona">
      <h4>Admin</h4>
      <ul class="needs">
        <li>registrations + files</li>
        <li>payments + reminders</li>
        <li>room / schedule conflicts</li>
        <li>operational dashboards</li>
      </ul>
    </div>
    <div class="persona">
      <h4>Management</h4>
      <ul class="needs">
        <li>multi-campus KPIs</li>
        <li>success / occupancy / revenue</li>
        <li>planning + analysis</li>
        <li>strategic reports</li>
      </ul>
    </div>
  </div>

  <div class="variants">
    <!-- v1 system context diagram -->
    <div class="wf">
      <div class="wf-tag">v1 · system context</div>
      <h3>"The black box"</h3>
      <div class="wf-sub">Actors around the ERP, external systems on the right. Classic Level-0.</div>
      <svg viewBox="0 0 420 280" style="width:100%; height:auto;">
        <defs>
          <marker id="ar" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
            <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
          </marker>
        </defs>
        <!-- central system -->
        <rect x="140" y="100" width="140" height="80" rx="8" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="2"/>
        <text x="210" y="135" text-anchor="middle" font-family="Caveat" font-size="22" fill="#2a2620">NovaCampus ERP</text>
        <text x="210" y="158" text-anchor="middle" font-family="Architects Daughter" font-size="11" fill="#5a5247">multi-campus core</text>
        <!-- actors -->
        <g font-family="Kalam" font-size="12" fill="#2a2620">
          <circle cx="40" cy="50" r="16" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="40" y="86" text-anchor="middle">Student</text>
          <circle cx="40" cy="140" r="16" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="40" y="176" text-anchor="middle">Teacher</text>
          <circle cx="40" cy="230" r="16" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="40" y="266" text-anchor="middle">Admin</text>
          <circle cx="210" cy="40" r="16" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="210" y="22" text-anchor="middle">Management</text>
        </g>
        <!-- externals -->
        <g font-family="Kalam" font-size="11" fill="#5a5247">
          <rect x="330" y="40" width="80" height="38" stroke="#2a2620" stroke-dasharray="4 3" fill="none"/>
          <text x="370" y="62" text-anchor="middle">Payment GW</text>
          <rect x="330" y="120" width="80" height="38" stroke="#2a2620" stroke-dasharray="4 3" fill="none"/>
          <text x="370" y="142" text-anchor="middle">Email / SMS</text>
          <rect x="330" y="200" width="80" height="38" stroke="#2a2620" stroke-dasharray="4 3" fill="none"/>
          <text x="370" y="222" text-anchor="middle">Identity SSO</text>
        </g>
        <!-- AI -->
        <g>
          <rect x="160" y="220" width="100" height="38" rx="6" stroke="#D9773C" stroke-width="2" fill="rgba(217,119,60,0.12)"/>
          <text x="210" y="245" text-anchor="middle" font-family="Kalam" font-size="13" fill="#D9773C">AI Agent ✦</text>
        </g>
        <!-- arrows -->
        <g stroke="#2a2620" stroke-width="1.4" fill="none" marker-end="url(#ar)">
          <path d="M56,50 C100,60 110,110 140,120"/>
          <path d="M56,140 L140,140"/>
          <path d="M56,230 C100,210 110,180 140,170"/>
          <path d="M210,56 L210,100"/>
          <path d="M280,120 L330,60"/>
          <path d="M280,140 L330,140"/>
          <path d="M280,160 L330,220"/>
          <path d="M210,180 L210,220" stroke="#D9773C"/>
        </g>
      </svg>
      <div class="pros">
        <span class="plus">classic, easy to defend</span>
        <span class="minus">flat — no campus dimension</span>
      </div>
    </div>

    <!-- v2 process map: enrollment -->
    <div class="wf">
      <div class="wf-tag">v2 · process map</div>
      <h3>"Enrollment → grade" swimlanes</h3>
      <div class="wf-sub">Cross-role process from application to transcript. Shows where AI shortens loops.</div>
      <svg viewBox="0 0 420 280" style="width:100%; height:auto; font-family: Kalam, sans-serif;">
        <!-- lanes -->
        <g font-size="10" fill="#5a5247">
          <line x1="80" y1="20" x2="80" y2="270" stroke="#2a2620" stroke-dasharray="3 3"/>
          <text x="40" y="55" text-anchor="middle">Student</text>
          <text x="40" y="115" text-anchor="middle">Admin</text>
          <text x="40" y="175" text-anchor="middle">Teacher</text>
          <text x="40" y="235" text-anchor="middle">Mgmt</text>
          <line x1="80" y1="80" x2="420" y2="80" stroke="#2a2620" stroke-dasharray="3 3"/>
          <line x1="80" y1="140" x2="420" y2="140" stroke="#2a2620" stroke-dasharray="3 3"/>
          <line x1="80" y1="200" x2="420" y2="200" stroke="#2a2620" stroke-dasharray="3 3"/>
        </g>
        <!-- steps -->
        <g font-family="Kalam" font-size="11" fill="#2a2620">
          <rect x="95" y="38" width="60" height="30" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="125" y="58" text-anchor="middle">apply</text>
          <rect x="170" y="98" width="60" height="30" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="200" y="118" text-anchor="middle">enroll</text>
          <rect x="170" y="158" width="60" height="30" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="200" y="178" text-anchor="middle">teach</text>
          <rect x="245" y="158" width="60" height="30" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="275" y="178" text-anchor="middle">grade</text>
          <rect x="245" y="98" width="60" height="30" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="275" y="118" text-anchor="middle">invoice</text>
          <rect x="320" y="38" width="60" height="30" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="350" y="58" text-anchor="middle">transcript</text>
          <rect x="320" y="218" width="60" height="30" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="350" y="238" text-anchor="middle">KPI report</text>
        </g>
        <!-- ai overlay -->
        <g stroke="#D9773C" fill="none">
          <rect x="155" y="92" width="155" height="42" stroke-dasharray="5 4" stroke-width="1.6"/>
          <text x="232" y="86" text-anchor="middle" font-family="Architects Daughter" font-size="11" fill="#D9773C">AI: dunning + room reshuffle</text>
        </g>
        <!-- arrows -->
        <g stroke="#2a2620" stroke-width="1.3" fill="none" marker-end="url(#ar)">
          <path d="M155,53 C190,53 180,98 200,98"/>
          <path d="M230,113 L245,113"/>
          <path d="M200,128 L200,158"/>
          <path d="M230,173 L245,173"/>
          <path d="M275,158 L275,128"/>
          <path d="M305,113 C330,113 330,68 320,53"/>
          <path d="M275,188 C275,210 320,220 320,233"/>
        </g>
      </svg>
      <div class="pros">
        <span class="plus">shows hand-offs + AI value</span>
        <span class="minus">denser, needs walkthrough</span>
      </div>
    </div>

    <!-- v3 campus map / topology -->
    <div class="wf">
      <div class="wf-tag">v3 · multi-campus</div>
      <h3>"4 campuses, one core"</h3>
      <div class="wf-sub">Spatial framing — answers the audit pain point about consolidated indicators.</div>
      <svg viewBox="0 0 420 280" style="width:100%; height:auto;">
        <!-- core -->
        <circle cx="210" cy="140" r="44" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="2"/>
        <text x="210" y="135" text-anchor="middle" font-family="Caveat" font-size="20" fill="#2a2620">Core ERP</text>
        <text x="210" y="155" text-anchor="middle" font-family="Architects Daughter" font-size="10" fill="#5a5247">single source</text>

        <!-- campuses -->
        <g font-family="Kalam" font-size="12" fill="#2a2620">
          <g transform="translate(60,50)">
            <rect width="80" height="50" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
            <text x="40" y="22" text-anchor="middle">Campus A</text>
            <text x="40" y="38" text-anchor="middle" font-size="10" fill="#5a5247">820 students</text>
          </g>
          <g transform="translate(280,50)">
            <rect width="80" height="50" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
            <text x="40" y="22" text-anchor="middle">Campus B</text>
            <text x="40" y="38" text-anchor="middle" font-size="10" fill="#5a5247">1,140 students</text>
          </g>
          <g transform="translate(60,180)">
            <rect width="80" height="50" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
            <text x="40" y="22" text-anchor="middle">Campus C</text>
            <text x="40" y="38" text-anchor="middle" font-size="10" fill="#5a5247">605 students</text>
          </g>
          <g transform="translate(280,180)">
            <rect width="80" height="50" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
            <text x="40" y="22" text-anchor="middle">Campus D</text>
            <text x="40" y="38" text-anchor="middle" font-size="10" fill="#5a5247">new · 210</text>
          </g>
        </g>
        <!-- links -->
        <g stroke="#2a2620" stroke-width="1.4" fill="none" marker-end="url(#ar)">
          <path d="M140,75 C170,90 180,115 175,125"/>
          <path d="M280,75 C250,90 240,115 245,125"/>
          <path d="M140,205 C170,190 180,170 175,160"/>
          <path d="M280,205 C250,190 240,170 245,160"/>
        </g>
        <!-- AI ribbon -->
        <g>
          <path d="M30,140 C70,120 120,160 165,140" stroke="#D9773C" fill="none" stroke-width="1.8" stroke-dasharray="4 4"/>
          <text x="30" y="130" font-family="Architects Daughter" font-size="10" fill="#D9773C">AI cross-campus suggestions ↗</text>
        </g>
      </svg>
      <div class="pros">
        <span class="plus">directly answers audit pain</span>
        <span class="minus">hides external systems</span>
      </div>
    </div>
  </div>

  <!-- Problem vs Solution -->
  <div class="lbl h" style="margin-top:22px;">④ Problem statement → Solution statement</div>
  <div class="grid-2" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl sm" style="color:var(--ink-soft)">PROBLEM</div>
      <div class="lbl h" style="margin-top:4px;">Four schools, not one alliance.</div>
      <div class="lbl" style="margin-top:6px; line-height:1.5;">
        NovaCampus doubled in 6 years across <b>4 campuses</b> but never redesigned its IS.
        Tools don't talk; rooms clash; reminders are manual; the recent audit could not produce
        consolidated success indicators. <i>"Craft-based, not systemic."</i>
      </div>
      <div class="lbl sm" style="margin-top:8px; color:var(--ink-soft);">Impact</div>
      <ul class="lbl sm" style="margin:4px 0 0; padding-left:16px;">
        <li>days lost re-keying data between tools</li>
        <li>students miss class on unofficial room changes</li>
        <li>~€18k overdue at any given month (semi-manual dunning)</li>
        <li>strategic reports impossible without manual consolidation</li>
      </ul>
    </div>
    <div class="frame pad accent" style="padding:12px; border-color: var(--accent);">
      <div class="lbl sm" style="color:var(--accent)">SOLUTION</div>
      <div class="lbl h" style="margin-top:4px;">One ERP, four campuses, one AI loop.</div>
      <div class="lbl" style="margin-top:6px; line-height:1.5;">
        A single, role-based academic ERP that <b>centralises multi-campus operations</b>,
        digitises core processes (registration → grading → invoicing), produces
        <b>reliable indicators</b>, and embeds an <b>AI agent</b> on the highest-pain loop.
      </div>
      <div class="lbl sm" style="margin-top:8px; color:var(--ink-soft);">Success looks like</div>
      <ul class="lbl sm" style="margin:4px 0 0; padding-left:16px;">
        <li>room conflicts/month ↓ &gt;70%</li>
        <li>days-late on invoices ↓ &gt;50%</li>
        <li>audit-cycle prep ↓ from weeks → hours</li>
        <li>1 AI win the board can point to</li>
      </ul>
    </div>
  </div>

  <!-- Stakeholder register -->
  <div class="lbl h" style="margin-top:22px;">⑤ Stakeholder register</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 130px 90px 90px 1fr 1fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Stakeholder</div>
      <div class="lbl sm" style="font-weight:700;">Role</div>
      <div class="lbl sm" style="font-weight:700;">Type</div>
      <div class="lbl sm" style="font-weight:700;">Main need</div>
      <div class="lbl sm" style="font-weight:700;">Pain today</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Students (~2.8k)</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">end user</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">timetable, grades, history</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">"is the room change real?"</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Teachers / Lecturers</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">end user</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">grade entry, room booking</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">grading takes hours · paper</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Educational manager</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">power user</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">enrolments, conflicts, $</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">semi-manual reminders</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Head of Education</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">decision</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">coordination across campuses</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">"4 independent schools"</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">CEO / Board</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">sponsor</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">strategic KPIs, growth</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">no consolidated reporting</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Auditors</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">regulator</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">external</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">traceable indicators</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">had to estimate at last audit</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">IT / Ops team</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">delivery</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">maintainable, observable</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">tool sprawl, no SSO</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Parents / Sponsors</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">payer</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">external</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">visibility on payment + progress</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">phone calls for receipts</span></div>
    </div>
  </div>

  <!-- Power / Interest matrix -->
  <div class="lbl h" style="margin-top:22px;">⑥ Stakeholder classification · power × interest</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 600 360" style="width:100%; height:auto;">
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <!-- axes -->
        <line x1="60" y1="40" x2="60" y2="320" stroke="#2a2620" stroke-width="1.5"/>
        <line x1="60" y1="320" x2="560" y2="320" stroke="#2a2620" stroke-width="1.5"/>
        <text x="30" y="180" text-anchor="middle" transform="rotate(-90 30 180)" font-family="Caveat" font-size="18">Power →</text>
        <text x="300" y="350" text-anchor="middle" font-family="Caveat" font-size="18">Interest →</text>

        <!-- quadrants -->
        <line x1="310" y1="40" x2="310" y2="320" stroke="#5a5247" stroke-dasharray="4 4" stroke-width="1"/>
        <line x1="60" y1="180" x2="560" y2="180" stroke="#5a5247" stroke-dasharray="4 4" stroke-width="1"/>
        <text x="180" y="60" text-anchor="middle" font-family="Architects Daughter" font-size="11" fill="#5a5247">KEEP SATISFIED</text>
        <text x="430" y="60" text-anchor="middle" font-family="Architects Daughter" font-size="11" fill="#D9773C">MANAGE CLOSELY</text>
        <text x="180" y="300" text-anchor="middle" font-family="Architects Daughter" font-size="11" fill="#5a5247">MONITOR</text>
        <text x="430" y="300" text-anchor="middle" font-family="Architects Daughter" font-size="11" fill="#5a5247">KEEP INFORMED</text>

        <!-- dots -->
        <g>
          <circle cx="430" cy="100" r="8" fill="#D9773C" stroke="#2a2620"/><text x="445" y="104">CEO / Board</text>
          <circle cx="380" cy="130" r="8" fill="#D9773C" stroke="#2a2620"/><text x="395" y="134">Head of Education</text>
          <circle cx="350" cy="170" r="8" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="365" y="174">Educational manager</text>
          <circle cx="180" cy="120" r="8" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="195" y="124">Auditors</text>
          <circle cx="200" cy="160" r="8" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="215" y="164">IT / Ops</text>
          <circle cx="440" cy="230" r="8" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="455" y="234">Students</text>
          <circle cx="400" cy="260" r="8" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="415" y="264">Teachers</text>
          <circle cx="200" cy="270" r="8" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="215" y="274">Parents</text>
        </g>
      </g>
    </svg>
  </div>

  <!-- Requirements -->
  <div class="lbl h" style="margin-top:22px;">⑦ Requirements list</div>
  <div class="grid-2" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Functional (FR)</div>
      <div class="col" style="gap:3px; margin-top:6px;">
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-01</b> · authenticate users via SSO (OIDC)</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-02</b> · scope every record by campusId</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-03</b> · enrol / unenrol students per program</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-04</b> · publish &amp; modify class schedules</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-05</b> · detect room/teacher/cohort conflicts</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-06</b> · record attendance per session</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-07</b> · enter, draft, publish grades</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-08</b> · generate transcripts (PDF)</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-09</b> · issue invoices &amp; track payments</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-10</b> · push/email/SMS notifications</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>FR-11</b> · cross-campus KPI dashboards</span></div>
        <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm"><b>FR-12</b> ✦ AI proposes resolutions &amp; drafts</span></div>
      </div>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Non-functional (NFR)</div>
      <div class="col" style="gap:3px; margin-top:6px;">
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-perf</b> · page p95 &lt; 1.5s · push &lt; 60s</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-scal</b> · support 10k concurrent · 4 → 8 campuses</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-avail</b> · 99.5% during academic hours</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-sec</b> · JWT · RBAC · row-level isolation</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-privacy</b> · GDPR · student data minimisation</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-audit</b> · every write traced · 7-year retention</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-a11y</b> · WCAG 2.1 AA</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-i18n</b> · FR / EN / AR-RTL</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-maint</b> · &lt; 30 min to roll back a service</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-portable</b> · containerised · no vendor lock</span></div>
        <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm"><b>NFR-ai</b> ✦ human-in-the-loop on every committing action</span></div>
      </div>
    </div>
  </div>

  <!-- Business objectives / KPIs -->
  <div class="lbl h" style="margin-top:22px;">⑧ Business objectives · measurable targets</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="kpi"><div class="v">−80%</div><div class="k">room conflicts / month</div></div>
    <div class="kpi"><div class="v">−60%</div><div class="k">billing delays</div></div>
    <div class="kpi"><div class="v">100%</div><div class="k">campuses unified</div></div>
    <div class="kpi"><div class="v">&lt;60s</div><div class="k">notification latency</div></div>
    <div class="kpi"><div class="v">100%</div><div class="k">KPIs auto-consolidated</div></div>
    <div class="kpi"><div class="v">−90%</div><div class="k">audit prep time</div></div>
  </div>

  <!-- Constraints & assumptions -->
  <div class="lbl h" style="margin-top:22px;">⑨ Constraints &amp; assumptions</div>
  <div class="grid-2" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Constraints</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>GDPR &amp; local privacy regulations</li>
        <li>Multi-campus data synchronization</li>
        <li>Budget &amp; timeline (academic year cadence)</li>
        <li>Internet dependency · rural connectivity</li>
        <li>Must integrate with existing payment gateway</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Assumptions</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>Users have institutional accounts (SSO/OIDC)</li>
        <li>Campuses share the same academic rules</li>
        <li>Existing data can be migrated (Excel / legacy)</li>
        <li>Wi-Fi available on campus premises</li>
        <li>Mobile-first behaviour for students</li>
      </ul>
    </div>
  </div>

  <!-- Risks -->
  <div class="lbl h" style="margin-top:22px;">⑩ Risk register</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 1.5fr 70px 70px 2fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Risk</div>
      <div class="lbl sm" style="font-weight:700;">Likelihood</div>
      <div class="lbl sm" style="font-weight:700;">Impact</div>
      <div class="lbl sm" style="font-weight:700;">Mitigation</div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI gives bad recommendation ✦</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Human-in-the-loop · tools enforce rules · audit log</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Service downtime</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Redundant pods · multi-AZ DB · health checks</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Data inconsistency across services</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Validation rules · outbox pattern · idempotency keys</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Cross-campus data leak (RLS misconfig)</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Low</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">CI tests for RLS · scope claims in JWT · pen-test</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">User adoption resistance</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Training · phased rollout · feedback loops</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Migration data loss</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Low</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Dry-runs · staged migration · rollback plan</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Vendor lock-in (LLM provider)</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Adapter layer · swappable model interface</span></div>
    </div>
  </div>

  <!-- Current state → Future state -->
  <div class="lbl h" style="margin-top:22px;">⑪ Current state → Future state (as-is / to-be)</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 1fr 1fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700; color:#5a5247;">CURRENT (as-is)</div>
      <div class="lbl sm" style="font-weight:700; color:var(--accent);">FUTURE (to-be)</div>

      <div class="tile fill" style="padding:6px 8px;"><span class="lbl sm">Excel / paper records, kept per-campus</span></div>
      <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Centralised ERP, single source of truth</span></div>

      <div class="tile fill" style="padding:6px 8px;"><span class="lbl sm">Grades published days late, via printout</span></div>
      <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Real-time updates, mobile push</span></div>

      <div class="tile fill" style="padding:6px 8px;"><span class="lbl sm">Four campuses operating in isolation</span></div>
      <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Unified system, cross-campus KPIs</span></div>

      <div class="tile fill" style="padding:6px 8px;"><span class="lbl sm">Room conflicts found <i>after</i> they happen</span></div>
      <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">AI-detected before publication ✦</span></div>

      <div class="tile fill" style="padding:6px 8px;"><span class="lbl sm">Payment reminders done by phone</span></div>
      <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Automated dunning, AI-drafted ✦</span></div>

      <div class="tile fill" style="padding:6px 8px;"><span class="lbl sm">Audit prep = weeks of consolidation</span></div>
      <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Audit-ready dashboard in real time</span></div>

      <div class="tile fill" style="padding:6px 8px;"><span class="lbl sm">No central identity — N passwords per user</span></div>
      <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">SSO · one identity · scoped roles</span></div>
    </div>
  </div>
</section>

<!-- ============ LOT 6 · FOUNDATIONS ============ -->
<section class="tab-pane" data-pane="foundations">
  <div class="pane-head">
    <div>
      <h2>UX foundations · principles &amp; navigation</h2>
      <p>Before screens — the rules every dashboard must obey, and the information architecture that ties them all together.</p>
    </div>
    <div class="legend"><b>Tools</b><br>UX principles: simplicity · consistency · accessibility<br>navigation structure (IA)</div>
  </div>

  <!-- Principles -->
  <div class="lbl h">① UX principles</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Simplicity</div>
      <div class="lbl sm" style="margin-top:6px;">One primary action per screen. Show what users need <i>now</i>, hide the rest behind nav.</div>
      <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">In practice</div>
      <ul class="lbl sm" style="margin:4px 0 0; padding-left:16px;">
        <li>student home = "what now?" — one card at the top</li>
        <li>teacher → max 2 clicks to attendance or grading</li>
        <li>no module that doesn't answer a real job-to-be-done</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Consistency</div>
      <div class="lbl sm" style="margin-top:6px;">Same component, same behaviour everywhere. One visual language across 4 roles.</div>
      <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">In practice</div>
      <ul class="lbl sm" style="margin:4px 0 0; padding-left:16px;">
        <li>shared design tokens (color, type, spacing)</li>
        <li>amber-hatched chip = AI surface · always</li>
        <li>top-bar pattern identical across roles</li>
        <li>destructive action = confirmation modal · always</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Accessibility</div>
      <div class="lbl sm" style="margin-top:6px;">A student with low vision, a teacher on a slow rural connection, an admin using a keyboard — all first-class.</div>
      <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">In practice</div>
      <ul class="lbl sm" style="margin:4px 0 0; padding-left:16px;">
        <li>WCAG 2.1 AA contrast everywhere</li>
        <li>full keyboard navigation · visible focus</li>
        <li>aria roles on dashboards &amp; tables</li>
        <li>RTL ready for Arabic · text scales 200%</li>
        <li>works on 3G &amp; older Android</li>
      </ul>
    </div>
  </div>

  <!-- Sitemap / IA -->
  <div class="lbl h" style="margin-top:18px;">② Navigation structure · information architecture</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 1000 380" style="width:100%; height:auto;">
      <defs>
        <marker id="aia" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="12" fill="#2a2620">
        <!-- root -->
        <rect x="430" y="20" width="140" height="40" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="500" y="44" text-anchor="middle" font-family="Caveat" font-size="20" fill="#D9773C">NovaCampus</text>

        <!-- 4 roles -->
        <g>
          <rect x="60" y="100" width="170" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="145" y="124" text-anchor="middle" font-family="Caveat" font-size="18">Student</text>
          <rect x="290" y="100" width="170" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="375" y="124" text-anchor="middle" font-family="Caveat" font-size="18">Teacher</text>
          <rect x="540" y="100" width="170" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="625" y="124" text-anchor="middle" font-family="Caveat" font-size="18">Admin</text>
          <rect x="770" y="100" width="170" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="855" y="124" text-anchor="middle" font-family="Caveat" font-size="18">Management</text>
        </g>

        <!-- student children -->
        <g font-size="11">
          <rect x="40" y="180" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="80" y="197" text-anchor="middle">Home</text>
          <rect x="125" y="180" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="165" y="197" text-anchor="middle">Schedule</text>
          <rect x="40" y="215" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="80" y="232" text-anchor="middle">Grades</text>
          <rect x="125" y="215" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="165" y="232" text-anchor="middle">Absences</text>
          <rect x="40" y="250" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="80" y="267" text-anchor="middle">Profile</text>
          <rect x="125" y="250" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="165" y="267" text-anchor="middle">Messages</text>
        </g>

        <!-- teacher children -->
        <g font-size="11">
          <rect x="280" y="180" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="320" y="197" text-anchor="middle">Today</text>
          <rect x="365" y="180" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="405" y="197" text-anchor="middle">Classes</text>
          <rect x="280" y="215" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="320" y="232" text-anchor="middle">Grading</text>
          <rect x="365" y="215" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="405" y="232" text-anchor="middle">Attendance</text>
          <rect x="280" y="250" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="320" y="267" text-anchor="middle">Rooms</text>
          <rect x="365" y="250" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="405" y="267" text-anchor="middle">Resources</text>
        </g>

        <!-- admin children -->
        <g font-size="11">
          <rect x="530" y="180" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="570" y="197" text-anchor="middle">Inbox</text>
          <rect x="615" y="180" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="655" y="197" text-anchor="middle">Enrolments</text>
          <rect x="530" y="215" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="570" y="232" text-anchor="middle">Payments</text>
          <rect x="615" y="215" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="655" y="232" text-anchor="middle">Rooms</text>
          <rect x="530" y="250" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="570" y="267" text-anchor="middle">Schedule</text>
          <rect x="615" y="250" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="655" y="267" text-anchor="middle">Files</text>
        </g>

        <!-- mgmt children -->
        <g font-size="11">
          <rect x="760" y="180" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="800" y="197" text-anchor="middle">KPIs</text>
          <rect x="845" y="180" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="885" y="197" text-anchor="middle">Compare</text>
          <rect x="760" y="215" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="800" y="232" text-anchor="middle">Reports</text>
          <rect x="845" y="215" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="885" y="232" text-anchor="middle">Planning</text>
          <rect x="760" y="250" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="800" y="267" text-anchor="middle">Finance</text>
          <rect x="845" y="250" width="80" height="26" stroke="#2a2620" fill="rgba(255,255,255,0.5)"/><text x="885" y="267" text-anchor="middle">Audit</text>
        </g>

        <!-- shared bottom -->
        <rect x="320" y="320" width="160" height="34" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="400" y="342" text-anchor="middle" font-family="Caveat" font-size="16" fill="#D9773C">✦ AI assistant</text>
        <text x="400" y="370" text-anchor="middle" font-size="10" fill="#5a5247">global · contextual to current role</text>

        <rect x="510" y="320" width="160" height="34" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
        <text x="590" y="342" text-anchor="middle" font-family="Caveat" font-size="16">Settings &amp; profile</text>
        <text x="590" y="370" text-anchor="middle" font-size="10" fill="#5a5247">shared across roles</text>

        <!-- arrows -->
        <g stroke="#2a2620" stroke-width="1.2" fill="none" marker-end="url(#aia)">
          <line x1="450" y1="60" x2="145" y2="100"/>
          <line x1="480" y1="60" x2="375" y2="100"/>
          <line x1="520" y1="60" x2="625" y2="100"/>
          <line x1="550" y1="60" x2="855" y2="100"/>

          <line x1="145" y1="140" x2="145" y2="175"/>
          <line x1="375" y1="140" x2="375" y2="175"/>
          <line x1="625" y1="140" x2="625" y2="175"/>
          <line x1="855" y1="140" x2="855" y2="175"/>
        </g>
        <g stroke="#D9773C" stroke-width="1.3" stroke-dasharray="3 3" fill="none">
          <line x1="145" y1="280" x2="320" y2="335"/>
          <line x1="375" y1="280" x2="380" y2="320"/>
          <line x1="625" y1="280" x2="430" y2="320"/>
          <line x1="855" y1="280" x2="475" y2="335"/>
        </g>
      </g>
    </svg>
    <div class="lbl sm" style="margin-top:6px; color: var(--ink-soft);">3 levels deep, max. The AI assistant is available from every role (orange dashed) but always inherits role-scope.</div>
  </div>

  <!-- Component vocabulary -->
  <div class="lbl h" style="margin-top:18px;">③ Shared component vocabulary</div>
  <div class="grid-4" style="margin-top:6px;">
    <div class="frame pad" style="padding:8px;">
      <div class="lbl sm" style="color:var(--ink-soft)">topbar</div>
      <div class="topbar" style="margin-top:6px;"><span class="crumbs">crumbs ›</span><div class="right"><span class="pill"></span></div></div>
    </div>
    <div class="frame pad" style="padding:8px;">
      <div class="lbl sm" style="color:var(--ink-soft)">KPI tile</div>
      <div class="kpi" style="margin-top:6px;"><div class="v">87%</div><div class="k">pass rate</div></div>
    </div>
    <div class="frame pad" style="padding:8px;">
      <div class="lbl sm" style="color:var(--ink-soft)">chip / status</div>
      <div style="margin-top:6px;"><span class="chip">default</span> <span class="chip acc">accent</span> <span class="chip fill">filled</span></div>
    </div>
    <div class="frame pad" style="padding:8px;">
      <div class="lbl sm" style="color:var(--ink-soft)">AI surface</div>
      <div class="tile ai" style="margin-top:6px; padding:6px 8px;"><span class="lbl sm">✦ always amber hatched</span></div>
    </div>
  </div>

  <!-- Responsive design -->
  <div class="lbl h" style="margin-top:18px;">④ Responsive design · 3 breakpoints</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <div class="row" style="gap:18px; align-items:flex-end; justify-content:center; flex-wrap:wrap;">
      <!-- desktop -->
      <div style="text-align:center;">
        <div class="frame" style="width:300px; height:180px; padding:6px; background: rgba(255,255,255,0.5);">
          <div class="row" style="gap:4px; height:100%;">
            <div class="sidebar" style="min-width:50px;">
              <div class="item on" style="font-size:9px;">Home</div>
              <div class="item" style="font-size:9px;">Sched</div>
              <div class="item" style="font-size:9px;">Grade</div>
            </div>
            <div class="col grow" style="gap:4px;">
              <div class="topbar" style="height:18px;"></div>
              <div class="grid-4" style="gap:3px;">
                <div class="kpi" style="padding:3px;"><div class="v" style="font-size:14px;">87</div></div>
                <div class="kpi" style="padding:3px;"><div class="v" style="font-size:14px;">2</div></div>
                <div class="kpi" style="padding:3px;"><div class="v" style="font-size:14px;">5</div></div>
                <div class="kpi" style="padding:3px;"><div class="v" style="font-size:14px;">€0</div></div>
              </div>
              <div class="tile" style="flex:1;"><div class="skeleton-line full"></div><div class="skeleton-line mid" style="margin-top:3px;"></div></div>
            </div>
          </div>
        </div>
        <div class="lbl" style="margin-top:6px;">Desktop · ≥ 1280</div>
        <div class="lbl sm" style="color:var(--ink-soft);">sidebar + multi-col</div>
      </div>

      <!-- tablet -->
      <div style="text-align:center;">
        <div class="frame" style="width:200px; height:240px; padding:6px; background: rgba(255,255,255,0.5);">
          <div class="topbar" style="height:18px;"><span class="lbl sm">☰</span></div>
          <div class="grid-2" style="gap:3px; margin-top:4px;">
            <div class="kpi" style="padding:3px;"><div class="v" style="font-size:14px;">87</div></div>
            <div class="kpi" style="padding:3px;"><div class="v" style="font-size:14px;">2</div></div>
          </div>
          <div class="tile" style="margin-top:4px; min-height:40px;"><div class="skeleton-line full"></div><div class="skeleton-line mid" style="margin-top:3px;"></div></div>
          <div class="tile ai" style="margin-top:4px; min-height:30px;"><div class="lbl sm">✦ next class</div></div>
        </div>
        <div class="lbl" style="margin-top:6px;">Tablet · 768–1279</div>
        <div class="lbl sm" style="color:var(--ink-soft);">collapsed nav · 2-col</div>
      </div>

      <!-- mobile -->
      <div style="text-align:center;">
        <div class="frame" style="width:130px; height:250px; padding:6px; background: rgba(255,255,255,0.5); border-radius: 16px;">
          <div class="topbar" style="height:18px;"><span class="lbl sm">☰</span><div class="right"><span class="pill" style="width:10px;height:10px;"></span></div></div>
          <div class="kpi" style="padding:4px; margin-top:4px;"><div class="v" style="font-size:18px;">87%</div><div class="k">pass</div></div>
          <div class="tile accent" style="margin-top:4px; min-height:36px;"><div class="lbl sm" style="font-size:9px;">10:30 · Algo II</div><div class="lbl sm" style="font-size:8px;">B-118 ✦</div></div>
          <div class="tile" style="margin-top:4px; min-height:24px;"><div class="skeleton-line full"></div></div>
          <div class="row" style="gap:3px; margin-top:6px; justify-content:space-around;">
            <div class="pill" style="width:14px;height:14px;"></div>
            <div class="pill" style="width:14px;height:14px;"></div>
            <div class="pill" style="width:14px;height:14px;"></div>
            <div class="pill" style="width:14px;height:14px;"></div>
          </div>
        </div>
        <div class="lbl" style="margin-top:6px;">Mobile · &lt; 768</div>
        <div class="lbl sm" style="color:var(--ink-soft);">bottom tabs · single col</div>
      </div>
    </div>
    <div class="lbl sm" style="margin-top:14px; color: var(--ink-soft);">Mobile-first CSS. Components reflow, not redesign. <b>Min hit target = 44px</b> on touch breakpoints.</div>
  </div>

  <!-- Design system -->
  <div class="lbl h" style="margin-top:22px;">⑤ Design system tokens</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Typography</div>
      <div class="lbl sm" style="margin-top:6px; color: var(--ink-soft);">Inter / system stack — neutral, readable, RTL-ready</div>
      <div style="margin-top:8px; font-family: 'Inter', sans-serif;">
        <div style="font-size: 28px; font-weight: 700; line-height: 1.1;">Display · 28/32</div>
        <div style="font-size: 20px; font-weight: 600; margin-top:4px;">Title · 20/26</div>
        <div style="font-size: 16px; margin-top:4px;">Body · 16/24</div>
        <div style="font-size: 14px; color: #5a5247; margin-top:4px;">Small · 14/20</div>
        <div style="font-size: 12px; color: #5a5247; margin-top:4px; font-family: monospace;">Mono · 12 · data</div>
      </div>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Spacing scale</div>
      <div class="lbl sm" style="margin-top:6px; color: var(--ink-soft);">4-pt base · 6 steps</div>
      <div class="col" style="gap:4px; margin-top:8px;">
        <div class="row" style="align-items:center; gap:6px;"><div style="height:4px; width:4px; background:var(--ink);"></div><span class="lbl sm">4 · xs · icon gap</span></div>
        <div class="row" style="align-items:center; gap:6px;"><div style="height:8px; width:8px; background:var(--ink);"></div><span class="lbl sm">8 · sm · between chips</span></div>
        <div class="row" style="align-items:center; gap:6px;"><div style="height:12px; width:12px; background:var(--ink);"></div><span class="lbl sm">12 · md · inside cards</span></div>
        <div class="row" style="align-items:center; gap:6px;"><div style="height:16px; width:16px; background:var(--ink);"></div><span class="lbl sm">16 · lg · card padding</span></div>
        <div class="row" style="align-items:center; gap:6px;"><div style="height:24px; width:24px; background:var(--ink);"></div><span class="lbl sm">24 · xl · between sections</span></div>
        <div class="row" style="align-items:center; gap:6px;"><div style="height:32px; width:32px; background:var(--ink);"></div><span class="lbl sm">32 · 2xl · page gutter</span></div>
      </div>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Colour palette</div>
      <div class="lbl sm" style="margin-top:6px; color: var(--ink-soft);">2 brand · 5 semantic · 6 neutrals</div>
      <div style="margin-top:8px; display:grid; grid-template-columns: repeat(6, 1fr); gap:4px;">
        <div style="height: 36px; background: var(--accent); border:1.4px solid var(--ink);"><span class="lbl sm" style="color:white; padding:2px 4px; font-size:9px;">brand/accent</span></div>
        <div style="height: 36px; background: oklch(0.55 0.13 200); border:1.4px solid var(--ink);"><span class="lbl sm" style="color:white; padding:2px 4px; font-size:9px;">brand/2</span></div>
        <div style="height: 36px; background: oklch(0.65 0.16 145); border:1.4px solid var(--ink);"><span class="lbl sm" style="color:white; padding:2px 4px; font-size:9px;">success</span></div>
        <div style="height: 36px; background: oklch(0.78 0.16 85); border:1.4px solid var(--ink);"><span class="lbl sm" style="padding:2px 4px; font-size:9px;">warning</span></div>
        <div style="height: 36px; background: oklch(0.58 0.20 25); border:1.4px solid var(--ink);"><span class="lbl sm" style="color:white; padding:2px 4px; font-size:9px;">danger</span></div>
        <div style="height: 36px; background: oklch(0.60 0.13 240); border:1.4px solid var(--ink);"><span class="lbl sm" style="color:white; padding:2px 4px; font-size:9px;">info</span></div>
        <div style="height: 24px; background: #fff; border:1.4px solid var(--ink);"></div>
        <div style="height: 24px; background: #f4ede0; border:1.4px solid var(--ink);"></div>
        <div style="height: 24px; background: #d6cfb8; border:1.4px solid var(--ink);"></div>
        <div style="height: 24px; background: #a89e8a; border:1.4px solid var(--ink);"></div>
        <div style="height: 24px; background: #5a5247; border:1.4px solid var(--ink);"></div>
        <div style="height: 24px; background: #2a2620; border:1.4px solid var(--ink);"></div>
      </div>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Reusable components</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>Button · primary / secondary / ghost / danger</li>
        <li>Input · text, number, date, search</li>
        <li>Select / Combobox · with type-ahead</li>
        <li>Card · KPI / List / Action / AI ✦</li>
        <li>Table · sortable, filterable, virtualised</li>
        <li>Chip · status / filter / tag</li>
        <li>Toast / Banner / Modal / Drawer</li>
        <li>Nav · sidebar / tabs / breadcrumbs</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Radius &amp; elevation</div>
      <div class="grid-3" style="margin-top:8px;">
        <div style="height: 40px; border:1.4px solid var(--ink); border-radius:0;"></div>
        <div style="height: 40px; border:1.4px solid var(--ink); border-radius:4px;"></div>
        <div style="height: 40px; border:1.4px solid var(--ink); border-radius:12px;"></div>
      </div>
      <div class="lbl sm" style="margin-top:6px; color: var(--ink-soft);">0 / 4 / 12 — never go higher (consistency)</div>
      <div class="lbl sm" style="margin-top:4px;">Shadow: <i>flat</i> default. Modal only.</div>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Iconography</div>
      <div class="lbl sm" style="margin-top:6px;">Single open-source set (e.g. Lucide). 20px / 24px sizes. Stroke 1.5px. No mixing styles.</div>
      <div class="row" style="gap:6px; margin-top:8px;">
        <div class="tile" style="width:32px; height:32px; padding:4px; display:flex; align-items:center; justify-content:center;"><svg width="18" height="18" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5" fill="none"><circle cx="12" cy="12" r="9"/></svg></div>
        <div class="tile" style="width:32px; height:32px; padding:4px; display:flex; align-items:center; justify-content:center;"><svg width="18" height="18" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5" fill="none"><rect x="4" y="4" width="16" height="16"/></svg></div>
        <div class="tile" style="width:32px; height:32px; padding:4px; display:flex; align-items:center; justify-content:center;"><svg width="18" height="18" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5" fill="none"><path d="M3 12 L9 18 L21 6"/></svg></div>
        <div class="tile" style="width:32px; height:32px; padding:4px; display:flex; align-items:center; justify-content:center;"><svg width="18" height="18" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5" fill="none"><path d="M12 3 L21 12 L12 21 M21 12 L3 12"/></svg></div>
      </div>
    </div>
  </div>

  <!-- Accessibility -->
  <div class="lbl h" style="margin-top:22px;">⑥ Accessibility · WCAG 2.1 AA checklist</div>
  <div class="grid-4" style="margin-top:6px;">
    <div class="tile"><div class="lbl h">Contrast</div><div class="lbl sm">text ≥ 4.5:1 · UI ≥ 3:1 · automated CI check</div></div>
    <div class="tile"><div class="lbl h">Keyboard</div><div class="lbl sm">every action reachable · visible focus ring · skip links</div></div>
    <div class="tile"><div class="lbl h">Screen reader</div><div class="lbl sm">semantic HTML · aria-labels on icons · live regions for toasts</div></div>
    <div class="tile"><div class="lbl h">Motion</div><div class="lbl sm">respect prefers-reduced-motion · no auto-playing video</div></div>
    <div class="tile"><div class="lbl h">Resize</div><div class="lbl sm">readable at 200% zoom · text reflows at 320px</div></div>
    <div class="tile"><div class="lbl h">Forms</div><div class="lbl sm">label every input · error msgs near the field · ≠ colour-only</div></div>
    <div class="tile"><div class="lbl h">Language</div><div class="lbl sm">lang attribute · FR / EN / AR-RTL · numerals localised</div></div>
    <div class="tile ai"><div class="lbl h">AI surfaces ✦</div><div class="lbl sm">always labelled "AI suggestion" · never autoplay / never auto-apply</div></div>
  </div>

  <!-- User journey -->
  <div class="lbl h" style="margin-top:22px;">⑦ User journey · "Lina checks if her room changed"</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 220" style="width:100%; height:auto;">
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <line x1="40" y1="120" x2="860" y2="120" stroke="#2a2620" stroke-width="1.5"/>
        <!-- emotion curve -->
        <path d="M 80,160 C 200,170 220,180 320,180 C 420,180 460,80 580,70 C 700,60 760,80 820,80"
              fill="none" stroke="#D9773C" stroke-width="2" stroke-dasharray="5 4"/>
        <text x="40" y="40" font-family="Caveat" font-size="14" fill="#5a5247">Emotional arc →</text>

        <g>
          <circle cx="80" cy="120" r="6" fill="#2a2620"/>
          <text x="80" y="105" text-anchor="middle" font-family="Caveat" font-size="14">① unlock phone</text>
          <text x="80" y="200" text-anchor="middle" font-size="10" fill="#5a5247">"is class 10:30 still on?"</text>

          <circle cx="240" cy="120" r="6" fill="#2a2620"/>
          <text x="240" y="105" text-anchor="middle" font-family="Caveat" font-size="14">② open app</text>
          <text x="240" y="200" text-anchor="middle" font-size="10" fill="#5a5247">app remembers her</text>

          <circle cx="400" cy="120" r="6" fill="#D9773C"/>
          <text x="400" y="105" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">③ home screen</text>
          <text x="400" y="200" text-anchor="middle" font-size="10" fill="#5a5247">"in 22 min · B-118 ✦"</text>

          <circle cx="560" cy="120" r="6" fill="#2a2620"/>
          <text x="560" y="105" text-anchor="middle" font-family="Caveat" font-size="14">④ tap card</text>
          <text x="560" y="200" text-anchor="middle" font-size="10" fill="#5a5247">map · walking time</text>

          <circle cx="720" cy="120" r="6" fill="#2a2620"/>
          <text x="720" y="105" text-anchor="middle" font-family="Caveat" font-size="14">⑤ heads to class</text>
          <text x="720" y="200" text-anchor="middle" font-size="10" fill="#5a5247">arrives on time, calm</text>
        </g>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:10px;">
      <div class="tile"><div class="lbl h">3 taps · 8 seconds</div><div class="lbl sm">from unlocking phone to knowing the answer</div></div>
      <div class="tile accent"><div class="lbl h">Anxiety → confidence</div><div class="lbl sm">the "official" stamp closes the loop</div></div>
      <div class="tile ai"><div class="lbl h">✦ AI does the work</div><div class="lbl sm">change auto-pushed; Lina pulls nothing</div></div>
    </div>
  </div>
</section>

<!-- ============ STUDENT ============ -->
<section class="tab-pane" data-pane="student">
  <div class="pane-head">
    <div>
      <h2>Student dashboard</h2>
      <p>"<i>You never know if a room change is official.</i>" — Three takes on a single home screen prioritising the next class, recent grades, and live changes.</p>
    </div>
    <div class="legend">
      <b>Top jobs</b><br>
      next class · room changes · grades<br>
      absence count · push alerts
    </div>
  </div>

  <div class="variants">
    <!-- v1 conventional sidebar dashboard -->
    <div class="wf">
      <div class="wf-tag">v1 · classic SIS</div>
      <h3>Sidebar + card grid</h3>
      <div class="wf-sub">Familiar. Every module behind a left rail. KPI tiles on top.</div>
      <div class="row" style="gap:6px;">
        <div class="sidebar" style="min-width: 78px;">
          <div class="lbl sm">Lina M.</div>
          <div class="item on">Home</div>
          <div class="item">Schedule</div>
          <div class="item">Grades</div>
          <div class="item">Absences</div>
          <div class="item">Courses</div>
          <div class="item">Messages</div>
          <div class="item">Profile</div>
        </div>
        <div class="col grow">
          <div class="topbar">
            <span class="crumbs">Home · Fall 2025</span>
            <div class="right"><span class="chip">B.Sc · S3</span><span class="pill"></span><span class="pill"></span></div>
          </div>
          <div class="grid-4">
            <div class="kpi"><div class="v">14.2</div><div class="k">GPA</div></div>
            <div class="kpi"><div class="v">2</div><div class="k">absences</div></div>
            <div class="kpi"><div class="v">5</div><div class="k">today's classes</div></div>
            <div class="kpi"><div class="v">€0</div><div class="k">balance due</div></div>
          </div>
          <div class="grid-2">
            <div class="tile" style="min-height:120px;">
              <div class="lbl h">Next up</div>
              <div class="lbl">Algorithms II · 10:30</div>
              <div class="lbl sm">Room B-204 · Prof. Hadji</div>
              <div class="skeleton-line full" style="margin-top:6px;"></div>
              <div class="skeleton-line mid" style="margin-top:4px;"></div>
            </div>
            <div class="tile" style="min-height:120px;">
              <div class="lbl h">Recent grades</div>
              <div class="row" style="justify-content:space-between"><span class="lbl">Stats</span><span class="lbl">15</span></div>
              <div class="row" style="justify-content:space-between"><span class="lbl">Web Dev</span><span class="lbl">13</span></div>
              <div class="row" style="justify-content:space-between"><span class="lbl">English</span><span class="lbl">17</span></div>
            </div>
          </div>
          <div class="tile">
            <div class="lbl h">Announcements</div>
            <div class="skeleton-line full"></div>
            <div class="skeleton-line full" style="margin-top:4px;"></div>
            <div class="skeleton-line mid" style="margin-top:4px;"></div>
          </div>
        </div>
      </div>
      <div class="pros">
        <span class="plus">zero learning curve</span>
        <span class="minus">no answer to "is room change real?"</span>
      </div>
    </div>

    <!-- v2 focus / next-action feed -->
    <div class="wf">
      <div class="wf-tag">v2 · focus mode</div>
      <h3>"What now?" feed</h3>
      <div class="wf-sub">Single scrollable timeline. Today first, then this week, then changes/alerts inline.</div>
      <div class="topbar">
        <span class="crumbs">☰ Lina · Today, Tue 14 Oct</span>
        <div class="right"><span class="chip acc">3 changes</span><span class="pill"></span></div>
      </div>
      <div class="col" style="margin-top:8px;">
        <div class="tile accent" style="border-color:var(--accent);">
          <div class="row" style="justify-content:space-between">
            <span class="lbl h">10:30 · Algorithms II</span>
            <span class="chip acc">in 22 min</span>
          </div>
          <div class="lbl sm">B-204 → <b>moved to B-118</b></div>
          <span class="annot" style="position:static; display:block; margin-top:4px;">✦ confirmed by admin · 09:12</span>
        </div>
        <div class="tile">
          <div class="row" style="justify-content:space-between"><span class="lbl h">13:00 · Stats lab</span><span class="chip">no change</span></div>
          <div class="lbl sm">Lab-3</div>
        </div>
        <div class="tile fill"><span class="lbl h">Wed · 3 classes</span><div class="grid-3" style="margin-top:4px;">
          <div class="skeleton-line full"></div><div class="skeleton-line full"></div><div class="skeleton-line full"></div>
        </div></div>
        <div class="tile ai">
          <div class="row" style="justify-content:space-between"><span class="lbl h">✦ AI assistant</span><span class="chip acc">3 nudges</span></div>
          <div class="lbl sm">"You missed last Stats lecture — want a 10-min recap?"</div>
        </div>
        <div class="tile">
          <div class="lbl h">New grade · Web Dev · <b>13/20</b></div>
          <div class="skeleton-line mid"></div>
        </div>
      </div>
      <div class="pros">
        <span class="plus">solves room-change anxiety</span>
        <span class="minus">harder to find deep info</span>
      </div>
    </div>

    <!-- v3 timetable-first -->
    <div class="wf">
      <div class="wf-tag">v3 · novel</div>
      <h3>Timetable canvas</h3>
      <div class="wf-sub">Week grid is the home. Everything else lives in the right rail.</div>
      <div class="topbar">
        <span class="crumbs">◀ week 42 ▶ · my timetable</span>
        <div class="right"><span class="chip">grades</span><span class="chip">absences</span></div>
      </div>
      <div class="row" style="gap:6px; margin-top:6px;">
        <div class="ttgrid grow">
          <div class="head"></div><div class="head">Mon</div><div class="head">Tue</div><div class="head">Wed</div><div class="head">Thu</div><div class="head">Fri</div>
          <div class="head">8</div><div class="blk"></div><div class="empty"></div><div class="blk"></div><div class="empty"></div><div class="blk"></div>
          <div class="head">10</div><div class="blk"></div><div class="acc">Algo II<br>B-118 ✦</div><div class="blk"></div><div class="empty"></div><div class="blk"></div>
          <div class="head">12</div><div class="empty"></div><div class="empty"></div><div class="empty"></div><div class="empty"></div><div class="empty"></div>
          <div class="head">14</div><div class="blk"></div><div class="blk"></div><div class="ai">AI lab ✦</div><div class="blk"></div><div class="empty"></div>
          <div class="head">16</div><div class="empty"></div><div class="blk"></div><div class="empty"></div><div class="blk"></div><div class="empty"></div>
        </div>
        <div class="col" style="width: 110px;">
          <div class="kpi"><div class="v">14.2</div><div class="k">GPA</div></div>
          <div class="kpi"><div class="v">2</div><div class="k">absences</div></div>
          <div class="tile" style="padding:6px;"><span class="lbl sm">last grade</span><div class="lbl">Stats · 15</div></div>
          <div class="tile ai" style="padding:6px;"><span class="lbl sm">✦ AI</span><div class="lbl sm">"prep for Fri quiz?"</div></div>
        </div>
      </div>
      <div class="pros">
        <span class="plus">schedule = main mental model</span>
        <span class="minus">mobile compresses badly</span>
      </div>
    </div>
  </div>
</section>

<!-- ============ TEACHER ============ -->
<section class="tab-pane" data-pane="teacher">
  <div class="pane-head">
    <div>
      <h2>Teacher dashboard</h2>
      <p>Grading and attendance must take <i>seconds</i>, not minutes. Three angles: classic gradebook, "today only" focus, and a roster-first split view.</p>
    </div>
    <div class="legend"><b>Top jobs</b><br>grade entry · attendance<br>room booking · class history</div>
  </div>

  <div class="variants">
    <!-- v1 -->
    <div class="wf">
      <div class="wf-tag">v1 · gradebook</div>
      <h3>Spreadsheet-first</h3>
      <div class="wf-sub">A familiar matrix view. Each row a student, each column an assessment.</div>
      <div class="topbar">
        <span class="crumbs">Algorithms II · S3 · group A</span>
        <div class="right"><span class="chip">save ✓</span><span class="chip">export</span></div>
      </div>
      <div class="col" style="margin-top:6px; gap: 0;">
        <div class="row" style="gap:0;">
          <div class="tile" style="width:90px; border-radius:4px 0 0 0;"><span class="lbl sm">Student</span></div>
          <div class="tile fill" style="flex:1; border-left:none; border-radius:0;"><span class="lbl sm">Quiz 1</span></div>
          <div class="tile fill" style="flex:1; border-left:none; border-radius:0;"><span class="lbl sm">Mid</span></div>
          <div class="tile fill" style="flex:1; border-left:none; border-radius:0;"><span class="lbl sm">Project</span></div>
          <div class="tile fill" style="flex:1; border-left:none; border-radius:0 4px 0 0;"><span class="lbl sm">Final</span></div>
        </div>
        <!-- rows -->
        <div class="row" style="gap:0; margin-top:-2px;">
          <div class="tile" style="width:90px; border-radius:0;"><span class="lbl">A. Mansouri</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">14</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">12</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">15</span></div>
          <div class="tile dashed" style="flex:1; border-left:none;"><span class="lbl sm">—</span></div>
        </div>
        <div class="row" style="gap:0; margin-top:-2px;">
          <div class="tile" style="width:90px; border-radius:0;"><span class="lbl">B. Idrissi</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">17</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">16</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">18</span></div>
          <div class="tile dashed" style="flex:1; border-left:none;"><span class="lbl sm">—</span></div>
        </div>
        <div class="row" style="gap:0; margin-top:-2px;">
          <div class="tile" style="width:90px; border-radius:0;"><span class="lbl">C. Lopez</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">09</span></div>
          <div class="tile ai" style="flex:1; border-left:none;"><span class="lbl">✦ risk</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">11</span></div>
          <div class="tile dashed" style="flex:1; border-left:none;"><span class="lbl sm">—</span></div>
        </div>
        <div class="row" style="gap:0; margin-top:-2px;">
          <div class="tile" style="width:90px; border-radius:0 0 0 4px;"><span class="lbl">D. Nakamura</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">15</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">14</span></div>
          <div class="tile" style="flex:1; border-left:none;"><span class="lbl">16</span></div>
          <div class="tile dashed" style="flex:1; border-left:none; border-radius:0 0 4px 0;"><span class="lbl sm">—</span></div>
        </div>
      </div>
      <div class="tile ai" style="margin-top:8px;">
        <span class="lbl h">✦ AI · attendance summary</span>
        <div class="lbl sm">"3 students missed ≥30%. Suggest 1:1 outreach."</div>
      </div>
      <div class="pros">
        <span class="plus">fast bulk entry</span>
        <span class="minus">hides individual stories</span>
      </div>
    </div>

    <!-- v2 today-only -->
    <div class="wf">
      <div class="wf-tag">v2 · today only</div>
      <h3>One class at a time</h3>
      <div class="wf-sub">Card carousel — flip through today's sessions. Each card has attendance + quick grade.</div>
      <div class="topbar">
        <span class="crumbs">Today · 3 sessions</span>
        <div class="right"><span class="chip">◀</span><span class="chip">▶</span></div>
      </div>
      <div class="frame" style="margin-top:8px; padding:10px;">
        <div class="row" style="justify-content:space-between">
          <div>
            <div class="lbl big">Algorithms II</div>
            <div class="lbl sm">10:30 – 12:00 · B-118 · group A</div>
          </div>
          <span class="chip fill">now</span>
        </div>
        <div class="row" style="margin-top:8px; gap:6px;">
          <div class="tile" style="flex:1;">
            <span class="lbl sm">Attendance</span>
            <div class="row" style="gap:4px; margin-top:4px; flex-wrap:wrap;">
              <span class="chip fill">●</span><span class="chip fill">●</span><span class="chip fill">●</span><span class="chip">○</span>
              <span class="chip fill">●</span><span class="chip fill">●</span><span class="chip">○</span><span class="chip fill">●</span>
              <span class="chip fill">●</span><span class="chip fill">●</span><span class="chip fill">●</span><span class="chip">○</span>
            </div>
            <div class="lbl sm" style="margin-top:6px;">21 / 24 present · tap to flip</div>
          </div>
          <div class="tile" style="flex:1;">
            <span class="lbl sm">Quick add</span>
            <div class="row" style="gap:4px; margin-top:4px;">
              <span class="chip">+ note</span><span class="chip">+ grade</span><span class="chip">+ resource</span>
            </div>
            <div class="skeleton-line full" style="margin-top:8px;"></div>
            <div class="skeleton-line mid" style="margin-top:4px;"></div>
          </div>
        </div>
        <div class="tile ai" style="margin-top:8px;">
          <span class="lbl h">✦ AI: draft today's summary</span>
          <div class="lbl sm">"3 absent, lecture on greedy algos, lab Friday. Send?"</div>
        </div>
      </div>
      <div class="pros">
        <span class="plus">distraction-free in-class</span>
        <span class="minus">slower for grading week</span>
      </div>
    </div>

    <!-- v3 split roster -->
    <div class="wf">
      <div class="wf-tag">v3 · split roster</div>
      <h3>Class · student · history</h3>
      <div class="wf-sub">Three-pane drill-down. Inspector pattern — tap a student, see their arc.</div>
      <div class="row" style="gap:4px;">
        <div class="col" style="width:90px;">
          <div class="lbl sm" style="margin-bottom:2px;">Classes</div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Algo II ·</span></div>
          <div class="tile" style="padding:4px 6px; background: var(--ink); color: var(--paper);"><span class="lbl sm" style="color:inherit">Stats · A</span></div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Stats · B</span></div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Sem Proj</span></div>
        </div>
        <div class="col" style="width: 110px;">
          <div class="lbl sm" style="margin-bottom:2px;">Roster</div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A. Mansouri 14</span></div>
          <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">B. Idrissi 17</span></div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">C. Lopez 09</span></div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">D. Nakamura 15</span></div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">E. Onyeka 13</span></div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">F. Perez 11</span></div>
        </div>
        <div class="col grow">
          <div class="lbl sm">B. Idrissi · S3</div>
          <div class="tile" style="min-height: 60px;">
            <div class="row" style="justify-content:space-between">
              <span class="lbl h">Trend</span><span class="chip acc">↑ rising</span>
            </div>
            <svg viewBox="0 0 200 40" style="width:100%; height:40px;">
              <polyline points="5,30 35,25 65,28 95,18 125,15 155,12 195,8"
                fill="none" stroke="var(--accent)" stroke-width="2"/>
              <g stroke="#5a5247" stroke-dasharray="2 3" stroke-width="0.8">
                <line x1="0" y1="20" x2="200" y2="20"/>
              </g>
            </svg>
          </div>
          <div class="grid-2">
            <div class="tile"><span class="lbl sm">attendance</span><div class="lbl big">96%</div></div>
            <div class="tile"><span class="lbl sm">avg grade</span><div class="lbl big">16.2</div></div>
          </div>
          <div class="tile ai"><span class="lbl h">✦ AI note</span>
            <div class="lbl sm">"Top of class — suggest mentoring pairing with C. Lopez."</div>
          </div>
        </div>
      </div>
      <div class="pros">
        <span class="plus">teachers see the human</span>
        <span class="minus">3 columns squeeze on laptop</span>
      </div>
    </div>
  </div>
</section>

<!-- ============ ADMIN ============ -->
<section class="tab-pane" data-pane="admin">
  <div class="pane-head">
    <div>
      <h2>Admin / Educational manager</h2>
      <p>Ops console — registrations, payments, room conflicts. The audit pain ("payment reminders semi-manual") gets solved here.</p>
    </div>
    <div class="legend"><b>Top jobs</b><br>registrations · payments<br>room conflicts · ops KPIs</div>
  </div>

  <div class="variants">
    <!-- v1 inbox / queues -->
    <div class="wf">
      <div class="wf-tag">v1 · queues</div>
      <h3>Triage inbox</h3>
      <div class="wf-sub">Everything that needs attention as a single ranked list. Filters on the left.</div>
      <div class="row" style="gap:6px;">
        <div class="sidebar" style="min-width: 80px;">
          <div class="lbl sm">Filters</div>
          <div class="item on">All · 47</div>
          <div class="item">Payments · 18</div>
          <div class="item">Conflicts · 6</div>
          <div class="item">Files · 12</div>
          <div class="item">Refunds · 3</div>
          <div class="item">AI ✦ · 8</div>
        </div>
        <div class="col grow">
          <div class="topbar"><span class="crumbs">Inbox · Campus B</span>
            <div class="right"><span class="chip">bulk</span><span class="chip">assign</span></div>
          </div>
          <div class="col" style="gap:4px; margin-top:6px;">
            <div class="tile"><div class="row" style="justify-content:space-between"><span class="lbl">💶 Late payment · M. Tahiri</span><span class="chip acc">€840 · 18d</span></div></div>
            <div class="tile"><div class="row" style="justify-content:space-between"><span class="lbl">🗓 Room conflict · B-204 Fri 14h</span><span class="chip">2 classes</span></div></div>
            <div class="tile ai"><div class="row" style="justify-content:space-between"><span class="lbl">✦ AI suggests move to B-118 (free)</span><span class="chip acc">apply</span></div></div>
            <div class="tile"><div class="row" style="justify-content:space-between"><span class="lbl">📎 Missing transcript · L. Bouazza</span><span class="chip">request</span></div></div>
            <div class="tile"><div class="row" style="justify-content:space-between"><span class="lbl">💶 Late payment · 4 students</span><span class="chip">€2,160</span></div></div>
            <div class="tile ai"><div class="row" style="justify-content:space-between"><span class="lbl">✦ AI drafted 4 dunning emails</span><span class="chip acc">review</span></div></div>
            <div class="tile"><div class="row" style="justify-content:space-between"><span class="lbl">📝 New enrollment · S. Park</span><span class="chip">approve</span></div></div>
          </div>
        </div>
      </div>
      <div class="pros">
        <span class="plus">work disappears as you clear it</span>
        <span class="minus">no spatial sense of rooms</span>
      </div>
    </div>

    <!-- v2 finance + ops board -->
    <div class="wf">
      <div class="wf-tag">v2 · ops board</div>
      <h3>Finance + capacity board</h3>
      <div class="wf-sub">KPI hero + two columns: collections and room utilisation, both as kanban-ish lanes.</div>
      <div class="grid-4">
        <div class="kpi"><div class="v">€124k</div><div class="k">collected (mo)</div></div>
        <div class="kpi"><div class="v">€18.2k</div><div class="k">overdue</div></div>
        <div class="kpi"><div class="v">81%</div><div class="k">room util.</div></div>
        <div class="kpi"><div class="v">6</div><div class="k">conflicts</div></div>
      </div>
      <div class="grid-2" style="margin-top:8px;">
        <div class="frame pad" style="padding:8px;">
          <div class="lbl h">Collections</div>
          <div class="col" style="gap:4px; margin-top:4px;">
            <div class="lbl sm" style="margin-top:2px;">on time</div>
            <div class="tile" style="padding:4px 6px;"><span class="lbl sm">M. Bennani · €420</span></div>
            <div class="lbl sm" style="margin-top:4px;">5-15 days late</div>
            <div class="tile" style="padding:4px 6px;"><span class="lbl sm">3 students · €1,260</span></div>
            <div class="lbl sm" style="margin-top:4px;">> 15 days</div>
            <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">M. Tahiri · €840</span></div>
            <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">✦ AI: escalate? draft call script</span></div>
          </div>
        </div>
        <div class="frame pad" style="padding:8px;">
          <div class="lbl h">Rooms · this week</div>
          <div class="col" style="gap:4px; margin-top:4px;">
            <div class="lbl sm">free</div>
            <div class="row"><span class="chip">A-101</span><span class="chip">A-205</span><span class="chip">B-110</span></div>
            <div class="lbl sm" style="margin-top:4px;">tight</div>
            <div class="row"><span class="chip">B-118</span><span class="chip">Lab-3</span></div>
            <div class="lbl sm" style="margin-top:4px;">conflicts</div>
            <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">B-204 · Fri 14h ×2</span></div>
            <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">✦ AI: auto-resolve all</span></div>
          </div>
        </div>
      </div>
      <div class="pros">
        <span class="plus">two big pains at a glance</span>
        <span class="minus">other modules pushed to nav</span>
      </div>
    </div>

    <!-- v3 calendar-grid -->
    <div class="wf">
      <div class="wf-tag">v3 · novel</div>
      <h3>Building-floor heatmap</h3>
      <div class="wf-sub">Rooms drawn as a literal floorplan grid; colour = occupancy. Click to zoom into a slot.</div>
      <div class="topbar">
        <span class="crumbs">Campus B · Fri 18 Oct</span>
        <div class="right"><span class="chip">8h</span><span class="chip">14h</span><span class="chip">18h</span></div>
      </div>
      <div style="display:grid; grid-template-columns: repeat(6, 1fr); gap:3px; margin-top:8px;">
        <!-- 24 rooms colored -->
        <div class="tile fill" style="min-height:40px;"><span class="lbl sm">A-101</span></div>
        <div class="tile fill" style="min-height:40px;"><span class="lbl sm">A-102</span></div>
        <div class="tile" style="min-height:40px; background:rgba(217,119,60,0.30);"><span class="lbl sm">A-103</span></div>
        <div class="tile" style="min-height:40px; background:rgba(42,38,32,0.30);"><span class="lbl sm">A-104</span></div>
        <div class="tile fill" style="min-height:40px;"><span class="lbl sm">A-201</span></div>
        <div class="tile" style="min-height:40px; background:rgba(42,38,32,0.30);"><span class="lbl sm">A-205</span></div>

        <div class="tile" style="min-height:40px; background:rgba(42,38,32,0.30);"><span class="lbl sm">B-110</span></div>
        <div class="tile fill" style="min-height:40px;"><span class="lbl sm">B-118</span></div>
        <div class="tile accent" style="min-height:40px; background:rgba(217,119,60,0.45);"><span class="lbl sm">B-204 ⚠</span></div>
        <div class="tile" style="min-height:40px; background:rgba(42,38,32,0.30);"><span class="lbl sm">B-206</span></div>
        <div class="tile fill" style="min-height:40px;"><span class="lbl sm">Lab-1</span></div>
        <div class="tile" style="min-height:40px; background:rgba(217,119,60,0.30);"><span class="lbl sm">Lab-3</span></div>

        <div class="tile" style="min-height:40px;"><span class="lbl sm">Audi-1</span></div>
        <div class="tile fill" style="min-height:40px;"><span class="lbl sm">Audi-2</span></div>
        <div class="tile" style="min-height:40px;"><span class="lbl sm">C-301</span></div>
        <div class="tile fill" style="min-height:40px;"><span class="lbl sm">C-302</span></div>
        <div class="tile" style="min-height:40px;"><span class="lbl sm">C-305</span></div>
        <div class="tile fill" style="min-height:40px;"><span class="lbl sm">C-310</span></div>
      </div>
      <div class="row" style="margin-top:8px; gap:6px;">
        <span class="chip">free</span>
        <span class="chip fill">booked</span>
        <span class="chip" style="background:rgba(42,38,32,0.30);">tight</span>
        <span class="chip acc">conflict</span>
      </div>
      <div class="tile ai" style="margin-top:6px;">
        <span class="lbl h">✦ AI · B-204 conflict</span>
        <div class="lbl sm">"Move 'Stats S2-B' → B-118 14h. 38 students, walk = 2 min. Apply?"</div>
      </div>
      <div class="pros">
        <span class="plus">conflicts feel physical</span>
        <span class="minus">single-day scope</span>
      </div>
    </div>
  </div>
</section>

<!-- ============ MANAGEMENT ============ -->
<section class="tab-pane" data-pane="mgmt">
  <div class="pane-head">
    <div>
      <h2>Management dashboard</h2>
      <p>"<i>We need to move from craft-based to systemic organization.</i>" — Consolidated indicators across the four campuses, in three flavours.</p>
    </div>
    <div class="legend"><b>Top jobs</b><br>cross-campus KPIs<br>success · occupancy · revenue<br>plan + improve</div>
  </div>

  <div class="variants">
    <!-- v1 -->
    <div class="wf">
      <div class="wf-tag">v1 · classic exec</div>
      <h3>KPI hero + trend rows</h3>
      <div class="wf-sub">Big numbers, sparkline rows below. The board-meeting layout.</div>
      <div class="topbar"><span class="crumbs">Group · YTD · all campuses</span>
        <div class="right"><span class="chip">YTD</span><span class="chip fill">QTD</span><span class="chip">MTD</span></div>
      </div>
      <div class="grid-4" style="margin-top:8px;">
        <div class="kpi"><div class="v">87%</div><div class="k">pass rate ↑3</div></div>
        <div class="kpi"><div class="v">81%</div><div class="k">occupancy ↓2</div></div>
        <div class="kpi"><div class="v">€2.4M</div><div class="k">revenue ↑11</div></div>
        <div class="kpi"><div class="v">2 775</div><div class="k">students</div></div>
      </div>
      <div class="col" style="margin-top:8px; gap:4px;">
        <div class="row" style="gap:6px; align-items:center;">
          <div class="lbl" style="width:90px;">Campus A</div>
          <svg viewBox="0 0 200 24" style="flex:1; height:24px;">
            <polyline points="0,18 25,16 50,14 75,12 100,13 125,10 150,9 175,7 200,6" fill="none" stroke="var(--ink)" stroke-width="1.6"/>
          </svg>
          <div class="lbl sm">88% · €620k</div>
        </div>
        <div class="row" style="gap:6px; align-items:center;">
          <div class="lbl" style="width:90px;">Campus B</div>
          <svg viewBox="0 0 200 24" style="flex:1; height:24px;">
            <polyline points="0,12 25,10 50,11 75,14 100,12 125,15 150,12 175,11 200,9" fill="none" stroke="var(--ink)" stroke-width="1.6"/>
          </svg>
          <div class="lbl sm">85% · €910k</div>
        </div>
        <div class="row" style="gap:6px; align-items:center;">
          <div class="lbl" style="width:90px;">Campus C</div>
          <svg viewBox="0 0 200 24" style="flex:1; height:24px;">
            <polyline points="0,14 25,18 50,16 75,20 100,18 125,19 150,17 175,18 200,15" fill="none" stroke="var(--accent)" stroke-width="1.6"/>
          </svg>
          <div class="lbl sm">79% ⚠ · €510k</div>
        </div>
        <div class="row" style="gap:6px; align-items:center;">
          <div class="lbl" style="width:90px;">Campus D</div>
          <svg viewBox="0 0 200 24" style="flex:1; height:24px;">
            <polyline points="0,22 25,20 50,18 75,16 100,14 125,12 150,11 175,10 200,8" fill="none" stroke="var(--ink)" stroke-width="1.6" stroke-dasharray="3 3"/>
          </svg>
          <div class="lbl sm">new · €360k</div>
        </div>
      </div>
      <div class="tile ai" style="margin-top:8px;">
        <span class="lbl h">✦ AI · narrative</span>
        <div class="lbl sm">"Campus C dragging group pass rate. Probable cause: Stats S2 (n=68). Drill ↗"</div>
      </div>
      <div class="pros">
        <span class="plus">board-ready</span>
        <span class="minus">passive — no actions surfaced</span>
      </div>
    </div>

    <!-- v2 comparison matrix -->
    <div class="wf">
      <div class="wf-tag">v2 · comparison</div>
      <h3>Campus × metric matrix</h3>
      <div class="wf-sub">Small-multiples grid. Spot outliers at a glance. Click cell → drilldown.</div>
      <div class="topbar"><span class="crumbs">compare · 4 campuses × 5 metrics</span>
        <div class="right"><span class="chip">add metric +</span></div>
      </div>
      <div style="display:grid; grid-template-columns: 80px repeat(4, 1fr); gap:3px; margin-top:8px;">
        <div></div>
        <div class="head lbl sm" style="text-align:center; padding:2px;">A</div>
        <div class="head lbl sm" style="text-align:center; padding:2px;">B</div>
        <div class="head lbl sm" style="text-align:center; padding:2px;">C</div>
        <div class="head lbl sm" style="text-align:center; padding:2px;">D</div>

        <div class="lbl sm" style="align-self:center;">pass</div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">88</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">85</div></div>
        <div class="tile accent" style="padding:4px; background:rgba(217,119,60,0.18);"><div class="lbl big" style="font-size:18px;">79</div></div>
        <div class="tile dashed" style="padding:4px;"><div class="lbl sm">new</div></div>

        <div class="lbl sm" style="align-self:center;">attend</div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">93</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">91</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">87</div></div>
        <div class="tile dashed" style="padding:4px;"><div class="lbl sm">94</div></div>

        <div class="lbl sm" style="align-self:center;">occ.</div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">84</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">86</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">78</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">63</div></div>

        <div class="lbl sm" style="align-self:center;">rev/stu</div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">€760</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">€800</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">€840</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">€1.7k</div></div>

        <div class="lbl sm" style="align-self:center;">NPS</div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">+42</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">+38</div></div>
        <div class="tile accent" style="padding:4px; background:rgba(217,119,60,0.18);"><div class="lbl big" style="font-size:18px;">+11</div></div>
        <div class="tile" style="padding:4px;"><div class="lbl big" style="font-size:18px;">+55</div></div>
      </div>
      <div class="tile ai" style="margin-top:8px;">
        <span class="lbl h">✦ AI · outliers</span>
        <div class="lbl sm">"Campus C low on pass + NPS. Same root? See cohort drill ↗"</div>
      </div>
      <div class="pros">
        <span class="plus">compare without thinking</span>
        <span class="minus">no time dimension</span>
      </div>
    </div>

    <!-- v3 strategic narrative -->
    <div class="wf">
      <div class="wf-tag">v3 · novel</div>
      <h3>Narrative report</h3>
      <div class="wf-sub">A weekly briefing rendered like an article. AI writes the lede, humans approve.</div>
      <div class="frame pad" style="padding:14px;">
        <div class="lbl sm">Briefing · week 42 · auto-drafted ✦</div>
        <div class="lbl big" style="margin-top:4px;">"Group on track, Campus C needs attention."</div>
        <div class="lbl" style="margin-top:6px; line-height:1.4;">
          Pass rate is <b>87% (+3)</b>, revenue <b>+11% YoY</b>. The Stats S2 cohort at <b>Campus C</b> is dragging the average — 68 students, projected fail rate 24%.
        </div>
        <div class="grid-3" style="margin-top:10px;">
          <div class="kpi"><div class="v">87%</div><div class="k">pass</div></div>
          <div class="kpi"><div class="v">+11%</div><div class="k">rev YoY</div></div>
          <div class="kpi" style="background:rgba(217,119,60,0.12); border-color:var(--accent);"><div class="v">24%</div><div class="k">C · fail risk</div></div>
        </div>
        <div class="lbl sm" style="margin-top:8px; border-top:1px dashed var(--rule-soft); padding-top:6px;">Recommended actions</div>
        <div class="col" style="gap:4px; margin-top:4px;">
          <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">✦ schedule Stats S2-C tutoring · 4 sessions</span></div>
          <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">✦ open Campus D capacity for sept intake (+80 seats)</span></div>
          <div class="tile" style="padding:4px 6px;"><span class="lbl sm">— present to board · Mon</span></div>
        </div>
      </div>
      <div class="pros">
        <span class="plus">story sticks &gt; numbers do</span>
        <span class="minus">trust in AI required</span>
      </div>
    </div>
  </div>
</section>

<!-- ============ AI AGENT ============ -->
<section class="tab-pane" data-pane="ai">
  <div class="pane-head">
    <div>
      <h2>AI agent · placement study</h2>
      <p>Open brief from leadership. Three different "where does the agent live?" theses — pick one (or compose), each makes a different bet.</p>
    </div>
    <div class="legend"><b>Constraint</b><br>solve <i>one</i> real ERP loop<br>not chat-for-chat's sake</div>
  </div>

  <div class="variants">
    <!-- v1 schedule conflict resolver -->
    <div class="wf">
      <div class="wf-tag">thesis A</div>
      <h3>Schedule conflict resolver</h3>
      <div class="wf-sub">Embedded inside Admin. Watches room/teacher/student calendars; proposes moves.</div>
      <div class="frame pad" style="padding:10px;">
        <div class="row" style="justify-content:space-between">
          <div class="lbl h">Conflict · B-204 · Fri 14h</div>
          <span class="chip acc">2 classes</span>
        </div>
        <div class="grid-2" style="margin-top:6px;">
          <div class="tile"><span class="lbl sm">Class A</span><div class="lbl">Stats S2-B · 38 students</div></div>
          <div class="tile"><span class="lbl sm">Class B</span><div class="lbl">Web Dev S3 · 22 students</div></div>
        </div>
        <div class="tile ai" style="margin-top:6px;">
          <div class="lbl h">✦ Proposal</div>
          <div class="lbl sm">Move <b>Stats S2-B → B-118</b> (free 14-16, capacity 42, 2-min walk).</div>
          <div class="row" style="margin-top:4px; gap:4px;">
            <span class="chip fill">apply</span><span class="chip">edit</span><span class="chip">decline</span>
          </div>
        </div>
        <div class="lbl sm" style="margin-top:4px;">Why: capacity ✓ · walking distance ✓ · no teacher clash ✓ · 38 students notified by push.</div>
      </div>
      <div class="pros">
        <span class="plus">tight scope, measurable win</span>
        <span class="minus">narrow audience</span>
      </div>
    </div>

    <!-- v2 dunning / payments concierge -->
    <div class="wf">
      <div class="wf-tag">thesis B</div>
      <h3>Payments concierge</h3>
      <div class="wf-sub">Drafts dunning emails + payment plans. Closes the "semi-manual reminders" loop directly.</div>
      <div class="frame pad" style="padding:10px;">
        <div class="row" style="justify-content:space-between">
          <div class="lbl h">Overdue queue · 18</div>
          <span class="chip">€18.2k</span>
        </div>
        <div class="col" style="gap:4px; margin-top:6px;">
          <div class="bubble ai">"4 students > 15 days late, similar profile. Draft batch reminder + 3-month plan?"</div>
          <div class="bubble me">yes — but soften the tone for Tahiri (was sick).</div>
          <div class="bubble ai">"Done. Tahiri version: empathetic, no late fee. Others: standard. Preview?"</div>
        </div>
        <div class="grid-2" style="margin-top:8px;">
          <div class="tile"><span class="lbl sm">drafted</span><div class="lbl big">4</div></div>
          <div class="tile"><span class="lbl sm">awaiting human</span><div class="lbl big">4</div></div>
        </div>
        <div class="row" style="margin-top:6px; gap:4px;">
          <span class="chip fill">review all</span><span class="chip acc">send approved</span>
        </div>
      </div>
      <div class="pros">
        <span class="plus">directly cited audit pain</span>
        <span class="minus">tone/legal risk needs guardrails</span>
      </div>
    </div>

    <!-- v3 cohort risk + tutor -->
    <div class="wf">
      <div class="wf-tag">thesis C · novel</div>
      <h3>Cohort risk + study buddy</h3>
      <div class="wf-sub">Two-sided agent: warns teachers/mgmt about at-risk cohorts; coaches students 1:1.</div>
      <div class="frame pad" style="padding:10px;">
        <div class="lbl h">Stats S2 · Campus C</div>
        <div class="row" style="margin-top:4px; gap:6px;">
          <div class="tile" style="flex:1; padding:4px 6px;"><span class="lbl sm">cohort</span><div class="lbl">68 students</div></div>
          <div class="tile accent" style="flex:1; padding:4px 6px; background:rgba(217,119,60,0.12);"><span class="lbl sm">fail risk</span><div class="lbl big">24%</div></div>
          <div class="tile" style="flex:1; padding:4px 6px;"><span class="lbl sm">avg attend</span><div class="lbl">79%</div></div>
        </div>
        <div class="grid-2" style="margin-top:8px;">
          <div class="tile ai">
            <div class="lbl h">✦ Teacher view</div>
            <div class="lbl sm">"3 topics drive 70% of poor scores. Add Friday office hours?"</div>
          </div>
          <div class="tile ai">
            <div class="lbl h">✦ Student view</div>
            <div class="lbl sm">"Lina, you missed last lecture on hypothesis tests — 8-min recap ready."</div>
          </div>
        </div>
        <div class="lbl sm" style="margin-top:8px;">Loop: teacher signals → AI personalises → student acts → metrics close.</div>
      </div>
      <div class="pros">
        <span class="plus">academic + human impact</span>
        <span class="minus">heavier model + privacy work</span>
      </div>
    </div>
  </div>

  <!-- recommendation -->
  <div class="frame pad" style="padding:14px 16px; margin-top:18px; background: rgba(255,255,255,0.4);">
    <div class="row" style="justify-content:space-between; align-items:flex-start; gap:14px;">
      <div>
        <div class="lbl h" style="font-size:22px;">Recommendation for the brief</div>
        <div class="lbl" style="margin-top:4px; max-width: 720px;">
          Start with <b>thesis A (Schedule resolver)</b> as the demo-friendly MVP — tight scope, visible win, low risk. Sequence into <b>thesis B</b> next semester. Reserve <b>thesis C</b> as the differentiator for the final defense — bigger story, requires real cohort data.
        </div>
      </div>
      <div class="mast-stamp" style="transform: rotate(-3deg);">
        <b>pick for defense</b>
        A → B → C
      </div>
    </div>
  </div>
</section>

<!-- ============ LOT 2 · BACKLOG ============ -->
<section class="tab-pane" data-pane="backlog">
  <div class="pane-head">
    <div>
      <h2>Backlog · epics, stories, MoSCoW, MVP</h2>
      <p>From needs → features. Six epics, twenty-ish stories, prioritised, with an MVP cutline so the first sprint has a clear target.</p>
    </div>
    <div class="legend"><b>SCRUM toolkit</b><br>epics · user stories · MoSCoW<br>MVP definition · acceptance criteria</div>
  </div>

  <!-- Epics row -->
  <div class="lbl h" style="margin-top:4px;">① Epics</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="tile"><div class="lbl h">E1 · Identity & roles</div><div class="lbl sm">SSO, RBAC, multi-campus scoping</div></div>
    <div class="tile"><div class="lbl h">E2 · Academics</div><div class="lbl sm">courses, schedules, rooms, attendance</div></div>
    <div class="tile"><div class="lbl h">E3 · Grading</div><div class="lbl sm">entry, transcripts, history</div></div>
    <div class="tile"><div class="lbl h">E4 · Finance</div><div class="lbl sm">tuition, invoices, dunning</div></div>
    <div class="tile"><div class="lbl h">E5 · Notifications</div><div class="lbl sm">push, email, SMS · room changes</div></div>
    <div class="tile ai"><div class="lbl h">E6 · AI agent ✦</div><div class="lbl sm">conflicts, dunning, cohort risk</div></div>
  </div>

  <!-- Story cards -->
  <div class="lbl h" style="margin-top:18px;">② Sample user stories (acceptance criteria sketched)</div>
  <div class="variants" style="margin-top:6px;">
    <div class="wf">
      <div class="wf-tag">US-12 · E2</div>
      <h3>"Did my room change?"</h3>
      <div class="wf-sub">As a <b>student</b>, I want a clear signal when my class room/time changes, so I never miss class.</div>
      <div class="col" style="gap:4px;">
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Given</span><div class="lbl">a teacher updates a session room</div></div>
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">When</span><div class="lbl">the change is committed</div></div>
        <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Then</span><div class="lbl">enrolled students get push within 60s, and the change is flagged "official"</div></div>
      </div>
      <div class="pros"><span class="plus">size: M</span><span class="minus">depends on E5</span></div>
    </div>

    <div class="wf">
      <div class="wf-tag">US-23 · E3</div>
      <h3>"Bulk grade entry"</h3>
      <div class="wf-sub">As a <b>teacher</b>, I want to enter grades for a whole class in one screen, so I save 20 min per session.</div>
      <div class="col" style="gap:4px;">
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Given</span><div class="lbl">my class has an open assessment</div></div>
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">When</span><div class="lbl">I tab through rows entering values</div></div>
        <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Then</span><div class="lbl">drafts auto-save, students notified only on "publish"</div></div>
      </div>
      <div class="pros"><span class="plus">size: M</span><span class="minus">draft state UX</span></div>
    </div>

    <div class="wf">
      <div class="wf-tag">US-31 · E4+E6</div>
      <h3>"Stop chasing payments"</h3>
      <div class="wf-sub">As an <b>admin</b>, I want AI to draft dunning emails so I only spend time on edge cases.</div>
      <div class="col" style="gap:4px;">
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Given</span><div class="lbl">an invoice is &gt; N days late</div></div>
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">When</span><div class="lbl">I open the collections queue</div></div>
        <div class="tile ai" style="padding:6px 8px;"><span class="lbl sm">Then</span><div class="lbl">drafts are ready · tone toggle · I review/send</div></div>
      </div>
      <div class="pros"><span class="plus">size: L</span><span class="minus">legal review on tone</span></div>
    </div>
  </div>

  <!-- MoSCoW board -->
  <div class="lbl h" style="margin-top:22px;">③ MoSCoW prioritisation</div>
  <div class="grid-4" style="margin-top:6px;">
    <div class="frame pad" style="padding:8px;">
      <div class="lbl h">Must</div>
      <div class="col" style="gap:4px; margin-top:4px;">
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm">login · RBAC</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm">timetable view</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm">room change push</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm">grade entry</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm">invoice list</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm">attendance</span></div>
      </div>
    </div>
    <div class="frame pad" style="padding:8px;">
      <div class="lbl h">Should</div>
      <div class="col" style="gap:4px; margin-top:4px;">
        <div class="tile dashed" style="padding:4px 6px;"><span class="lbl sm">transcript export</span></div>
        <div class="tile dashed" style="padding:4px 6px;"><span class="lbl sm">conflict detector</span></div>
        <div class="tile dashed" style="padding:4px 6px;"><span class="lbl sm">mgmt KPIs</span></div>
        <div class="tile dashed" style="padding:4px 6px;"><span class="lbl sm">SMS reminders</span></div>
      </div>
    </div>
    <div class="frame pad" style="padding:8px;">
      <div class="lbl h">Could</div>
      <div class="col" style="gap:4px; margin-top:4px;">
        <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">✦ AI scheduler</span></div>
        <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">✦ AI dunning</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm">parent portal</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl sm">library module</span></div>
      </div>
    </div>
    <div class="frame pad" style="padding:8px;">
      <div class="lbl h">Won't (now)</div>
      <div class="col" style="gap:4px; margin-top:4px;">
        <div class="tile fill" style="padding:4px 6px; opacity:0.6;"><span class="lbl sm">HR payroll</span></div>
        <div class="tile fill" style="padding:4px 6px; opacity:0.6;"><span class="lbl sm">LMS content</span></div>
        <div class="tile fill" style="padding:4px 6px; opacity:0.6;"><span class="lbl sm">alumni CRM</span></div>
      </div>
    </div>
  </div>

  <!-- MVP cutline -->
  <div class="lbl h" style="margin-top:22px;">④ MVP definition</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 800 80" style="width:100%; height:80px;">
      <g font-family="Kalam" font-size="12" fill="#2a2620">
        <line x1="20" y1="40" x2="780" y2="40" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="380" y1="20" x2="380" y2="60" stroke="#D9773C" stroke-width="2" stroke-dasharray="4 3"/>
        <text x="380" y="14" text-anchor="middle" font-family="Caveat" font-size="18" fill="#D9773C">MVP cutline</text>
        <g>
          <circle cx="80" cy="40" r="4" fill="#2a2620"/><text x="80" y="58" text-anchor="middle">login</text>
          <circle cx="160" cy="40" r="4" fill="#2a2620"/><text x="160" y="58" text-anchor="middle">timetable</text>
          <circle cx="240" cy="40" r="4" fill="#2a2620"/><text x="240" y="58" text-anchor="middle">attendance</text>
          <circle cx="320" cy="40" r="4" fill="#2a2620"/><text x="320" y="58" text-anchor="middle">grades</text>
          <circle cx="440" cy="40" r="4" fill="#5a5247"/><text x="440" y="58" text-anchor="middle">invoices</text>
          <circle cx="520" cy="40" r="4" fill="#5a5247"/><text x="520" y="58" text-anchor="middle">mgmt KPIs</text>
          <circle cx="600" cy="40" r="4" fill="#D9773C"/><text x="600" y="58" text-anchor="middle" fill="#D9773C">AI ✦ resolver</text>
          <circle cx="680" cy="40" r="4" fill="#a89e8a"/><text x="680" y="58" text-anchor="middle" fill="#a89e8a">parent app</text>
          <circle cx="740" cy="40" r="4" fill="#a89e8a"/><text x="740" y="58" text-anchor="middle" fill="#a89e8a">library</text>
        </g>
        <text x="200" y="26" text-anchor="middle" font-family="Architects Daughter" font-size="11" fill="#5a5247">Sprint 1-3 · MUST</text>
        <text x="560" y="26" text-anchor="middle" font-family="Architects Daughter" font-size="11" fill="#5a5247">Sprint 4-6 · SHOULD + ★</text>
      </g>
    </svg>
    <div class="lbl sm" style="margin-top:8px;">MVP = enough to replace today's "non-interconnected tools" for two campuses, plus the AI conflict resolver as the defendable wow.</div>
  </div>

  <!-- Product backlog (ranked) -->
  <div class="lbl h" style="margin-top:22px;">⑤ Product backlog — ranked</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 36px 60px 50px 60px 1fr 60px; gap:3px;">
      <div class="lbl sm" style="font-weight:700;">#</div>
      <div class="lbl sm" style="font-weight:700;">ID</div>
      <div class="lbl sm" style="font-weight:700;">Epic</div>
      <div class="lbl sm" style="font-weight:700;">MoSCoW</div>
      <div class="lbl sm" style="font-weight:700;">User story</div>
      <div class="lbl sm" style="font-weight:700;">Size</div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">01</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-01</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E1</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As any user, I can log in via SSO with my campus account</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">S</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">02</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-02</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E1</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As admin, I can assign roles + campus scope to a user</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">03</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-08</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E2</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As student, I view my weekly timetable on web + mobile</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">04</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-12</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E2 / E5</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As student, I'm notified within 60s of a room/time change</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">05</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-15</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E2</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As teacher, I record attendance for a session in one screen</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">S</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">06</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-23</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E3</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As teacher, I bulk-enter grades for a class</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">07</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-25</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E3</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As student, I view all my grades + academic history</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">S</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">08</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-28</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E4</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As admin, I view the list of invoices &amp; their status</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">09</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-29</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E4</span></div>
      <div class="tile accent" style="padding:3px 6px;"><span class="lbl sm">Must</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As parent, I pay tuition online &amp; get a receipt</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">10</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-31</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E4 / E6</span></div>
      <div class="tile ai" style="padding:3px 6px;"><span class="lbl sm">Could ✦</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As admin, AI drafts dunning emails for me to review</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">L</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">11</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-34</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E2 / E6</span></div>
      <div class="tile ai" style="padding:3px 6px;"><span class="lbl sm">Could ✦</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As admin, AI proposes a room move for any conflict</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">12</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-37</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E2</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">Should</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As teacher, I book a free room from a map view</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">13</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-41</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E2</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">Should</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As student, I download an absence justification</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">S</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">14</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-43</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E3</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">Should</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As admin, I export an official transcript PDF</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">S</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">15</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-48</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">— mgmt</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">Should</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As mgmt, I see cross-campus KPIs in one dashboard</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">L</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">16</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-50</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">— mgmt</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">Should</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As mgmt, I export a campus comparison report (Excel)</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">17</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-55</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E5</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">Should</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As student, I configure my notification channels</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">S</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">18</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-60</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">E6 ✦</span></div>
      <div class="tile ai" style="padding:3px 6px;"><span class="lbl sm">Could ✦</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As teacher, AI flags at-risk students in my class</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">L</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">19</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-62</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">— parent</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">Could</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">As parent, I see my child's grades + payments</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">M</span></div>

      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">20</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">US-70</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm">— lib</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm" style="opacity:0.6;">Won't · v1</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm" style="opacity:0.6;">Library / book loans</span></div>
      <div class="tile" style="padding:3px 6px;"><span class="lbl sm" style="opacity:0.6;">L</span></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Ordering = sequencing by business value × technical risk × dependency. Above the line in MVP cutline (item ⓪④) lives in Sprints 1-3.</div>
  </div>

  <!-- Sprint goals -->
  <div class="lbl h" style="margin-top:22px;">⑥ Sprint plan · 2-week sprints</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Sprint 1</div>
      <div class="lbl sm" style="color:var(--ink-soft); margin-top:2px;">"Stand up the foundation"</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>SSO authentication (US-01)</li>
        <li>User &amp; role admin (US-02)</li>
        <li>CI/CD pipeline + observability skeleton</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Sprint 2</div>
      <div class="lbl sm" style="color:var(--ink-soft); margin-top:2px;">"Make the school visible"</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>Timetable view, student + teacher (US-08)</li>
        <li>Attendance entry (US-15)</li>
        <li>Course / room model</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Sprint 3</div>
      <div class="lbl sm" style="color:var(--ink-soft); margin-top:2px;">"Close the loop"</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>Notifications (US-12) — room change push</li>
        <li>Mgmt KPI dashboard skeleton</li>
        <li>Grade entry (US-23)</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Sprint 4</div>
      <div class="lbl sm" style="color:var(--ink-soft); margin-top:2px;">"Money in, money out"</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>Invoice list (US-28) + payment (US-29)</li>
        <li>Student grades + history (US-25)</li>
      </ul>
    </div>
    <div class="frame pad accent" style="padding:10px; border-color: var(--accent);">
      <div class="lbl h">Sprint 5 ✦</div>
      <div class="lbl sm" style="color:var(--ink-soft); margin-top:2px;">"The AI moment"</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>AI conflict resolver (US-34)</li>
        <li>AI dunning drafts (US-31)</li>
        <li>Demo-ready end-to-end</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Sprint 6</div>
      <div class="lbl sm" style="color:var(--ink-soft); margin-top:2px;">"Polish &amp; harden"</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>Transcript export (US-43)</li>
        <li>Room map booking (US-37)</li>
        <li>Load &amp; pen testing</li>
      </ul>
    </div>
  </div>

  <!-- Definition of Done -->
  <div class="lbl h" style="margin-top:22px;">⑦ Definition of Done</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <div class="lbl" style="margin-bottom:8px;">A story is "done" only when <i>all</i> of these are true:</div>
    <div class="grid-4">
      <div class="tile" style="padding:8px;"><div class="lbl h">✓ Coded</div><div class="lbl sm">PR merged · feature flag where needed</div></div>
      <div class="tile" style="padding:8px;"><div class="lbl h">✓ Tested</div><div class="lbl sm">unit + integration · &gt; 80% coverage</div></div>
      <div class="tile" style="padding:8px;"><div class="lbl h">✓ Reviewed</div><div class="lbl sm">code review by 1+ teammate</div></div>
      <div class="tile" style="padding:8px;"><div class="lbl h">✓ Documented</div><div class="lbl sm">README / API docs / runbook updated</div></div>
      <div class="tile" style="padding:8px;"><div class="lbl h">✓ Accessible</div><div class="lbl sm">WCAG 2.1 AA · keyboard tested</div></div>
      <div class="tile" style="padding:8px;"><div class="lbl h">✓ Secure</div><div class="lbl sm">RBAC checks · no secrets in code</div></div>
      <div class="tile" style="padding:8px;"><div class="lbl h">✓ Deployed</div><div class="lbl sm">staging green · ready to promote</div></div>
      <div class="tile" style="padding:8px;"><div class="lbl h">✓ Accepted</div><div class="lbl sm">PO validates against acceptance criteria</div></div>
    </div>
  </div>

  <!-- Story points -->
  <div class="lbl h" style="margin-top:22px;">⑧ Story points · the Fibonacci scale</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <div class="lbl" style="margin-bottom:8px;">We estimate <b>complexity</b>, not hours. Hours are about <i>who</i> does it; points are about <i>what</i> it is.</div>
    <div style="display:grid; grid-template-columns: repeat(7, 1fr); gap:6px;">
      <div class="kpi" style="padding:6px;"><div class="v">1</div><div class="k">trivial</div></div>
      <div class="kpi" style="padding:6px;"><div class="v">2</div><div class="k">small</div></div>
      <div class="kpi" style="padding:6px;"><div class="v">3</div><div class="k">simple</div></div>
      <div class="kpi" style="padding:6px;"><div class="v">5</div><div class="k">moderate</div></div>
      <div class="kpi" style="padding:6px;"><div class="v">8</div><div class="k">complex</div></div>
      <div class="kpi" style="padding:6px;"><div class="v">13</div><div class="k">very complex</div></div>
      <div class="kpi" style="padding:6px;"><div class="v">21</div><div class="k">split it!</div></div>
    </div>
    <div class="grid-3" style="margin-top:10px;">
      <div class="tile" style="padding:6px 8px;"><span class="lbl sm"><b>2 pts</b> · change a label, add a tooltip</span></div>
      <div class="tile" style="padding:6px 8px;"><span class="lbl sm"><b>5 pts</b> · build attendance entry screen</span></div>
      <div class="tile ai" style="padding:6px 8px;"><span class="lbl sm"><b>13 pts</b> ✦ AI conflict resolver MVP</span></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Velocity = sum of points completed per sprint. Used to forecast, never to judge people.</div>
  </div>

  <!-- Scrum roles -->
  <div class="lbl h" style="margin-top:22px;">⑨ Scrum roles</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Product Owner</div>
      <div class="lbl sm" style="margin-top:4px; color: var(--ink-soft);">→ Head of Education</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>owns the backlog &amp; priorities</li>
        <li>defines acceptance criteria</li>
        <li>represents stakeholders</li>
        <li>says "no" to scope creep</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Scrum Master</div>
      <div class="lbl sm" style="margin-top:4px; color: var(--ink-soft);">→ Tech lead</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>facilitates ceremonies (standup, retro, planning)</li>
        <li>removes blockers</li>
        <li>protects the team from interruptions</li>
        <li>coaches on agile practice</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Development team</div>
      <div class="lbl sm" style="margin-top:4px; color: var(--ink-soft);">→ 4-6 cross-functional engineers</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>builds &amp; tests the increment</li>
        <li>self-organises around stories</li>
        <li>commits to a sprint goal</li>
        <li>owns the Definition of Done</li>
      </ul>
    </div>
  </div>

  <!-- Ceremonies -->
  <div class="lbl h" style="margin-top:18px;">⑩ Ceremonies cadence</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <svg viewBox="0 0 900 100" style="width:100%; height:100px;">
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <line x1="20" y1="50" x2="880" y2="50" stroke="#2a2620" stroke-width="1.5"/>
        <text x="20" y="20" font-family="Caveat" font-size="14" fill="#5a5247">Sprint = 2 weeks</text>
        <g>
          <circle cx="60" cy="50" r="5" fill="#D9773C"/><text x="60" y="35" text-anchor="middle">planning</text><text x="60" y="75" text-anchor="middle" font-size="9" fill="#5a5247">2h · Mon</text>
          <circle cx="200" cy="50" r="4" fill="#2a2620"/><text x="200" y="35" text-anchor="middle">daily standup</text><text x="200" y="75" text-anchor="middle" font-size="9" fill="#5a5247">15min · every day</text>
          <circle cx="380" cy="50" r="4" fill="#2a2620"/><text x="380" y="35" text-anchor="middle">backlog refinement</text><text x="380" y="75" text-anchor="middle" font-size="9" fill="#5a5247">1h · mid-sprint</text>
          <circle cx="600" cy="50" r="4" fill="#2a2620"/><text x="600" y="35" text-anchor="middle">daily standup ...</text>
          <circle cx="780" cy="50" r="5" fill="#D9773C"/><text x="780" y="35" text-anchor="middle">review + retro</text><text x="780" y="75" text-anchor="middle" font-size="9" fill="#5a5247">2h · Fri</text>
        </g>
      </g>
    </svg>
  </div>
</section>

<!-- ============ LOT 3 · ARCHITECTURE ============ -->
<section class="tab-pane" data-pane="arch">
  <div class="pane-head">
    <div>
      <h2>Architecture &amp; UML</h2>
      <p>Microservices split, event flow, and the four UML diagrams the brief expects: use case, class, sequence, deployment.</p>
    </div>
    <div class="legend"><b>Toolkit</b><br>microservices · API gateway · event bus<br>UML: UC · class · seq · deploy</div>
  </div>

  <!-- Microservices map -->
  <div class="lbl h">① Microservices map</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 380" style="width:100%; height:auto;">
      <defs>
        <marker id="a2" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="12" fill="#2a2620">
        <!-- clients -->
        <rect x="20" y="20" width="120" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
        <text x="80" y="44" text-anchor="middle" font-family="Caveat" font-size="18">Web SPA</text>
        <rect x="20" y="80" width="120" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
        <text x="80" y="104" text-anchor="middle" font-family="Caveat" font-size="18">Mobile app</text>
        <rect x="20" y="140" width="120" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
        <text x="80" y="164" text-anchor="middle" font-family="Caveat" font-size="18">Admin console</text>

        <!-- gateway -->
        <rect x="200" y="60" width="140" height="100" rx="8" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="270" y="92" text-anchor="middle" font-family="Caveat" font-size="22" fill="#D9773C">API Gateway</text>
        <text x="270" y="112" text-anchor="middle" font-family="Architects Daughter" font-size="10" fill="#5a5247">JWT auth · rate limit</text>
        <text x="270" y="128" text-anchor="middle" font-family="Architects Daughter" font-size="10" fill="#5a5247">aggregation · routing</text>

        <!-- services -->
        <g>
          <rect x="400" y="20" width="130" height="44" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="465" y="48" text-anchor="middle" font-family="Caveat" font-size="18">Identity svc</text>
          <rect x="400" y="74" width="130" height="44" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="465" y="102" text-anchor="middle" font-family="Caveat" font-size="18">Academic svc</text>
          <rect x="400" y="128" width="130" height="44" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="465" y="156" text-anchor="middle" font-family="Caveat" font-size="18">Grading svc</text>
          <rect x="400" y="182" width="130" height="44" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="465" y="210" text-anchor="middle" font-family="Caveat" font-size="18">Finance svc</text>
          <rect x="400" y="236" width="130" height="44" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620" stroke-width="1.6"/>
          <text x="465" y="264" text-anchor="middle" font-family="Caveat" font-size="18">Notif svc</text>
          <rect x="400" y="290" width="130" height="44" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
          <text x="465" y="318" text-anchor="middle" font-family="Caveat" font-size="18" fill="#D9773C">AI agent svc ✦</text>
        </g>

        <!-- event bus -->
        <rect x="580" y="60" width="60" height="280" rx="6" fill="rgba(42,38,32,0.06)" stroke="#2a2620" stroke-dasharray="5 4"/>
        <text x="610" y="200" text-anchor="middle" transform="rotate(-90 610 200)" font-family="Caveat" font-size="22">Event bus</text>
        <text x="610" y="60" text-anchor="middle" font-family="Architects Daughter" font-size="10" fill="#5a5247" dy="-4">Kafka / NATS</text>

        <!-- datastores -->
        <g>
          <ellipse cx="760" cy="50" rx="50" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="760" y="54" text-anchor="middle">PG · identity</text>
          <ellipse cx="760" cy="100" rx="50" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="760" y="104" text-anchor="middle">PG · academic</text>
          <ellipse cx="760" cy="150" rx="50" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="760" y="154" text-anchor="middle">PG · grades</text>
          <ellipse cx="760" cy="200" rx="50" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="760" y="204" text-anchor="middle">PG · finance</text>
          <ellipse cx="760" cy="260" rx="50" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="760" y="264" text-anchor="middle">Mongo · logs</text>
          <ellipse cx="760" cy="320" rx="50" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="760" y="324" text-anchor="middle">Vector · AI</text>
        </g>
      </g>
      <!-- arrows -->
      <g stroke="#2a2620" stroke-width="1.4" fill="none" marker-end="url(#a2)">
        <path d="M140,40 L200,80"/>
        <path d="M140,100 L200,110"/>
        <path d="M140,160 L200,140"/>
        <path d="M340,90 L400,42"/>
        <path d="M340,100 L400,96"/>
        <path d="M340,120 L400,150"/>
        <path d="M340,140 L400,204"/>
        <path d="M340,150 L400,258"/>
        <path d="M340,160 L400,312" stroke="#D9773C"/>
      </g>
      <g stroke="#5a5247" stroke-width="1.2" fill="none" stroke-dasharray="3 3" marker-end="url(#a2)">
        <path d="M530,96 L580,120"/>
        <path d="M530,150 L580,170"/>
        <path d="M530,204 L580,220"/>
        <path d="M530,258 L580,260"/>
        <path d="M530,312 L580,300"/>
        <path d="M640,150 L710,150"/>
        <path d="M640,260 L710,260"/>
        <path d="M640,300 L710,320"/>
      </g>
      <g stroke="#2a2620" stroke-width="1.2" fill="none" marker-end="url(#a2)">
        <path d="M530,42 L710,50"/>
        <path d="M530,96 L710,100"/>
        <path d="M530,204 L710,200"/>
      </g>
    </svg>
    <div class="lbl sm" style="margin-top:6px;">Solid = sync REST. Dashed = async events. Each service owns its DB; AI svc reads via events + vector store for context.</div>
  </div>

  <!-- UML grid -->
  <div class="lbl h" style="margin-top:18px;">② UML · the four required diagrams</div>
  <div class="variants" style="margin-top:6px;">

    <!-- Use case -->
    <div class="wf">
      <div class="wf-tag">UML · use case</div>
      <h3>Who does what</h3>
      <div class="wf-sub">Actors → use cases. AI agent shown as a secondary actor.</div>
      <svg viewBox="0 0 360 260" style="width:100%; height:auto;">
        <g font-family="Kalam" font-size="11" fill="#2a2620">
          <!-- system box -->
          <rect x="90" y="20" width="200" height="220" rx="8" fill="rgba(255,255,255,0.4)" stroke="#2a2620"/>
          <text x="190" y="14" text-anchor="middle" font-family="Caveat" font-size="14" fill="#5a5247">NovaCampus ERP</text>
          <!-- use cases -->
          <ellipse cx="190" cy="50" rx="60" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="190" y="54" text-anchor="middle">view timetable</text>
          <ellipse cx="190" cy="84" rx="60" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="190" y="88" text-anchor="middle">enter grades</text>
          <ellipse cx="190" cy="118" rx="60" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="190" y="122" text-anchor="middle">book room</text>
          <ellipse cx="190" cy="152" rx="60" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="190" y="156" text-anchor="middle">pay tuition</text>
          <ellipse cx="190" cy="186" rx="60" ry="14" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="190" y="190" text-anchor="middle">view KPIs</text>
          <ellipse cx="190" cy="218" rx="60" ry="14" fill="rgba(217,119,60,0.15)" stroke="#D9773C"/><text x="190" y="222" text-anchor="middle" fill="#D9773C">resolve conflict ✦</text>
          <!-- actors -->
          <g>
            <circle cx="40" cy="50" r="6" fill="none" stroke="#2a2620"/><line x1="40" y1="56" x2="40" y2="68" stroke="#2a2620"/>
            <line x1="34" y1="60" x2="46" y2="60" stroke="#2a2620"/><line x1="40" y1="68" x2="34" y2="78" stroke="#2a2620"/><line x1="40" y1="68" x2="46" y2="78" stroke="#2a2620"/>
            <text x="40" y="92" text-anchor="middle">Student</text>

            <circle cx="40" cy="115" r="6" fill="none" stroke="#2a2620"/><line x1="40" y1="121" x2="40" y2="133" stroke="#2a2620"/>
            <line x1="34" y1="125" x2="46" y2="125" stroke="#2a2620"/><line x1="40" y1="133" x2="34" y2="143" stroke="#2a2620"/><line x1="40" y1="133" x2="46" y2="143" stroke="#2a2620"/>
            <text x="40" y="157" text-anchor="middle">Teacher</text>

            <circle cx="40" cy="180" r="6" fill="none" stroke="#2a2620"/><line x1="40" y1="186" x2="40" y2="198" stroke="#2a2620"/>
            <line x1="34" y1="190" x2="46" y2="190" stroke="#2a2620"/><line x1="40" y1="198" x2="34" y2="208" stroke="#2a2620"/><line x1="40" y1="198" x2="46" y2="208" stroke="#2a2620"/>
            <text x="40" y="222" text-anchor="middle">Admin</text>

            <circle cx="330" cy="115" r="6" fill="none" stroke="#2a2620"/><line x1="330" y1="121" x2="330" y2="133" stroke="#2a2620"/>
            <line x1="324" y1="125" x2="336" y2="125" stroke="#2a2620"/><line x1="330" y1="133" x2="324" y2="143" stroke="#2a2620"/><line x1="330" y1="133" x2="336" y2="143" stroke="#2a2620"/>
            <text x="330" y="157" text-anchor="middle">Mgmt</text>

            <rect x="316" y="208" width="28" height="22" stroke="#D9773C" fill="rgba(217,119,60,0.12)"/>
            <text x="330" y="223" text-anchor="middle" font-size="9" fill="#D9773C">AI ✦</text>
            <text x="330" y="244" text-anchor="middle" fill="#D9773C">agent</text>
          </g>
          <!-- lines -->
          <g stroke="#2a2620" stroke-width="1.1" fill="none">
            <path d="M50,50 L130,50"/>
            <path d="M50,115 C90,90 100,84 130,84"/>
            <path d="M50,115 C90,115 100,118 130,118"/>
            <path d="M50,180 C90,155 100,152 130,152"/>
            <path d="M50,180 C90,180 100,186 130,186"/>
            <path d="M320,115 C280,140 260,180 250,186"/>
            <path d="M250,186 C260,210 290,218 316,218" stroke="#D9773C"/>
          </g>
        </g>
      </svg>
      <div class="pros"><span class="plus">classic UC1</span><span class="minus">flat — no campus</span></div>
    </div>

    <!-- Class diagram -->
    <div class="wf">
      <div class="wf-tag">UML · class</div>
      <h3>Domain model (core)</h3>
      <div class="wf-sub">Six core classes. Real model has ~25 — this is the explanatory slice.</div>
      <svg viewBox="0 0 360 290" style="width:100%; height:auto; font-family: Kalam, sans-serif;">
        <g font-size="10" fill="#2a2620">
          <!-- Student -->
          <rect x="20" y="20" width="100" height="70" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <line x1="20" y1="38" x2="120" y2="38" stroke="#2a2620"/>
          <line x1="20" y1="64" x2="120" y2="64" stroke="#2a2620"/>
          <text x="70" y="33" text-anchor="middle" font-family="Caveat" font-size="14">Student</text>
          <text x="24" y="50">- id, name</text><text x="24" y="60">- campus</text>
          <text x="24" y="77">+ enroll()</text>

          <!-- Course -->
          <rect x="140" y="20" width="100" height="70" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <line x1="140" y1="38" x2="240" y2="38" stroke="#2a2620"/>
          <line x1="140" y1="64" x2="240" y2="64" stroke="#2a2620"/>
          <text x="190" y="33" text-anchor="middle" font-family="Caveat" font-size="14">Course</text>
          <text x="144" y="50">- code, name</text><text x="144" y="60">- credits</text>
          <text x="144" y="77">+ syllabus()</text>

          <!-- Teacher -->
          <rect x="260" y="20" width="80" height="70" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <line x1="260" y1="38" x2="340" y2="38" stroke="#2a2620"/>
          <line x1="260" y1="64" x2="340" y2="64" stroke="#2a2620"/>
          <text x="300" y="33" text-anchor="middle" font-family="Caveat" font-size="14">Teacher</text>
          <text x="264" y="50">- id, name</text>
          <text x="264" y="77">+ grade()</text>

          <!-- Session -->
          <rect x="80" y="120" width="100" height="70" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <line x1="80" y1="138" x2="180" y2="138" stroke="#2a2620"/>
          <line x1="80" y1="164" x2="180" y2="164" stroke="#2a2620"/>
          <text x="130" y="133" text-anchor="middle" font-family="Caveat" font-size="14">Session</text>
          <text x="84" y="150">- date, slot</text><text x="84" y="160">- room</text>
          <text x="84" y="177">+ reschedule()</text>

          <!-- Grade -->
          <rect x="200" y="120" width="100" height="70" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <line x1="200" y1="138" x2="300" y2="138" stroke="#2a2620"/>
          <line x1="200" y1="164" x2="300" y2="164" stroke="#2a2620"/>
          <text x="250" y="133" text-anchor="middle" font-family="Caveat" font-size="14">Grade</text>
          <text x="204" y="150">- value</text><text x="204" y="160">- assessmentId</text>
          <text x="204" y="177">+ publish()</text>

          <!-- Invoice -->
          <rect x="140" y="215" width="100" height="65" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <line x1="140" y1="233" x2="240" y2="233" stroke="#2a2620"/>
          <line x1="140" y1="259" x2="240" y2="259" stroke="#2a2620"/>
          <text x="190" y="228" text-anchor="middle" font-family="Caveat" font-size="14">Invoice</text>
          <text x="144" y="245">- amount</text><text x="144" y="255">- status</text>
          <text x="144" y="272">+ remind()</text>

          <!-- relations -->
          <g stroke="#2a2620" fill="none" stroke-width="1.2">
            <line x1="120" y1="55" x2="140" y2="55"/>
            <text x="130" y="50" font-size="9" fill="#5a5247">*..*</text>
            <line x1="240" y1="55" x2="260" y2="55"/>
            <text x="250" y="50" font-size="9" fill="#5a5247">1..*</text>
            <line x1="190" y1="90" x2="160" y2="120"/>
            <text x="180" y="108" font-size="9" fill="#5a5247">1..*</text>
            <line x1="220" y1="90" x2="240" y2="120"/>
            <text x="232" y="108" font-size="9" fill="#5a5247">1..*</text>
            <line x1="70" y1="90" x2="100" y2="120"/>
            <text x="80" y="108" font-size="9" fill="#5a5247">*</text>
            <line x1="70" y1="90" x2="180" y2="215" stroke-dasharray="3 3"/>
            <text x="105" y="160" font-size="9" fill="#5a5247">issues</text>
          </g>
        </g>
      </svg>
      <div class="pros"><span class="plus">defendable scope</span><span class="minus">hides aggregates</span></div>
    </div>

    <!-- Sequence diagram -->
    <div class="wf">
      <div class="wf-tag">UML · sequence</div>
      <h3>Grade publish → notify</h3>
      <div class="wf-sub">Teacher publishes → events flow through bus → students get push.</div>
      <svg viewBox="0 0 360 280" style="width:100%; height:auto; font-family: Kalam, sans-serif;">
        <g font-size="10" fill="#2a2620">
          <!-- heads -->
          <g font-family="Caveat" font-size="13">
            <rect x="10" y="14" width="60" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="40" y="29" text-anchor="middle">Teacher</text>
            <rect x="80" y="14" width="60" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="110" y="29" text-anchor="middle">Gateway</text>
            <rect x="150" y="14" width="60" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="180" y="29" text-anchor="middle">GradeSvc</text>
            <rect x="220" y="14" width="60" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="250" y="29" text-anchor="middle">Bus</text>
            <rect x="290" y="14" width="60" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="320" y="29" text-anchor="middle">NotifSvc</text>
          </g>
          <!-- lifelines -->
          <g stroke="#2a2620" stroke-dasharray="3 4" stroke-width="0.9">
            <line x1="40" y1="36" x2="40" y2="270"/>
            <line x1="110" y1="36" x2="110" y2="270"/>
            <line x1="180" y1="36" x2="180" y2="270"/>
            <line x1="250" y1="36" x2="250" y2="270"/>
            <line x1="320" y1="36" x2="320" y2="270"/>
          </g>
          <!-- messages -->
          <defs>
            <marker id="aseq" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
              <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
            </marker>
          </defs>
          <g stroke="#2a2620" stroke-width="1.3" fill="none" marker-end="url(#aseq)">
            <line x1="40" y1="60" x2="110" y2="60"/><text x="60" y="55">POST /grade</text>
            <line x1="110" y1="90" x2="180" y2="90"/><text x="120" y="85">forward</text>
            <line x1="180" y1="120" x2="180" y2="138" stroke-dasharray="2 2"/><text x="184" y="132" fill="#5a5247">save()</text>
            <line x1="180" y1="160" x2="250" y2="160"/><text x="190" y="155">emit GradePublished</text>
            <line x1="250" y1="190" x2="320" y2="190"/><text x="260" y="185">consume</text>
            <line x1="320" y1="220" x2="40" y2="220" stroke="#D9773C"/><text x="160" y="215" fill="#D9773C">push notification ✦</text>
          </g>
        </g>
      </svg>
      <div class="pros"><span class="plus">shows async</span><span class="minus">one flow only</span></div>
    </div>

    <!-- Deployment diagram -->
    <div class="wf">
      <div class="wf-tag">UML · deployment</div>
      <h3>Where things run</h3>
      <div class="wf-sub">Containers, nodes, managed services. Single cluster, multi-region DB.</div>
      <svg viewBox="0 0 360 280" style="width:100%; height:auto; font-family: Kalam, sans-serif;">
        <g font-size="10" fill="#2a2620">
          <!-- cluster -->
          <rect x="20" y="60" width="240" height="180" fill="rgba(255,255,255,0.4)" stroke="#2a2620" stroke-dasharray="5 4"/>
          <text x="140" y="56" text-anchor="middle" font-family="Caveat" font-size="14">Kubernetes cluster</text>

          <!-- nodes -->
          <rect x="30" y="80" width="100" height="60" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <text x="80" y="95" text-anchor="middle" font-family="Caveat" font-size="13">node-1</text>
          <text x="80" y="110" text-anchor="middle">gateway · identity</text>
          <text x="80" y="124" text-anchor="middle">notif</text>

          <rect x="150" y="80" width="100" height="60" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <text x="200" y="95" text-anchor="middle" font-family="Caveat" font-size="13">node-2</text>
          <text x="200" y="110" text-anchor="middle">academic · grading</text>
          <text x="200" y="124" text-anchor="middle">finance</text>

          <rect x="30" y="160" width="100" height="60" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <text x="80" y="175" text-anchor="middle" font-family="Caveat" font-size="13">node-3</text>
          <text x="80" y="190" text-anchor="middle">Kafka brokers</text>
          <text x="80" y="204" text-anchor="middle">×3</text>

          <rect x="150" y="160" width="100" height="60" fill="rgba(217,119,60,0.10)" stroke="#D9773C"/>
          <text x="200" y="175" text-anchor="middle" font-family="Caveat" font-size="13" fill="#D9773C">node-4 (GPU)</text>
          <text x="200" y="190" text-anchor="middle">AI agent ✦</text>
          <text x="200" y="204" text-anchor="middle">vector store</text>

          <!-- managed -->
          <rect x="280" y="80" width="70" height="60" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <text x="315" y="95" text-anchor="middle" font-family="Caveat" font-size="13">Managed</text>
          <text x="315" y="110" text-anchor="middle">Postgres HA</text>
          <text x="315" y="124" text-anchor="middle">(multi-AZ)</text>

          <rect x="280" y="160" width="70" height="60" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <text x="315" y="175" text-anchor="middle" font-family="Caveat" font-size="13">Storage</text>
          <text x="315" y="190" text-anchor="middle">S3 docs</text>
          <text x="315" y="204" text-anchor="middle">CDN</text>

          <!-- arrows -->
          <g stroke="#2a2620" stroke-width="1.1" fill="none" marker-end="url(#aseq)">
            <line x1="130" y1="110" x2="150" y2="110"/>
            <line x1="250" y1="110" x2="280" y2="110"/>
            <line x1="200" y1="140" x2="200" y2="160"/>
            <line x1="80" y1="140" x2="80" y2="160"/>
            <line x1="250" y1="190" x2="280" y2="190" stroke-dasharray="3 3"/>
          </g>
        </g>
      </svg>
      <div class="pros"><span class="plus">explains the budget line</span><span class="minus">cloud-vendor neutral</span></div>
    </div>
  </div>

  <!-- Event-driven explainer -->
  <div class="lbl h" style="margin-top:18px;">③ Event-driven architecture · the idea</div>
  <div class="grid-2" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Why events?</div>
      <div class="lbl" style="margin-top:6px; line-height:1.5;">
        A service writes <b>what happened</b> as a fact, then forgets who cares. Anyone interested
        subscribes. Add a consumer tomorrow without touching the producer.
      </div>
      <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Wins</div>
      <ul class="lbl sm" style="margin:4px 0 0; padding-left:16px;">
        <li><b>decoupling</b> — grading doesn't know that notifications exist</li>
        <li><b>replay</b> — re-derive any read model from history</li>
        <li><b>parallelism</b> — slow consumers don't slow producers</li>
        <li><b>audit</b> — every event is a permanent record</li>
      </ul>
      <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Costs</div>
      <ul class="lbl sm" style="margin:4px 0 0; padding-left:16px;">
        <li>eventual consistency — UI must show "pending"</li>
        <li>need idempotency keys per consumer</li>
        <li>extra ops surface (Kafka brokers)</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Event catalogue (excerpt)</div>
      <div class="col" style="gap:4px; margin-top:6px;">
        <div class="tile" style="padding:4px 6px;"><span class="lbl mono">StudentEnrolled</span> <span class="lbl sm">→ academic · finance · notif</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl mono">SessionRescheduled</span> <span class="lbl sm">→ notif · AI agent</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl mono">AttendanceRecorded</span> <span class="lbl sm">→ AI agent (cohort risk)</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl mono">GradePublished</span> <span class="lbl sm">→ notif · transcript projector</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl mono">InvoiceIssued</span> <span class="lbl sm">→ notif · ledger</span></div>
        <div class="tile" style="padding:4px 6px;"><span class="lbl mono">PaymentReceived</span> <span class="lbl sm">→ invoice · audit</span></div>
        <div class="tile ai" style="padding:4px 6px;"><span class="lbl mono">ConflictDetected</span> <span class="lbl sm">→ AI agent (proposes move)</span></div>
        <div class="tile ai" style="padding:4px 6px;"><span class="lbl mono">AISuggestionApplied</span> <span class="lbl sm">→ audit · notif</span></div>
      </div>
      <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Outbox pattern guarantees every domain change becomes exactly one event, even if Kafka is down momentarily.</div>
    </div>
  </div>

  <!-- Process → sequence mapping -->
  <div class="lbl h" style="margin-top:22px;">④ Process map → UML sequence · "room change"</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 220" style="width:100%; height:auto;">
      <defs>
        <marker id="amap" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <!-- top: business process -->
        <text x="20" y="20" font-family="Caveat" font-size="16" fill="#5a5247">Business process</text>
        <rect x="20" y="30" width="100" height="36" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="70" y="52" text-anchor="middle">teacher edits</text>
        <rect x="170" y="30" width="100" height="36" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="220" y="52" text-anchor="middle">admin OK</text>
        <rect x="320" y="30" width="100" height="36" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="370" y="52" text-anchor="middle">student informed</text>
        <g stroke="#2a2620" stroke-width="1.4" fill="none" marker-end="url(#amap)">
          <line x1="120" y1="48" x2="170" y2="48"/>
          <line x1="270" y1="48" x2="320" y2="48"/>
        </g>
        <!-- arrow down -->
        <g stroke="#D9773C" stroke-width="1.6" stroke-dasharray="4 4" fill="none" marker-end="url(#amap)">
          <line x1="450" y1="68" x2="450" y2="100"/>
          <text x="460" y="90" fill="#D9773C" font-family="Architects Daughter">maps to →</text>
        </g>
        <!-- bottom: sequence -->
        <text x="20" y="120" font-family="Caveat" font-size="16" fill="#5a5247">UML sequence</text>
        <g font-family="Caveat" font-size="13">
          <rect x="20" y="128" width="60" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="50" y="144" text-anchor="middle">Teacher</text>
          <rect x="130" y="128" width="80" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="170" y="144" text-anchor="middle">AcademicSvc</text>
          <rect x="260" y="128" width="60" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="290" y="144" text-anchor="middle">Bus</text>
          <rect x="370" y="128" width="80" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="410" y="144" text-anchor="middle">NotifSvc</text>
          <rect x="500" y="128" width="80" height="22" fill="rgba(217,119,60,0.12)" stroke="#D9773C"/><text x="540" y="144" text-anchor="middle" fill="#D9773C">AI agent ✦</text>
          <rect x="630" y="128" width="80" height="22" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="670" y="144" text-anchor="middle">Student app</text>
        </g>
        <g stroke="#2a2620" stroke-dasharray="3 4" stroke-width="0.9">
          <line x1="50" y1="150" x2="50" y2="210"/>
          <line x1="170" y1="150" x2="170" y2="210"/>
          <line x1="290" y1="150" x2="290" y2="210"/>
          <line x1="410" y1="150" x2="410" y2="210"/>
          <line x1="540" y1="150" x2="540" y2="210"/>
          <line x1="670" y1="150" x2="670" y2="210"/>
        </g>
        <g stroke="#2a2620" stroke-width="1.3" fill="none" marker-end="url(#amap)" font-size="10">
          <line x1="50" y1="165" x2="170" y2="165"/><text x="65" y="161">edit room</text>
          <line x1="170" y1="180" x2="290" y2="180"/><text x="180" y="176">emit SessionRescheduled</text>
          <line x1="290" y1="195" x2="410" y2="195"/><text x="300" y="191">→ NotifSvc</text>
          <line x1="290" y1="208" x2="540" y2="208" stroke="#D9773C"/><text x="380" y="204" fill="#D9773C">→ AI (log + advise)</text>
          <line x1="410" y1="205" x2="670" y2="205"/><text x="520" y="201">push</text>
        </g>
      </g>
    </svg>
    <div class="lbl sm" style="margin-top:8px; color:var(--ink-soft);">Same "room change" story, two altitudes: the business-process bar at the top is what the brief calls a process map; the swimlane below is the implementation-level sequence the architecture has to support.</div>
  </div>

  <!-- API flow example -->
  <div class="lbl h" style="margin-top:22px;">⑤ API flow · single request walkthrough</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <div class="lbl" style="margin-bottom:8px;">Example: <i>"Lina opens her grades on mobile."</i></div>
    <svg viewBox="0 0 900 140" style="width:100%; height:140px;">
      <defs>
        <marker id="aapi" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <rect x="10" y="50" width="100" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="60" y="72" text-anchor="middle" font-family="Caveat" font-size="14">Mobile app</text>
        <text x="60" y="88" text-anchor="middle" font-size="9">GET /grades</text>

        <rect x="140" y="50" width="100" height="50" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="190" y="72" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">Gateway</text>
        <text x="190" y="88" text-anchor="middle" font-size="9" fill="#5a5247">verify JWT · route</text>

        <rect x="270" y="50" width="100" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="320" y="72" text-anchor="middle" font-family="Caveat" font-size="14">GradeSvc</text>
        <text x="320" y="88" text-anchor="middle" font-size="9">RBAC check</text>

        <ellipse cx="450" cy="75" rx="55" ry="20" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="450" y="78" text-anchor="middle" font-family="Caveat" font-size="14">PG · grades</text>

        <rect x="540" y="50" width="100" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="590" y="72" text-anchor="middle" font-family="Caveat" font-size="14">GradeSvc</text>
        <text x="590" y="88" text-anchor="middle" font-size="9">200 OK + JSON</text>

        <rect x="670" y="20" width="100" height="40" rx="6" fill="rgba(42,38,32,0.06)" stroke="#2a2620" stroke-dasharray="4 4"/>
        <text x="720" y="38" text-anchor="middle" font-family="Caveat" font-size="13">Bus</text>
        <text x="720" y="52" text-anchor="middle" font-size="9">GradeViewed</text>

        <rect x="790" y="50" width="100" height="50" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="840" y="72" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">AI agent ✦</text>
        <text x="840" y="88" text-anchor="middle" font-size="9" fill="#5a5247">cohort signal</text>

        <g stroke="#2a2620" stroke-width="1.3" fill="none" marker-end="url(#aapi)">
          <line x1="110" y1="75" x2="140" y2="75"/>
          <line x1="240" y1="75" x2="270" y2="75"/>
          <line x1="370" y1="75" x2="395" y2="75"/>
          <line x1="505" y1="75" x2="540" y2="75"/>
          <line x1="640" y1="75" x2="670" y2="75" stroke-dasharray="3 3"/>
          <line x1="720" y1="60" x2="790" y2="70" stroke="#D9773C" stroke-dasharray="3 3"/>
        </g>
      </g>
    </svg>
    <div class="grid-4" style="margin-top:8px;">
      <div class="tile" style="padding:6px 8px;"><span class="lbl sm"><b>1.</b> request signed with JWT</span></div>
      <div class="tile" style="padding:6px 8px;"><span class="lbl sm"><b>2.</b> gateway verifies + routes</span></div>
      <div class="tile" style="padding:6px 8px;"><span class="lbl sm"><b>3.</b> service queries its DB</span></div>
      <div class="tile" style="padding:6px 8px;"><span class="lbl sm"><b>4.</b> response &lt; 200ms · event for AI</span></div>
    </div>
  </div>

  <!-- Database ownership -->
  <div class="lbl h" style="margin-top:22px;">⑥ Database ownership · one DB per service</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 1fr 1fr 1fr 2fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Service</div>
      <div class="lbl sm" style="font-weight:700;">Owns</div>
      <div class="lbl sm" style="font-weight:700;">Engine</div>
      <div class="lbl sm" style="font-weight:700;">Why</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Identity</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">users · roles · scopes</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Postgres</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">relational, small, audited</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Academic</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">courses · sessions · rooms · attendance</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Postgres</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">joins everywhere, FK heavy</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Grading</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">assessments · grades · transcripts</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Postgres</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">ACID for academic record</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Finance</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">invoices · payments · ledger</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Postgres</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">ACID for money</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Notifications</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">delivery log · preferences</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Mongo</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">flexible payload, high write volume</span></div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI agent ✦</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">conversation log · embeddings</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">pgvector + Mongo</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">vector similarity + flexible logs</span></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color:var(--ink-soft);">Rule: <b>no service reads another service's DB directly</b>. Cross-domain data flows via API or events. Stops shared-DB coupling from creeping back in.</div>
  </div>

  <!-- Failure handling / resilience -->
  <div class="lbl h" style="margin-top:22px;">⑦ Failure handling &amp; resilience</div>
  <div class="grid-4" style="margin-top:6px;">
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Retries</div>
      <div class="lbl sm" style="margin-top:4px;">Exponential backoff for transient errors (network blip, DB lock). Capped at 3 attempts.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Dead-letter queue</div>
      <div class="lbl sm" style="margin-top:4px;">Messages that keep failing after retries get parked in a DLQ — humans inspect, fix, replay.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Health checks</div>
      <div class="lbl sm" style="margin-top:4px;">Each pod exposes <span class="lbl mono">/healthz</span> + <span class="lbl mono">/readyz</span>. K8s removes sick pods from rotation automatically.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Circuit breakers + fallback</div>
      <div class="lbl sm" style="margin-top:4px;">If GradeSvc is down, dashboard shows cached values + "data may be stale" banner — graceful degradation.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Idempotency keys</div>
      <div class="lbl sm" style="margin-top:4px;">Every write carries a key — replaying a Kafka event twice produces one DB write.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Outbox pattern</div>
      <div class="lbl sm" style="margin-top:4px;">Domain write + event published atomically in one DB transaction. Bus can be momentarily down.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Multi-AZ DB</div>
      <div class="lbl sm" style="margin-top:4px;">Managed PG with hot standby in second availability zone. RPO ~ 0, RTO &lt; 60s.</div>
    </div>
    <div class="frame pad ai" style="padding:10px; border:2px solid var(--accent); background: repeating-linear-gradient(45deg, rgba(217,119,60,0.10) 0 6px, transparent 6px 12px);">
      <div class="lbl h">AI fallback ✦</div>
      <div class="lbl sm" style="margin-top:4px;">If model is unavailable, agent surfaces "AI unavailable — manual mode" and disables Apply buttons. Never blocks the user.</div>
    </div>
  </div>

  <!-- Service discovery / load balancing -->
  <div class="lbl h" style="margin-top:22px;">⑧ Service discovery &amp; load balancing</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 200" style="width:100%; height:auto;">
      <defs>
        <marker id="adisc" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <rect x="40" y="80" width="100" height="40" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="90" y="104" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">Gateway</text>

        <rect x="200" y="80" width="120" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="260" y="98" text-anchor="middle" font-family="Caveat" font-size="13">K8s Service</text>
        <text x="260" y="113" text-anchor="middle" font-size="9" fill="#5a5247">DNS-based discovery</text>

        <g>
          <rect x="400" y="20" width="100" height="36" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <text x="450" y="42" text-anchor="middle">grade-pod-1</text>
          <rect x="400" y="80" width="100" height="36" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <text x="450" y="102" text-anchor="middle">grade-pod-2</text>
          <rect x="400" y="140" width="100" height="36" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
          <text x="450" y="162" text-anchor="middle">grade-pod-3</text>
        </g>

        <rect x="550" y="60" width="140" height="80" rx="6" fill="rgba(255,255,255,0.4)" stroke="#2a2620" stroke-dasharray="4 4"/>
        <text x="620" y="80" text-anchor="middle" font-family="Caveat" font-size="13">HPA</text>
        <text x="620" y="100" text-anchor="middle" font-size="9" fill="#5a5247">CPU &gt; 70%?</text>
        <text x="620" y="115" text-anchor="middle" font-size="9" fill="#5a5247">queue depth?</text>
        <text x="620" y="130" text-anchor="middle" font-size="10" fill="#D9773C">add a pod</text>

        <rect x="720" y="80" width="140" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="790" y="98" text-anchor="middle" font-family="Caveat" font-size="13">Ingress · TLS</text>
        <text x="790" y="113" text-anchor="middle" font-size="9" fill="#5a5247">external load balancer</text>

        <g stroke="#2a2620" stroke-width="1.3" fill="none" marker-end="url(#adisc)">
          <line x1="140" y1="100" x2="200" y2="100"/>
          <line x1="320" y1="100" x2="395" y2="38"/>
          <line x1="320" y1="100" x2="395" y2="98"/>
          <line x1="320" y1="100" x2="395" y2="158"/>
          <line x1="500" y1="100" x2="550" y2="100" stroke-dasharray="3 3"/>
          <line x1="690" y1="100" x2="720" y2="100"/>
        </g>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:8px;">
      <div class="tile"><div class="lbl h">Discovery</div><div class="lbl sm">K8s assigns each service a DNS name. New pods register automatically — no config to update.</div></div>
      <div class="tile"><div class="lbl h">Load balancing</div><div class="lbl sm">Round-robin across healthy pods. Gateway uses keep-alive; ingress terminates TLS.</div></div>
      <div class="tile"><div class="lbl h">Autoscale</div><div class="lbl sm">HPA watches CPU + queue depth; adds pods within 30s of load spike. Scales back down off-peak.</div></div>
    </div>
  </div>

  <!-- C4 -->
  <div class="lbl h" style="margin-top:22px;">⑨ C4 model · Context · Container · Component</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="wf" style="padding:10px 12px;">
      <div class="wf-tag">C1 · context</div>
      <h3>Who uses it</h3>
      <div class="wf-sub">Zoomed all the way out. 4 actors, 1 system, 3 external services.</div>
      <svg viewBox="0 0 280 180" style="width:100%; height:auto;">
        <g font-family="Kalam" font-size="10" fill="#2a2620">
          <rect x="90" y="60" width="100" height="60" rx="8" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
          <text x="140" y="85" text-anchor="middle" font-family="Caveat" font-size="13" fill="#D9773C">NovaCampus</text>
          <text x="140" y="100" text-anchor="middle" font-size="9" fill="#5a5247">[Software System]</text>
          <circle cx="30" cy="40" r="8" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="30" y="60" text-anchor="middle">Student</text>
          <circle cx="30" cy="100" r="8" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="30" y="120" text-anchor="middle">Teacher</text>
          <circle cx="30" cy="160" r="8" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/><text x="30" y="178" text-anchor="middle">Admin / Mgmt</text>
          <rect x="220" y="20" width="50" height="20" stroke="#2a2620" fill="none" stroke-dasharray="3 3"/><text x="245" y="34" text-anchor="middle">Pay GW</text>
          <rect x="220" y="80" width="50" height="20" stroke="#2a2620" fill="none" stroke-dasharray="3 3"/><text x="245" y="94" text-anchor="middle">Email/SMS</text>
          <rect x="220" y="140" width="50" height="20" stroke="#2a2620" fill="none" stroke-dasharray="3 3"/><text x="245" y="154" text-anchor="middle">OIDC IdP</text>
          <g stroke="#2a2620" stroke-width="1" fill="none">
            <line x1="40" y1="40" x2="90" y2="80"/>
            <line x1="40" y1="100" x2="90" y2="90"/>
            <line x1="40" y1="160" x2="90" y2="110"/>
            <line x1="190" y1="80" x2="220" y2="30"/>
            <line x1="190" y1="90" x2="220" y2="90"/>
            <line x1="190" y1="100" x2="220" y2="150"/>
          </g>
        </g>
      </svg>
    </div>
    <div class="wf" style="padding:10px 12px;">
      <div class="wf-tag">C2 · container</div>
      <h3>What runs where</h3>
      <div class="wf-sub">Zoom in one level: SPA, mobile, gateway, services, DBs.</div>
      <svg viewBox="0 0 280 180" style="width:100%; height:auto;">
        <g font-family="Kalam" font-size="9" fill="#2a2620">
          <rect x="10" y="10" width="60" height="22" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="40" y="24" text-anchor="middle">SPA</text>
          <rect x="10" y="40" width="60" height="22" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="40" y="54" text-anchor="middle">Mobile</text>
          <rect x="90" y="25" width="60" height="22" stroke="#D9773C" fill="rgba(217,119,60,0.10)"/><text x="120" y="39" text-anchor="middle" fill="#D9773C">Gateway</text>
          <rect x="170" y="5" width="60" height="20" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="200" y="18" text-anchor="middle">Identity</text>
          <rect x="170" y="30" width="60" height="20" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="200" y="43" text-anchor="middle">Academic</text>
          <rect x="170" y="55" width="60" height="20" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="200" y="68" text-anchor="middle">Grading</text>
          <rect x="170" y="80" width="60" height="20" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="200" y="93" text-anchor="middle">Finance</text>
          <rect x="170" y="105" width="60" height="20" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="200" y="118" text-anchor="middle">Notif</text>
          <rect x="170" y="130" width="60" height="20" stroke="#D9773C" fill="rgba(217,119,60,0.10)"/><text x="200" y="143" text-anchor="middle" fill="#D9773C">AI ✦</text>
          <rect x="100" y="120" width="50" height="40" stroke="#2a2620" fill="rgba(42,38,32,0.06)" stroke-dasharray="3 3"/><text x="125" y="142" text-anchor="middle">Kafka</text>
          <ellipse cx="250" cy="170" rx="25" ry="8" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="250" y="172" text-anchor="middle">PG/Mongo</text>
        </g>
      </svg>
    </div>
    <div class="wf" style="padding:10px 12px;">
      <div class="wf-tag">C3 · component</div>
      <h3>Inside one container</h3>
      <div class="wf-sub">Zoom into GradingSvc: controller → service → repo → DB.</div>
      <svg viewBox="0 0 280 180" style="width:100%; height:auto;">
        <g font-family="Kalam" font-size="10" fill="#2a2620">
          <rect x="20" y="20" width="240" height="140" stroke="#2a2620" stroke-dasharray="4 3" fill="rgba(255,255,255,0.3)"/>
          <text x="140" y="14" text-anchor="middle" font-family="Caveat" font-size="13" fill="#5a5247">GradingSvc · [Container]</text>
          <rect x="40" y="40" width="200" height="22" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="140" y="55" text-anchor="middle">GradesController · REST</text>
          <rect x="40" y="68" width="200" height="22" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="140" y="83" text-anchor="middle">GradingService · domain logic</text>
          <rect x="40" y="96" width="200" height="22" stroke="#2a2620" fill="rgba(255,255,255,0.6)"/><text x="140" y="111" text-anchor="middle">GradeRepository · persistence</text>
          <rect x="40" y="124" width="200" height="22" stroke="#D9773C" fill="rgba(217,119,60,0.10)"/><text x="140" y="139" text-anchor="middle" fill="#D9773C">EventPublisher → Kafka</text>
        </g>
      </svg>
    </div>
  </div>
  <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">C4 zooms progressively: <b>Context</b> (who uses it) → <b>Container</b> (deployable units) → <b>Component</b> (inside one container) → Code (rarely diagrammed). Same notation at every zoom level.</div>

  <!-- ERD -->
  <div class="lbl h" style="margin-top:22px;">⑩ Entity-relationship diagram · the data model</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 480" style="width:100%; height:auto;">
      <defs>
        <marker id="aerd" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="10" fill="#2a2620">

        <!-- Student -->
        <rect x="40" y="40" width="140" height="120" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="40" y1="62" x2="180" y2="62" stroke="#2a2620"/>
        <text x="110" y="56" text-anchor="middle" font-family="Caveat" font-size="16">Student</text>
        <text x="46" y="76">PK id</text>
        <text x="46" y="90">FK campusId</text>
        <text x="46" y="104">firstName, lastName</text>
        <text x="46" y="118">email · phone</text>
        <text x="46" y="132">enrollmentDate</text>
        <text x="46" y="146">status</text>

        <!-- Teacher -->
        <rect x="380" y="40" width="140" height="100" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="380" y1="62" x2="520" y2="62" stroke="#2a2620"/>
        <text x="450" y="56" text-anchor="middle" font-family="Caveat" font-size="16">Teacher</text>
        <text x="386" y="76">PK id</text>
        <text x="386" y="90">FK campusId</text>
        <text x="386" y="104">firstName, lastName</text>
        <text x="386" y="118">email</text>
        <text x="386" y="132">specialization</text>

        <!-- Course -->
        <rect x="720" y="40" width="140" height="110" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="720" y1="62" x2="860" y2="62" stroke="#2a2620"/>
        <text x="790" y="56" text-anchor="middle" font-family="Caveat" font-size="16">Course</text>
        <text x="726" y="76">PK id</text>
        <text x="726" y="90">code · name</text>
        <text x="726" y="104">credits</text>
        <text x="726" y="118">FK teacherId</text>
        <text x="726" y="132">FK programId</text>

        <!-- Room -->
        <rect x="40" y="220" width="140" height="90" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="40" y1="242" x2="180" y2="242" stroke="#2a2620"/>
        <text x="110" y="236" text-anchor="middle" font-family="Caveat" font-size="16">Room</text>
        <text x="46" y="256">PK id</text>
        <text x="46" y="270">FK campusId</text>
        <text x="46" y="284">code · capacity</text>
        <text x="46" y="298">equipment</text>

        <!-- Schedule -->
        <rect x="240" y="220" width="160" height="120" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="240" y1="242" x2="400" y2="242" stroke="#2a2620"/>
        <text x="320" y="236" text-anchor="middle" font-family="Caveat" font-size="16">Schedule (Session)</text>
        <text x="246" y="256">PK id</text>
        <text x="246" y="270">FK courseId</text>
        <text x="246" y="284">FK teacherId</text>
        <text x="246" y="298">FK roomId</text>
        <text x="246" y="312">date · startTime</text>
        <text x="246" y="326">endTime · status</text>

        <!-- Grade -->
        <rect x="460" y="220" width="160" height="110" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="460" y1="242" x2="620" y2="242" stroke="#2a2620"/>
        <text x="540" y="236" text-anchor="middle" font-family="Caveat" font-size="16">Grade</text>
        <text x="466" y="256">PK id</text>
        <text x="466" y="270">FK studentId</text>
        <text x="466" y="284">FK courseId</text>
        <text x="466" y="298">FK assessmentId</text>
        <text x="466" y="312">value · publishedAt</text>

        <!-- Attendance -->
        <rect x="680" y="220" width="160" height="100" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="680" y1="242" x2="840" y2="242" stroke="#2a2620"/>
        <text x="760" y="236" text-anchor="middle" font-family="Caveat" font-size="16">Attendance</text>
        <text x="686" y="256">PK id</text>
        <text x="686" y="270">FK studentId</text>
        <text x="686" y="284">FK sessionId</text>
        <text x="686" y="298">status · note</text>

        <!-- Enrollment (junction) -->
        <rect x="200" y="40" width="160" height="100" fill="rgba(255,255,255,0.5)" stroke="#2a2620" stroke-width="1.6" stroke-dasharray="4 3"/>
        <line x1="200" y1="62" x2="360" y2="62" stroke="#2a2620"/>
        <text x="280" y="56" text-anchor="middle" font-family="Caveat" font-size="16">Enrollment</text>
        <text x="206" y="76">PK id · junction</text>
        <text x="206" y="90">FK studentId</text>
        <text x="206" y="104">FK courseId</text>
        <text x="206" y="118">enrolledAt</text>
        <text x="206" y="132">status</text>

        <!-- Invoice / Payment -->
        <rect x="40" y="370" width="140" height="100" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="40" y1="392" x2="180" y2="392" stroke="#2a2620"/>
        <text x="110" y="386" text-anchor="middle" font-family="Caveat" font-size="16">Invoice</text>
        <text x="46" y="406">PK id</text>
        <text x="46" y="420">FK studentId</text>
        <text x="46" y="434">amount · dueDate</text>
        <text x="46" y="448">status · period</text>

        <rect x="240" y="370" width="140" height="100" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="240" y1="392" x2="380" y2="392" stroke="#2a2620"/>
        <text x="310" y="386" text-anchor="middle" font-family="Caveat" font-size="16">Payment</text>
        <text x="246" y="406">PK id</text>
        <text x="246" y="420">FK invoiceId</text>
        <text x="246" y="434">amount · method</text>
        <text x="246" y="448">paidAt · receipt#</text>

        <!-- Notification -->
        <rect x="440" y="370" width="160" height="100" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <line x1="440" y1="392" x2="600" y2="392" stroke="#2a2620"/>
        <text x="520" y="386" text-anchor="middle" font-family="Caveat" font-size="16">Notification</text>
        <text x="446" y="406">PK id</text>
        <text x="446" y="420">FK userId · channel</text>
        <text x="446" y="434">type · payload</text>
        <text x="446" y="448">sentAt · readAt</text>

        <!-- Audit log -->
        <rect x="660" y="370" width="180" height="100" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <line x1="660" y1="392" x2="840" y2="392" stroke="#D9773C"/>
        <text x="750" y="386" text-anchor="middle" font-family="Caveat" font-size="16" fill="#D9773C">AuditLog ✦</text>
        <text x="666" y="406">PK id</text>
        <text x="666" y="420">FK actorId · target</text>
        <text x="666" y="434">action · before/after</text>
        <text x="666" y="448">aiSourced · at</text>

        <!-- relationships with cardinality -->
        <g stroke="#2a2620" stroke-width="1.2" fill="none">
          <!-- Student-Enrollment 1..N -->
          <line x1="180" y1="100" x2="200" y2="100"/>
          <text x="184" y="94" font-size="9" fill="#5a5247">1</text>
          <text x="194" y="94" font-size="9" fill="#5a5247">N</text>
          <!-- Enrollment-Course N..1 -->
          <line x1="360" y1="100" x2="720" y2="100"/>
          <text x="700" y="94" font-size="9" fill="#5a5247">1</text>
          <text x="364" y="94" font-size="9" fill="#5a5247">N</text>
          <!-- Teacher-Course 1..N -->
          <line x1="520" y1="120" x2="720" y2="120"/>
          <text x="700" y="115" font-size="9" fill="#5a5247">1</text>
          <text x="524" y="115" font-size="9" fill="#5a5247">N</text>
          <!-- Course-Schedule 1..N -->
          <line x1="790" y1="150" x2="400" y2="250"/>
          <text x="790" y="160" font-size="9" fill="#5a5247">1</text>
          <text x="395" y="245" font-size="9" fill="#5a5247">N</text>
          <!-- Room-Schedule 1..N -->
          <line x1="180" y1="270" x2="240" y2="270"/>
          <text x="183" y="265" font-size="9" fill="#5a5247">1</text>
          <text x="232" y="265" font-size="9" fill="#5a5247">N</text>
          <!-- Schedule-Attendance 1..N -->
          <line x1="400" y1="290" x2="680" y2="290"/>
          <text x="403" y="285" font-size="9" fill="#5a5247">1</text>
          <text x="672" y="285" font-size="9" fill="#5a5247">N</text>
          <!-- Student-Grade 1..N (curve) -->
          <path d="M 110,160 C 110,200 540,200 540,220"/>
          <text x="114" y="172" font-size="9" fill="#5a5247">1</text>
          <text x="535" y="218" font-size="9" fill="#5a5247">N</text>
          <!-- Course-Grade 1..N -->
          <line x1="790" y1="150" x2="620" y2="250"/>
          <text x="785" y="158" font-size="9" fill="#5a5247">1</text>
          <text x="615" y="245" font-size="9" fill="#5a5247">N</text>
          <!-- Student-Attendance 1..N (curve) -->
          <path d="M 110,160 C 110,200 760,200 760,220"/>
          <text x="120" y="175" font-size="9" fill="#5a5247">1</text>
          <text x="755" y="218" font-size="9" fill="#5a5247">N</text>
          <!-- Student-Invoice 1..N -->
          <line x1="110" y1="160" x2="110" y2="370"/>
          <text x="114" y="168" font-size="9" fill="#5a5247">1</text>
          <text x="114" y="365" font-size="9" fill="#5a5247">N</text>
          <!-- Invoice-Payment 1..N -->
          <line x1="180" y1="420" x2="240" y2="420"/>
          <text x="184" y="415" font-size="9" fill="#5a5247">1</text>
          <text x="232" y="415" font-size="9" fill="#5a5247">N</text>
          <!-- Notification → User (any) dashed -->
          <path d="M 110,160 C 200,300 400,360 440,400" stroke-dasharray="3 3"/>
          <text x="440" y="396" font-size="9" fill="#5a5247">N</text>
        </g>

        <!-- Audit dashed lines to all -->
        <g stroke="#D9773C" stroke-width="1.1" fill="none" stroke-dasharray="3 4">
          <path d="M660,420 C580,420 580,330 540,330"/>
          <path d="M660,440 C580,440 380,360 380,340"/>
          <path d="M660,460 C580,470 180,460 180,440"/>
        </g>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:8px;">
      <div class="tile"><div class="lbl h">8 + 2 entities</div><div class="lbl sm">8 core (Student, Teacher, Course, Schedule, Room, Grade, Invoice, Notification) + Enrollment junction + Audit</div></div>
      <div class="tile"><div class="lbl h">Cardinality</div><div class="lbl sm">N:M flattened via junctions (Student ↔ Course via Enrollment); 1:N elsewhere</div></div>
      <div class="tile ai"><div class="lbl h">Audit ✦</div><div class="lbl sm">every write spawns an AuditLog row; <span class="lbl mono">aiSourced</span> flag tells if the change came from a human-approved AI action</div></div>
    </div>
  </div>

  <!-- AI request lifecycle -->
  <div class="lbl h" style="margin-top:22px;">⑪ AI request lifecycle · one journey from prompt to action</div>
  <div class="frame pad ai" style="padding:14px; margin-top:6px; border:2px solid var(--accent); background: repeating-linear-gradient(45deg, rgba(217,119,60,0.06) 0 6px, transparent 6px 12px);">
    <svg viewBox="0 0 900 280" style="width:100%; height:auto;">
      <defs>
        <marker id="aai" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#D9773C"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">

        <!-- 1 user -->
        <rect x="20" y="40" width="110" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="75" y="58" text-anchor="middle" font-family="Caveat" font-size="14">① User action</text>
        <text x="75" y="78" text-anchor="middle" font-size="9" fill="#5a5247">"resolve conflict"</text>

        <!-- 2 ai gateway -->
        <rect x="160" y="40" width="120" height="50" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
        <text x="220" y="58" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">② AI gateway</text>
        <text x="220" y="78" text-anchor="middle" font-size="9" fill="#5a5247">auth · scope · rate-limit</text>

        <!-- 3 retrieval / RAG -->
        <rect x="310" y="40" width="120" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="370" y="58" text-anchor="middle" font-family="Caveat" font-size="14">③ Retrieval · RAG</text>
        <text x="370" y="78" text-anchor="middle" font-size="9" fill="#5a5247">vector + scoped SQL</text>

        <!-- 4 prompt assembly -->
        <rect x="460" y="40" width="120" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="520" y="58" text-anchor="middle" font-family="Caveat" font-size="14">④ Prompt build</text>
        <text x="520" y="78" text-anchor="middle" font-size="9" fill="#5a5247">PII tokenised</text>

        <!-- 5 LLM -->
        <rect x="610" y="40" width="120" height="50" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
        <text x="670" y="58" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">⑤ LLM call</text>
        <text x="670" y="78" text-anchor="middle" font-size="9" fill="#5a5247">model + tools</text>

        <!-- 6 tool exec -->
        <rect x="760" y="40" width="130" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="825" y="58" text-anchor="middle" font-family="Caveat" font-size="14">⑥ Tool execute</text>
        <text x="825" y="78" text-anchor="middle" font-size="9" fill="#5a5247">deterministic checks</text>

        <!-- row 2 -->
        <!-- 7 validation -->
        <rect x="760" y="140" width="130" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="825" y="158" text-anchor="middle" font-family="Caveat" font-size="14">⑦ Validation</text>
        <text x="825" y="178" text-anchor="middle" font-size="9" fill="#5a5247">business rules · scope</text>

        <!-- 8 detokenise + response -->
        <rect x="600" y="140" width="130" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="665" y="158" text-anchor="middle" font-family="Caveat" font-size="14">⑧ De-tokenise</text>
        <text x="665" y="178" text-anchor="middle" font-size="9" fill="#5a5247">restore PII inside perimeter</text>

        <!-- 9 propose to user -->
        <rect x="440" y="140" width="140" height="50" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
        <text x="510" y="158" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">⑨ Propose</text>
        <text x="510" y="178" text-anchor="middle" font-size="9" fill="#5a5247">show diff + reasons</text>

        <!-- 10 human approves -->
        <rect x="290" y="140" width="130" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="355" y="158" text-anchor="middle" font-family="Caveat" font-size="14">⑩ Human approves</text>
        <text x="355" y="178" text-anchor="middle" font-size="9" fill="#5a5247">Apply / Edit / Decline</text>

        <!-- 11 commit + event -->
        <rect x="140" y="140" width="130" height="50" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="205" y="158" text-anchor="middle" font-family="Caveat" font-size="14">⑪ Commit</text>
        <text x="205" y="178" text-anchor="middle" font-size="9" fill="#5a5247">DB write · emit event</text>

        <!-- 12 audit log -->
        <rect x="20" y="140" width="100" height="50" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
        <text x="70" y="158" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">⑫ Audit ✦</text>
        <text x="70" y="178" text-anchor="middle" font-size="9" fill="#5a5247">aiSourced=true</text>

        <!-- arrows row 1 -->
        <g stroke="#D9773C" stroke-width="1.4" fill="none" marker-end="url(#aai)">
          <line x1="130" y1="65" x2="160" y2="65"/>
          <line x1="280" y1="65" x2="310" y2="65"/>
          <line x1="430" y1="65" x2="460" y2="65"/>
          <line x1="580" y1="65" x2="610" y2="65"/>
          <line x1="730" y1="65" x2="760" y2="65"/>
        </g>

        <!-- arrow down -->
        <path d="M 825,90 L 825,140" stroke="#D9773C" stroke-width="1.4" fill="none" stroke-dasharray="3 3" marker-end="url(#aai)"/>

        <!-- arrows row 2 (right to left) -->
        <g stroke="#D9773C" stroke-width="1.4" fill="none" marker-end="url(#aai)">
          <line x1="760" y1="165" x2="730" y2="165"/>
          <line x1="600" y1="165" x2="580" y2="165"/>
          <line x1="440" y1="165" x2="420" y2="165"/>
          <line x1="290" y1="165" x2="270" y2="165"/>
          <line x1="140" y1="165" x2="120" y2="165"/>
        </g>

        <!-- bottom row callouts -->
        <g font-family="Architects Daughter" font-size="11" fill="#5a5247">
          <text x="220" y="120" text-anchor="middle">↓ inside our perimeter</text>
          <text x="670" y="120" text-anchor="middle">↓ only place model sees data</text>
        </g>

        <!-- key principles -->
        <g>
          <rect x="20" y="230" width="200" height="36" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="120" y="252" text-anchor="middle">scope inherited from caller</text>
          <rect x="240" y="230" width="200" height="36" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="340" y="252" text-anchor="middle">no PII leaves the perimeter</text>
          <rect x="460" y="230" width="200" height="36" rx="4" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="560" y="252" text-anchor="middle">tools enforce business rules</text>
          <rect x="680" y="230" width="200" height="36" rx="4" fill="rgba(217,119,60,0.12)" stroke="#D9773C"/>
          <text x="780" y="252" text-anchor="middle" fill="#D9773C">human approves before commit ✦</text>
        </g>
      </g>
    </svg>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">12 steps · 4 invariants. The model never writes to a DB; it only proposes. The audit log is the receipt.</div>
  </div>
</section>

<!-- ============ LOT 5 · TECH ============ -->
<section class="tab-pane" data-pane="tech">
  <div class="pane-head">
    <div>
      <h2>Tech choices</h2>
      <p>What we use, why, and what we deliberately said no to. Justifications structured for the defense panel.</p>
    </div>
    <div class="legend"><b>Sections</b><br>stack · comparisons · security<br>scalability · deployment</div>
  </div>

  <!-- Stack table -->
  <div class="lbl h">① Stack at a glance</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 130px 1fr 2fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Layer</div>
      <div class="lbl sm" style="font-weight:700;">Choice</div>
      <div class="lbl sm" style="font-weight:700;">Why (one-liner)</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Frontend</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">React + Vite</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">team familiarity · large ecosystem · role-based UIs</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Mobile</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">React Native</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">share code with web · push notifs · cheap iteration</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">API</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">REST + OpenAPI</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">defendable, well-understood, mock-friendly for demo</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Services</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">Node (NestJS) + Python (AI)</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">JS for CRUD speed, Python where the ML lives</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">DB · primary</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">PostgreSQL</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">relational integrity for academic + finance</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">DB · secondary</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">MongoDB · pgvector</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">audit logs + AI context embeddings</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Bus</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">Kafka</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">durable events · replay · industry standard</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Auth</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">JWT + OAuth2/OIDC · RBAC</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">stateless, multi-campus scope claims</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Deploy</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl">Docker · K8s · GitHub Actions</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">reproducible · scale per service · cheap CI</span></div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl">LLM API + rules + tools ✦</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">hosted model for language, deterministic tools for actions</span></div>
    </div>
  </div>

  <!-- Comparisons -->
  <div class="lbl h" style="margin-top:18px;">② Comparisons — what we said no to</div>
  <div class="variants" style="margin-top:6px;">
    <div class="wf">
      <div class="wf-tag">vs.</div>
      <h3>Monolith vs Microservices</h3>
      <div class="grid-2" style="margin-top:6px;">
        <div class="frame pad" style="padding:6px;">
          <div class="lbl h">Monolith</div>
          <div class="lbl sm">+ simple deploy<br>+ fast at start<br>− single failure surface<br>− team contention</div>
        </div>
        <div class="frame pad accent" style="padding:6px; border-color: var(--accent);">
          <div class="lbl h">Microservices ✓</div>
          <div class="lbl sm">+ scale per module<br>+ tech per service<br>− ops overhead<br>− eventual consistency</div>
        </div>
      </div>
      <div class="lbl sm" style="margin-top:8px;">Picked microservices because finance/AI/notif have wildly different load profiles &amp; data lifetimes.</div>
    </div>

    <div class="wf">
      <div class="wf-tag">vs.</div>
      <h3>Postgres vs Mongo</h3>
      <div class="grid-2" style="margin-top:6px;">
        <div class="frame pad accent" style="padding:6px; border-color: var(--accent);">
          <div class="lbl h">Postgres ✓</div>
          <div class="lbl sm">+ ACID for grades / €<br>+ joins everywhere<br>− schema migrations<br>− doc-heavy is awkward</div>
        </div>
        <div class="frame pad" style="padding:6px;">
          <div class="lbl h">Mongo</div>
          <div class="lbl sm">+ flexible docs<br>+ logs / events fit<br>− eventual joins<br>− weaker $$ guarantees</div>
        </div>
      </div>
      <div class="lbl sm" style="margin-top:8px;">Use both. PG for system of record. Mongo for audit logs &amp; flexible payloads. pgvector for AI memory.</div>
    </div>

    <div class="wf">
      <div class="wf-tag">vs.</div>
      <h3>REST vs GraphQL</h3>
      <div class="grid-2" style="margin-top:6px;">
        <div class="frame pad accent" style="padding:6px; border-color: var(--accent);">
          <div class="lbl h">REST ✓</div>
          <div class="lbl sm">+ team knows it<br>+ caches well<br>− N+1 on dashboards<br>− versioning ceremony</div>
        </div>
        <div class="frame pad" style="padding:6px;">
          <div class="lbl h">GraphQL</div>
          <div class="lbl sm">+ flexible UIs<br>+ single endpoint<br>− new infra<br>− security learning curve</div>
        </div>
      </div>
      <div class="lbl sm" style="margin-top:8px;">REST first. Gateway aggregates for heavy dashboards. Revisit GraphQL in year 2 if UI flex demands it.</div>
    </div>
  </div>

  <!-- Security model -->
  <div class="lbl h" style="margin-top:18px;">③ Security model · JWT + RBAC</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 800 200" style="width:100%; height:auto;">
      <defs>
        <marker id="asec" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="12" fill="#2a2620">
        <rect x="20" y="80" width="120" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
        <text x="80" y="105" text-anchor="middle" font-family="Caveat" font-size="18">User</text>

        <rect x="180" y="80" width="140" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
        <text x="250" y="105" text-anchor="middle" font-family="Caveat" font-size="18">OIDC provider</text>

        <rect x="360" y="80" width="140" height="40" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
        <text x="430" y="105" text-anchor="middle" font-family="Caveat" font-size="18" fill="#D9773C">JWT (signed)</text>

        <rect x="540" y="40" width="180" height="50" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
        <text x="630" y="60" text-anchor="middle" font-family="Caveat" font-size="16">Gateway · verify + scope</text>
        <text x="630" y="78" text-anchor="middle" font-size="10" fill="#5a5247">roles · campusIds · exp</text>

        <rect x="540" y="110" width="180" height="50" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
        <text x="630" y="130" text-anchor="middle" font-family="Caveat" font-size="16">Service · RBAC check</text>
        <text x="630" y="148" text-anchor="middle" font-size="10" fill="#5a5247">policy: can(role, action, scope)</text>

        <g stroke="#2a2620" stroke-width="1.4" fill="none" marker-end="url(#asec)">
          <path d="M140,100 L180,100"/>
          <path d="M320,100 L360,100"/>
          <path d="M500,100 C520,100 530,65 540,65"/>
          <path d="M500,100 C520,100 530,135 540,135"/>
        </g>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:8px;">
      <div class="tile"><div class="lbl h">Roles</div><div class="lbl sm">student · teacher · admin · mgmt · super</div></div>
      <div class="tile"><div class="lbl h">Scopes</div><div class="lbl sm">campusId(s) · programId(s) · classId(s)</div></div>
      <div class="tile ai"><div class="lbl h">✦ AI guardrail</div><div class="lbl sm">agent inherits caller's scope · never escalates</div></div>
    </div>
  </div>

  <!-- Scalability -->
  <div class="lbl h" style="margin-top:18px;">④ Scalability · how this grows from 4 → 8 campuses</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 800 200" style="width:100%; height:auto;">
      <defs>
        <marker id="ascal" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <!-- horiz scale -->
        <rect x="20" y="20" width="240" height="160" fill="rgba(255,255,255,0.4)" stroke="#2a2620" stroke-dasharray="5 4"/>
        <text x="140" y="38" text-anchor="middle" font-family="Caveat" font-size="16">① Horizontal · stateless pods</text>
        <g>
          <rect x="40" y="60" width="50" height="30" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="65" y="78" text-anchor="middle" font-size="10">academic</text>
          <rect x="100" y="60" width="50" height="30" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="125" y="78" text-anchor="middle" font-size="10">academic</text>
          <rect x="160" y="60" width="50" height="30" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="185" y="78" text-anchor="middle" font-size="10">academic</text>
          <rect x="40" y="105" width="50" height="30" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="65" y="123" text-anchor="middle" font-size="10">grading</text>
          <rect x="100" y="105" width="50" height="30" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="125" y="123" text-anchor="middle" font-size="10">grading</text>
        </g>
        <text x="140" y="160" text-anchor="middle" font-size="10" fill="#5a5247">HPA adds pods when CPU/queue grows</text>

        <!-- DB read replicas -->
        <rect x="280" y="20" width="240" height="160" fill="rgba(255,255,255,0.4)" stroke="#2a2620" stroke-dasharray="5 4"/>
        <text x="400" y="38" text-anchor="middle" font-family="Caveat" font-size="16">② Read replicas · CQRS lite</text>
        <ellipse cx="400" cy="80" rx="55" ry="16" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="400" y="84" text-anchor="middle">PG primary (write)</text>
        <ellipse cx="340" cy="130" rx="40" ry="14" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="340" y="134" text-anchor="middle">replica</text>
        <ellipse cx="460" cy="130" rx="40" ry="14" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="460" y="134" text-anchor="middle">replica</text>
        <g stroke="#2a2620" stroke-width="1.2" fill="none" marker-end="url(#ascal)">
          <line x1="380" y1="95" x2="345" y2="115"/>
          <line x1="420" y1="95" x2="455" y2="115"/>
        </g>
        <text x="400" y="160" text-anchor="middle" font-size="10" fill="#5a5247">dashboards &amp; AI hit replicas</text>

        <!-- Caching -->
        <rect x="540" y="20" width="240" height="160" fill="rgba(255,255,255,0.4)" stroke="#2a2620" stroke-dasharray="5 4"/>
        <text x="660" y="38" text-anchor="middle" font-family="Caveat" font-size="16">③ Cache + queue · absorb spikes</text>
        <rect x="570" y="60" width="80" height="30" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="610" y="78" text-anchor="middle">Redis cache</text>
        <rect x="670" y="60" width="80" height="30" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/><text x="710" y="78" text-anchor="middle">Kafka queue</text>
        <text x="610" y="110" text-anchor="middle" font-size="10" fill="#5a5247">hot timetables</text>
        <text x="710" y="110" text-anchor="middle" font-size="10" fill="#5a5247">notif burst → drain</text>
        <text x="660" y="160" text-anchor="middle" font-size="10" fill="#5a5247">avg p95 stays &lt; 1.5s even at peak</text>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:8px;">
      <div class="tile"><div class="lbl h">Vertical · DB</div><div class="lbl sm">scale primary up to handle write peaks (exam season, billing day)</div></div>
      <div class="tile"><div class="lbl h">Horizontal · services</div><div class="lbl sm">stateless pods, autoscaled per metric · no sticky sessions</div></div>
      <div class="tile"><div class="lbl h">Async · events</div><div class="lbl sm">slow consumers (notif, AI) never block the user request path</div></div>
    </div>
  </div>

  <!-- Docker / Deployment reasoning -->
  <div class="lbl h" style="margin-top:18px;">⑤ Why Docker · the deployment story</div>
  <div class="grid-2" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Container, not "it works on my machine"</div>
      <div class="lbl" style="margin-top:6px; line-height:1.5;">
        Each service is a <b>Docker image</b> with everything pinned: OS layer, runtime,
        deps, code, config. Same artifact runs in dev, staging, and prod.
      </div>
      <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Buys us</div>
      <ul class="lbl sm" style="margin:4px 0 0; padding-left:16px;">
        <li>identical envs — no "works locally" bugs</li>
        <li>independent deploys per service</li>
        <li>roll back in &lt; 30 min by re-tagging an old image</li>
        <li>onboard a dev in 10 min (clone · <span class="lbl mono">docker compose up</span>)</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">From laptop → production</div>
      <svg viewBox="0 0 400 140" style="width:100%; height:auto;">
        <defs>
          <marker id="adock" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
            <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
          </marker>
        </defs>
        <g font-family="Kalam" font-size="11" fill="#2a2620">
          <rect x="10" y="50" width="70" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="45" y="74" text-anchor="middle">git push</text>
          <rect x="100" y="50" width="80" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="140" y="68" text-anchor="middle" font-size="10">GH Actions</text>
          <text x="140" y="82" text-anchor="middle" font-size="10">test + build</text>
          <rect x="200" y="50" width="90" height="40" rx="6" fill="rgba(255,255,255,0.6)" stroke="#2a2620"/>
          <text x="245" y="68" text-anchor="middle" font-size="10">image registry</text>
          <text x="245" y="82" text-anchor="middle" font-size="10">tagged sha</text>
          <rect x="310" y="50" width="80" height="40" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
          <text x="350" y="68" text-anchor="middle" font-size="10" fill="#D9773C">K8s rolling</text>
          <text x="350" y="82" text-anchor="middle" font-size="10" fill="#D9773C">deploy</text>
          <g stroke="#2a2620" stroke-width="1.3" fill="none" marker-end="url(#adock)">
            <line x1="80" y1="70" x2="100" y2="70"/>
            <line x1="180" y1="70" x2="200" y2="70"/>
            <line x1="290" y1="70" x2="310" y2="70"/>
          </g>
          <text x="200" y="120" text-anchor="middle" font-size="10" fill="#5a5247">5–8 minutes · automated · reversible</text>
        </g>
      </svg>
    </div>
  </div>

  <!-- Why Kafka -->
  <div class="lbl h" style="margin-top:18px;">⑥ Why Kafka specifically?</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Asynchronous</div>
      <div class="lbl sm" style="margin-top:4px;">Producers write, walk away. Consumers catch up at their own pace. No "everyone wait while NotifSvc sends 2,000 SMS".</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Scalable</div>
      <div class="lbl sm" style="margin-top:4px;">Partitions = parallelism. Add brokers + partitions → linear throughput. Tens of thousands of msg/s on cheap hardware.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Decoupling</div>
      <div class="lbl sm" style="margin-top:4px;">GradingSvc doesn't know NotifSvc or AI svc exist. Tomorrow's "send to parent app" is a new consumer, zero producer changes.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Durable</div>
      <div class="lbl sm" style="margin-top:4px;">Events persist on disk with replication factor 3. Crash a broker, no data loss. Audit log built-in.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Replayable</div>
      <div class="lbl sm" style="margin-top:4px;">Need a new read model? Rewind the topic and rebuild from history — no DB dump needed.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Why not RabbitMQ?</div>
      <div class="lbl sm" style="margin-top:4px;">Great for task queues. Weaker on long retention &amp; replay — and we want events to be a system of record, not just a transport.</div>
    </div>
  </div>

  <!-- Monitoring / observability -->
  <div class="lbl h" style="margin-top:22px;">⑦ Observability stack</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 180" style="width:100%; height:180px;">
      <defs>
        <marker id="aobs" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <rect x="20" y="60" width="160" height="60" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="100" y="82" text-anchor="middle" font-family="Caveat" font-size="16">Services emit</text>
        <text x="100" y="100" text-anchor="middle" font-size="10" fill="#5a5247">structured logs · metrics · traces</text>

        <rect x="220" y="20" width="140" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="290" y="38" text-anchor="middle" font-family="Caveat" font-size="14">Logs</text>
        <text x="290" y="52" text-anchor="middle" font-size="10" fill="#5a5247">ELK / Loki</text>

        <rect x="220" y="80" width="140" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="290" y="98" text-anchor="middle" font-family="Caveat" font-size="14">Metrics</text>
        <text x="290" y="112" text-anchor="middle" font-size="10" fill="#5a5247">Prometheus</text>

        <rect x="220" y="140" width="140" height="30" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="290" y="155" text-anchor="middle" font-family="Caveat" font-size="14">Traces · OpenTelemetry / Jaeger</text>

        <rect x="400" y="50" width="160" height="80" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="480" y="78" text-anchor="middle" font-family="Caveat" font-size="18" fill="#D9773C">Grafana</text>
        <text x="480" y="100" text-anchor="middle" font-size="10" fill="#5a5247">unified dashboards</text>
        <text x="480" y="115" text-anchor="middle" font-size="10" fill="#5a5247">SLO views · drilldowns</text>

        <rect x="600" y="20" width="140" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="670" y="38" text-anchor="middle" font-family="Caveat" font-size="14">Alertmanager</text>
        <text x="670" y="52" text-anchor="middle" font-size="10" fill="#5a5247">on-call · Slack · email</text>

        <rect x="600" y="80" width="140" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="670" y="98" text-anchor="middle" font-family="Caveat" font-size="14">Status page</text>
        <text x="670" y="112" text-anchor="middle" font-size="10" fill="#5a5247">public · per-campus</text>

        <rect x="600" y="140" width="140" height="30" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C"/>
        <text x="670" y="155" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">SLO budget ✦</text>

        <g stroke="#2a2620" stroke-width="1.2" fill="none" marker-end="url(#aobs)">
          <line x1="180" y1="80" x2="220" y2="40"/>
          <line x1="180" y1="90" x2="220" y2="100"/>
          <line x1="180" y1="100" x2="220" y2="155"/>
          <line x1="360" y1="40" x2="400" y2="80"/>
          <line x1="360" y1="100" x2="400" y2="100"/>
          <line x1="360" y1="155" x2="400" y2="120"/>
          <line x1="560" y1="70" x2="600" y2="40"/>
          <line x1="560" y1="90" x2="600" y2="100"/>
          <line x1="560" y1="110" x2="600" y2="155"/>
        </g>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:8px;">
      <div class="tile"><div class="lbl h">3 pillars</div><div class="lbl sm">logs · metrics · traces — every service emits all three</div></div>
      <div class="tile"><div class="lbl h">SLOs · 4 golden signals</div><div class="lbl sm">latency · traffic · errors · saturation per service</div></div>
      <div class="tile ai"><div class="lbl h">AI in observability ✦</div><div class="lbl sm">anomaly detection on metrics surfaces incidents before they alert</div></div>
    </div>
  </div>

  <!-- Cost vs complexity -->
  <div class="lbl h" style="margin-top:22px;">⑧ Cost vs complexity · trade-offs we accepted</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 1fr 1.5fr 1fr 1fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Choice</div>
      <div class="lbl sm" style="font-weight:700;">Advantage</div>
      <div class="lbl sm" style="font-weight:700;">Cost</div>
      <div class="lbl sm" style="font-weight:700;">Verdict</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Microservices</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">scalability · team autonomy</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">operational complexity</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">accept · cap at 6 svcs</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Kafka</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">durable + replay + scale</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">3-broker cluster · ops</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">managed offering</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">K8s</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">parity · scale · roll-back</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">learning curve · platform fee</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">managed K8s</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Polyglot DB</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">right tool per shape</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">3 backup strategies</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">managed PG + Mongo</span></div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">LLM API ✦</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">no model ops, latest weights</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">€ per request · vendor risk</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">adapter layer · cap spend</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Self-host LLM (rejected)</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">data control · long-term €</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">GPU bill · model ops team</span></div>
      <div class="tile fill" style="padding:4px 6px;"><span class="lbl sm">reject · revisit yr 3</span></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Rule of thumb: pay <i>money</i> to avoid <i>complexity</i>, until volume makes complexity cheaper.</div>
  </div>

  <!-- SLO / Performance targets -->
  <div class="lbl h" style="margin-top:22px;">⑨ Performance targets · SLO/SLA</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 1.4fr 90px 90px 1.4fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Metric</div>
      <div class="lbl sm" style="font-weight:700;">Target</div>
      <div class="lbl sm" style="font-weight:700;">Type</div>
      <div class="lbl sm" style="font-weight:700;">Measured by</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">API latency · p95</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">&lt; 300 ms</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">SLO</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Prometheus histogram per service</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Page load · p95</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">&lt; 1.5 s</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">SLO</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">RUM (real-user monitoring)</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Uptime · core services</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">99.9%</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">SLA</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">synthetic probes · status page</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Notification delivery</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">&lt; 5 s</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">SLO</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">event-to-push trace span</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Error rate</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">&lt; 0.5%</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">SLO</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">5xx / total · per service</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">DB query · p99</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">&lt; 100 ms</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">SLO</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">pg_stat_statements + alerts</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Deploy · time-to-prod</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">&lt; 10 min</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">GitHub Actions metrics</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Roll-back · MTTR</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">&lt; 30 min</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">incident timeline</span></div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI proposal latency ✦</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">&lt; 3 s</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">SLO</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI svc end-to-end span</span></div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI useful proposal rate ✦</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">&gt; 70%</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">quality</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">apply/dismiss ratio</span></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);"><b>SLO</b> = internal target we hold ourselves to. <b>SLA</b> = contract with stakeholders. Burning SLO budget triggers a freeze on new features until it recovers.</div>
  </div>

  <!-- Environments + CI/CD -->
  <div class="lbl h" style="margin-top:22px;">⑩ Environments · dev → staging → prod</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 220" style="width:100%; height:auto;">
      <defs>
        <marker id="aenv" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <!-- dev -->
        <rect x="20" y="60" width="180" height="110" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <text x="110" y="84" text-anchor="middle" font-family="Caveat" font-size="18">Development</text>
        <text x="110" y="106" text-anchor="middle" font-size="10" fill="#5a5247">laptops · docker compose</text>
        <text x="110" y="124" text-anchor="middle" font-size="10" fill="#5a5247">seeded data · loose policies</text>
        <text x="110" y="142" text-anchor="middle" font-size="10" fill="#5a5247">push to feature branch</text>
        <text x="110" y="160" text-anchor="middle" font-size="10" fill="#D9773C">auto-deploy preview env ✦</text>

        <!-- staging -->
        <rect x="280" y="60" width="180" height="110" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="1.6"/>
        <text x="370" y="84" text-anchor="middle" font-family="Caveat" font-size="18">Staging</text>
        <text x="370" y="106" text-anchor="middle" font-size="10" fill="#5a5247">prod-like · 1 campus mirror</text>
        <text x="370" y="124" text-anchor="middle" font-size="10" fill="#5a5247">anonymised data subset</text>
        <text x="370" y="142" text-anchor="middle" font-size="10" fill="#5a5247">QA + UAT + load tests</text>
        <text x="370" y="160" text-anchor="middle" font-size="10" fill="#D9773C">auto from main branch ✦</text>

        <!-- pre-prod gate -->
        <rect x="500" y="80" width="80" height="70" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
        <text x="540" y="104" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">Approval</text>
        <text x="540" y="120" text-anchor="middle" font-size="9" fill="#5a5247">manual</text>
        <text x="540" y="134" text-anchor="middle" font-size="9" fill="#5a5247">PR + checks</text>

        <!-- prod -->
        <rect x="620" y="60" width="180" height="110" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620" stroke-width="2"/>
        <text x="710" y="84" text-anchor="middle" font-family="Caveat" font-size="18">Production</text>
        <text x="710" y="106" text-anchor="middle" font-size="10" fill="#5a5247">4 campuses · HA · multi-AZ</text>
        <text x="710" y="124" text-anchor="middle" font-size="10" fill="#5a5247">real data · strict policies</text>
        <text x="710" y="142" text-anchor="middle" font-size="10" fill="#5a5247">canary 5% → 50% → 100%</text>
        <text x="710" y="160" text-anchor="middle" font-size="10" fill="#D9773C">auto-rollback on SLO burn ✦</text>

        <!-- DR -->
        <rect x="820" y="60" width="70" height="110" rx="6" fill="rgba(255,255,255,0.4)" stroke="#2a2620" stroke-dasharray="4 4"/>
        <text x="855" y="84" text-anchor="middle" font-family="Caveat" font-size="14">DR</text>
        <text x="855" y="106" text-anchor="middle" font-size="9" fill="#5a5247">2nd region</text>
        <text x="855" y="120" text-anchor="middle" font-size="9" fill="#5a5247">cold standby</text>
        <text x="855" y="134" text-anchor="middle" font-size="9" fill="#5a5247">RTO &lt; 1h</text>
        <text x="855" y="148" text-anchor="middle" font-size="9" fill="#5a5247">RPO &lt; 15m</text>

        <!-- arrows -->
        <g stroke="#2a2620" stroke-width="1.4" fill="none" marker-end="url(#aenv)">
          <line x1="200" y1="115" x2="280" y2="115"/>
          <line x1="460" y1="115" x2="500" y2="115"/>
          <line x1="580" y1="115" x2="620" y2="115"/>
          <line x1="800" y1="115" x2="820" y2="115" stroke-dasharray="3 3"/>
        </g>

        <!-- bottom row: what's different -->
        <g font-family="Architects Daughter" font-size="10" fill="#5a5247">
          <text x="110" y="195" text-anchor="middle">data: synthetic</text>
          <text x="370" y="195" text-anchor="middle">data: anonymised real</text>
          <text x="710" y="195" text-anchor="middle">data: real · encrypted</text>
        </g>
      </g>
    </svg>
  </div>

  <!-- CI/CD pipeline detail -->
  <div class="lbl h" style="margin-top:18px;">⑪ CI/CD pipeline · git push → production</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 100" style="width:100%; height:100px;">
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <line x1="20" y1="50" x2="880" y2="50" stroke="#2a2620" stroke-width="1.5"/>
        <g>
          <circle cx="60" cy="50" r="6" fill="#2a2620"/><text x="60" y="32" text-anchor="middle" font-family="Caveat" font-size="13">commit</text><text x="60" y="72" text-anchor="middle" font-size="9" fill="#5a5247">git push</text>
          <circle cx="170" cy="50" r="6" fill="#2a2620"/><text x="170" y="32" text-anchor="middle" font-family="Caveat" font-size="13">lint + tests</text><text x="170" y="72" text-anchor="middle" font-size="9" fill="#5a5247">unit + integration</text>
          <circle cx="290" cy="50" r="6" fill="#2a2620"/><text x="290" y="32" text-anchor="middle" font-family="Caveat" font-size="13">SAST + SCA</text><text x="290" y="72" text-anchor="middle" font-size="9" fill="#5a5247">security scan</text>
          <circle cx="400" cy="50" r="6" fill="#2a2620"/><text x="400" y="32" text-anchor="middle" font-family="Caveat" font-size="13">build image</text><text x="400" y="72" text-anchor="middle" font-size="9" fill="#5a5247">docker · sign · push</text>
          <circle cx="510" cy="50" r="6" fill="#2a2620"/><text x="510" y="32" text-anchor="middle" font-family="Caveat" font-size="13">deploy staging</text><text x="510" y="72" text-anchor="middle" font-size="9" fill="#5a5247">auto</text>
          <circle cx="620" cy="50" r="6" fill="#2a2620"/><text x="620" y="32" text-anchor="middle" font-family="Caveat" font-size="13">e2e + load</text><text x="620" y="72" text-anchor="middle" font-size="9" fill="#5a5247">smoke + perf</text>
          <circle cx="720" cy="50" r="6" fill="#D9773C"/><text x="720" y="32" text-anchor="middle" font-family="Caveat" font-size="13" fill="#D9773C">approval ✦</text><text x="720" y="72" text-anchor="middle" font-size="9" fill="#5a5247">manual gate</text>
          <circle cx="820" cy="50" r="6" fill="#D9773C"/><text x="820" y="32" text-anchor="middle" font-family="Caveat" font-size="13" fill="#D9773C">prod canary</text><text x="820" y="72" text-anchor="middle" font-size="9" fill="#5a5247">5 → 50 → 100%</text>
        </g>
      </g>
    </svg>
    <div class="lbl sm" style="margin-top:6px; color: var(--ink-soft);">Same Docker image flows through every stage; only the config changes. Auto-rollback triggers if error rate or latency burns SLO during canary.</div>
  </div>
</section>

<!-- ============ LOT 7 · DECISIONS ============ -->
<section class="tab-pane" data-pane="decisions">
  <div class="pane-head">
    <div>
      <h2>Structural decisions</h2>
      <p>The "why" the panel will ask about. Each decision in ADR format: context → decision → consequences.</p>
    </div>
    <div class="legend"><b>Format</b><br>ADR · architecture decision record<br>one card = one trade-off</div>
  </div>

  <div class="variants">
    <div class="wf">
      <div class="wf-tag">ADR-001</div>
      <h3>Microservices over monolith</h3>
      <div class="col" style="gap:6px;">
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Context</span><div class="lbl">4 campuses, distinct module load profiles, audit traceability.</div></div>
        <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Decision</span><div class="lbl">Split into 6 services around bounded contexts.</div></div>
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Consequences</span><div class="lbl sm">+ independent scale &amp; deploy<br>− ops complexity, eventual consistency<br>↪ Kafka + outbox pattern</div></div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">ADR-002</div>
      <h3>Event-driven for notifications</h3>
      <div class="col" style="gap:6px;">
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Context</span><div class="lbl">"You never know if a room change is official."</div></div>
        <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Decision</span><div class="lbl">Domain events → Kafka → NotifSvc fans out push/email/SMS.</div></div>
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Consequences</span><div class="lbl sm">+ replayable history<br>+ decouples notif logic from each service<br>− need idempotency keys per consumer</div></div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">ADR-003</div>
      <h3>SQL + NoSQL (polyglot)</h3>
      <div class="col" style="gap:6px;">
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Context</span><div class="lbl">Grades &amp; € need ACID. Logs/payloads/embeddings don't.</div></div>
        <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Decision</span><div class="lbl">PG for system of record · Mongo for audit/log · pgvector for AI memory.</div></div>
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Consequences</span><div class="lbl sm">+ right tool per shape<br>− 3 backup strategies, 3 monitoring dashboards</div></div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">ADR-004 ✦</div>
      <h3>AI as a service, not a feature</h3>
      <div class="col" style="gap:6px;">
        <div class="tile ai" style="padding:6px 8px;"><span class="lbl sm">Context</span><div class="lbl">Leadership wants ONE meaningful AI win, not chat-everywhere.</div></div>
        <div class="tile ai" style="padding:6px 8px;"><span class="lbl sm">Decision</span><div class="lbl">AI agent runs as its own service, calls deterministic tools, inherits caller scope.</div></div>
        <div class="tile ai" style="padding:6px 8px;"><span class="lbl sm">Consequences</span><div class="lbl sm">+ swappable model · auditable actions<br>− needs explicit "human-in-the-loop" UX in every flow</div></div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">ADR-005</div>
      <h3>Single multi-tenant DB per service</h3>
      <div class="col" style="gap:6px;">
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Context</span><div class="lbl">4 campuses today, possibly more. Per-campus DB explodes ops.</div></div>
        <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Decision</span><div class="lbl">Logical isolation via campusId column + RLS, not separate DBs.</div></div>
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Consequences</span><div class="lbl sm">+ simple ops, easy cross-campus KPIs<br>− RLS misconfig = cross-campus leak (test ruthlessly)</div></div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">ADR-006</div>
      <h3>Docker + K8s from day 1</h3>
      <div class="col" style="gap:6px;">
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Context</span><div class="lbl">6 services, 4 campuses, dev/staging/prod parity matters.</div></div>
        <div class="tile accent" style="padding:6px 8px;"><span class="lbl sm">Decision</span><div class="lbl">Everything containerised; managed K8s; GitOps deploys.</div></div>
        <div class="tile" style="padding:6px 8px;"><span class="lbl sm">Consequences</span><div class="lbl sm">+ scales horizontally, consistent envs<br>− learning curve for team; budget K8s ops</div></div>
      </div>
    </div>
  </div>

  <!-- Constraints -->
  <div class="lbl h" style="margin-top:22px;">Architecture constraints we designed against</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Business</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>4 campuses today, possibly 8 in 3 yrs</li>
        <li>academic year cadence — exam &amp; billing spikes</li>
        <li>budget — can't afford a 6-person ops team</li>
        <li>auditable history of every grade/€ change</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Regulatory / Legal</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>GDPR · data minimisation, right to erasure</li>
        <li>student record retention · 7 years</li>
        <li>financial records · local accounting law</li>
        <li>AI decisions must be explainable + reversible</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Technical</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>mixed connectivity — 3G must work</li>
        <li>existing payment gateway must integrate</li>
        <li>SSO mandatory · no separate passwords</li>
        <li>roll-back &lt; 30 min · zero-downtime deploys</li>
      </ul>
    </div>
  </div>

  <!-- Pros / cons summary -->
  <div class="lbl h" style="margin-top:22px;">Pros &amp; cons · summary table</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Decision</div>
      <div class="lbl sm" style="font-weight:700;">Pros</div>
      <div class="lbl sm" style="font-weight:700;">Cons</div>
      <div class="lbl sm" style="font-weight:700;">Mitigation</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Microservices</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">scale per module · tech freedom</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">ops complexity · eventual consistency</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">keep to 6 services · K8s managed</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Event-driven</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">decoupling · replay · audit</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">UI "pending" states · idempotency</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">outbox pattern · explicit status UX</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">SQL + NoSQL</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">right tool per shape</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">3 backup strategies</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">managed services for both</span></div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI as service ✦</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">swappable model · auditable</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">human-in-loop UX everywhere</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">tools enforce business rules</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Multi-tenant DB</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">simple ops · easy cross-campus KPIs</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">RLS misconfig = cross-campus leak</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">CI tests for RLS · scope tests</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Docker + K8s</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">parity · scale · roll-back</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">team learning curve</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">managed K8s · 1 platform engineer</span></div>
    </div>
  </div>

  <!-- Scalability reasoning -->
  <div class="lbl h" style="margin-top:22px;">Scalability reasoning · why these decisions hold at 2× size</div>
  <div class="frame pad" style="padding:12px; margin-top:6px;">
    <div class="grid-3">
      <div class="tile"><div class="lbl h">2×&nbsp;students</div><div class="lbl sm" style="margin-top:4px;">stateless services autoscale · DB read replicas absorb dashboard load · cache hot timetables</div></div>
      <div class="tile"><div class="lbl h">2×&nbsp;campuses</div><div class="lbl sm" style="margin-top:4px;">campusId scope already in model · no schema change · onboarding = create tenant + import users</div></div>
      <div class="tile ai"><div class="lbl h">2×&nbsp;AI traffic ✦</div><div class="lbl sm" style="margin-top:4px;">agent svc scales independently · LLM API absorbs spikes · vector store sharded by campus</div></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Whole architecture was designed against "8 campuses" not "today" — see L1 Constraints, NFR-scal, ADR-005.</div>
  </div>

  <!-- Severity of trade-offs -->
  <div class="lbl h" style="margin-top:22px;">Severity matrix · how serious is each trade-off?</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 1.4fr 90px 90px 2fr; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Trade-off</div>
      <div class="lbl sm" style="font-weight:700;">Severity</div>
      <div class="lbl sm" style="font-weight:700;">Likelihood</div>
      <div class="lbl sm" style="font-weight:700;">How we hold the line</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Operational complexity (K8s + 6 svcs)</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">managed K8s · 1 dedicated platform engineer · runbooks</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Infrastructure cost</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">scale-to-zero off-peak · spot nodes for AI · spend budget</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Eventual consistency UX</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">explicit "pending" + "confirmed" states across the UI</span></div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI vendor lock-in ✦</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">adapter layer · model-agnostic tool interface</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">RLS misconfiguration → cross-tenant leak</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Low</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">RLS unit tests in CI · pen test before each major release</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Team learning curve (event-driven thinking)</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Med</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">internal training · pair programming · ADRs as docs</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">3 backup/observability stacks (polyglot DBs)</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Low</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">High</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">unified Grafana dashboards · managed offerings</span></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">High severity × low likelihood is fine if mitigated. The combos we refuse are <i>High</i> × <i>High</i> with no plan.</div>
  </div>

  <!-- Future evolution roadmap -->
  <div class="lbl h" style="margin-top:22px;">Future evolution · 18-month roadmap</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 120" style="width:100%; height:120px;">
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <line x1="20" y1="60" x2="880" y2="60" stroke="#2a2620" stroke-width="1.5"/>
        <!-- now marker -->
        <line x1="80" y1="30" x2="80" y2="90" stroke="#D9773C" stroke-width="2" stroke-dasharray="3 3"/>
        <text x="80" y="22" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">today</text>

        <g>
          <circle cx="180" cy="60" r="6" fill="#2a2620"/>
          <text x="180" y="44" text-anchor="middle" font-family="Caveat" font-size="14">+3 mo</text>
          <text x="180" y="80" text-anchor="middle" font-size="10" fill="#5a5247">MVP live · 2 campuses</text>
          <text x="180" y="95" text-anchor="middle" font-size="10" fill="#5a5247">AI resolver in beta</text>

          <circle cx="320" cy="60" r="6" fill="#2a2620"/>
          <text x="320" y="44" text-anchor="middle" font-family="Caveat" font-size="14">+6 mo</text>
          <text x="320" y="80" text-anchor="middle" font-size="10" fill="#5a5247">all 4 campuses · parent portal</text>
          <text x="320" y="95" text-anchor="middle" font-size="10" fill="#5a5247">AI dunning live</text>

          <circle cx="460" cy="60" r="6" fill="#D9773C"/>
          <text x="460" y="44" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">+9 mo</text>
          <text x="460" y="80" text-anchor="middle" font-size="10" fill="#5a5247">LMS integration ✦</text>
          <text x="460" y="95" text-anchor="middle" font-size="10" fill="#5a5247">course content + grades sync</text>

          <circle cx="600" cy="60" r="6" fill="#D9773C"/>
          <text x="600" y="44" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">+12 mo</text>
          <text x="600" y="80" text-anchor="middle" font-size="10" fill="#5a5247">predictive analytics ✦</text>
          <text x="600" y="95" text-anchor="middle" font-size="10" fill="#5a5247">cohort risk · drop-out signals</text>

          <circle cx="740" cy="60" r="6" fill="#D9773C"/>
          <text x="740" y="44" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">+15 mo</text>
          <text x="740" y="80" text-anchor="middle" font-size="10" fill="#5a5247">personalised AI tutor ✦</text>
          <text x="740" y="95" text-anchor="middle" font-size="10" fill="#5a5247">study plan per student</text>

          <circle cx="860" cy="60" r="6" fill="#2a2620"/>
          <text x="860" y="44" text-anchor="middle" font-family="Caveat" font-size="14">+18 mo</text>
          <text x="860" y="80" text-anchor="middle" font-size="10" fill="#5a5247">5th &amp; 6th campus</text>
          <text x="860" y="95" text-anchor="middle" font-size="10" fill="#5a5247">multi-region DB</text>
        </g>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:10px;">
      <div class="frame pad" style="padding:10px;">
        <div class="lbl h">Now → +6 mo</div>
        <div class="lbl sm" style="margin-top:4px;">Stabilise core ERP. Win confidence with the AI resolver. Get to all 4 campuses.</div>
      </div>
      <div class="frame pad accent" style="padding:10px; border-color: var(--accent);">
        <div class="lbl h">+6 → +12 mo</div>
        <div class="lbl sm" style="margin-top:4px;">Open the platform: LMS, parent portal. Begin predictive analytics on real data.</div>
      </div>
      <div class="frame pad ai" style="padding:10px; border-color: var(--accent); background: repeating-linear-gradient(45deg, rgba(217,119,60,0.10) 0 6px, transparent 6px 12px);">
        <div class="lbl h">+12 → +18 mo ✦</div>
        <div class="lbl sm" style="margin-top:4px;">Personalisation. Study buddy. Cohort intervention. Scale to 6+ campuses.</div>
      </div>
    </div>
  </div>
</section>

<!-- ============ L8 · SECURITY ============ -->
<section class="tab-pane" data-pane="security">
  <div class="pane-head">
    <div>
      <h2>Security architecture</h2>
      <p>Authentication · authorization · encryption · compliance · AI guardrails. The "trust me" of the whole system, designed not assumed.</p>
    </div>
    <div class="legend"><b>Layers</b><br>identity · access · data · transport<br>compliance · AI guardrails</div>
  </div>

  <!-- Authentication -->
  <div class="lbl h">① Authentication · who are you?</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 160" style="width:100%; height:160px;">
      <defs>
        <marker id="aauth" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <rect x="20" y="60" width="100" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="70" y="84" text-anchor="middle" font-family="Caveat" font-size="14">User</text>

        <rect x="160" y="60" width="140" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="230" y="78" text-anchor="middle" font-family="Caveat" font-size="14">OIDC provider</text>
        <text x="230" y="92" text-anchor="middle" font-size="10" fill="#5a5247">login · MFA</text>

        <rect x="340" y="60" width="140" height="40" rx="6" fill="rgba(217,119,60,0.12)" stroke="#D9773C" stroke-width="2"/>
        <text x="410" y="78" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">JWT</text>
        <text x="410" y="92" text-anchor="middle" font-size="10" fill="#5a5247">RS256 · 15min</text>

        <rect x="520" y="20" width="140" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="590" y="38" text-anchor="middle" font-family="Caveat" font-size="14">Refresh token</text>
        <text x="590" y="52" text-anchor="middle" font-size="10" fill="#5a5247">httpOnly · 30 days</text>

        <rect x="520" y="100" width="140" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="590" y="118" text-anchor="middle" font-family="Caveat" font-size="14">Gateway verify</text>
        <text x="590" y="132" text-anchor="middle" font-size="10" fill="#5a5247">signature · exp · scope</text>

        <rect x="700" y="60" width="160" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="780" y="78" text-anchor="middle" font-family="Caveat" font-size="14">Service · scoped call</text>
        <text x="780" y="92" text-anchor="middle" font-size="10" fill="#5a5247">campus + role enforced</text>

        <g stroke="#2a2620" stroke-width="1.3" fill="none" marker-end="url(#aauth)">
          <line x1="120" y1="80" x2="160" y2="80"/>
          <line x1="300" y1="80" x2="340" y2="80"/>
          <line x1="480" y1="70" x2="520" y2="40"/>
          <line x1="480" y1="90" x2="520" y2="120"/>
          <line x1="660" y1="120" x2="700" y2="90"/>
        </g>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:8px;">
      <div class="tile"><div class="lbl h">SSO · OIDC</div><div class="lbl sm">single sign-on with institutional identity. No password storage in our DB.</div></div>
      <div class="tile"><div class="lbl h">MFA on admin</div><div class="lbl sm">required for admin + management. TOTP or hardware key.</div></div>
      <div class="tile"><div class="lbl h">JWT short-lived</div><div class="lbl sm">15-min access · 30-day refresh in httpOnly cookie · rotation on use.</div></div>
    </div>
  </div>

  <!-- Authorization / RBAC -->
  <div class="lbl h" style="margin-top:22px;">② Authorization · RBAC + scopes</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 100px repeat(5, 1fr); gap:3px;">
      <div></div>
      <div class="lbl sm" style="font-weight:700; text-align:center;">view own</div>
      <div class="lbl sm" style="font-weight:700; text-align:center;">view class</div>
      <div class="lbl sm" style="font-weight:700; text-align:center;">edit grade</div>
      <div class="lbl sm" style="font-weight:700; text-align:center;">manage rooms</div>
      <div class="lbl sm" style="font-weight:700; text-align:center;">view all KPIs</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Student</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Teacher</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Admin</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">campus</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Management</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">✓</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">·</span></div>
      <div class="tile" style="padding:4px 6px; text-align:center;"><span class="lbl">all</span></div>

      <div class="tile ai" style="padding:4px 6px;"><span class="lbl sm">AI agent ✦</span></div>
      <div class="tile ai" style="padding:4px 6px; text-align:center;"><span class="lbl sm">caller scope</span></div>
      <div class="tile ai" style="padding:4px 6px; text-align:center;"><span class="lbl sm">caller scope</span></div>
      <div class="tile ai" style="padding:4px 6px; text-align:center;"><span class="lbl sm">propose only</span></div>
      <div class="tile ai" style="padding:4px 6px; text-align:center;"><span class="lbl sm">propose only</span></div>
      <div class="tile ai" style="padding:4px 6px; text-align:center;"><span class="lbl sm">caller scope</span></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">Each row × column resolves to a policy: <span class="lbl mono">can(role, action, scope)</span>. Enforced at the gateway AND in-service. AI inherits caller scope — never escalates.</div>
  </div>

  <!-- Data security / encryption -->
  <div class="lbl h" style="margin-top:22px;">③ Data &amp; transport security</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Encryption · in transit</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>HTTPS everywhere · TLS 1.2+</li>
        <li>HSTS · forced upgrades</li>
        <li>service-to-service mTLS inside cluster</li>
        <li>Kafka TLS + SASL between brokers</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Encryption · at rest</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>AES-256 on disk (managed DB)</li>
        <li>application-level encryption for sensitive fields (national ID)</li>
        <li>S3 documents · server-side encryption + signed URLs</li>
        <li>backups encrypted with separate key</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Secrets &amp; keys</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>secrets manager (Vault / cloud KMS)</li>
        <li>never in code or .env files in repos</li>
        <li>rotation every 90 days · automated</li>
        <li>JWT signing key rotation supported</li>
      </ul>
    </div>
  </div>

  <!-- Token expiration / session -->
  <div class="lbl h" style="margin-top:22px;">④ Token &amp; session lifecycle</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 80" style="width:100%; height:80px;">
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <line x1="20" y1="40" x2="880" y2="40" stroke="#2a2620" stroke-width="1.5"/>
        <g>
          <circle cx="80" cy="40" r="5" fill="#D9773C"/><text x="80" y="22" text-anchor="middle" font-family="Caveat" font-size="13">login</text><text x="80" y="62" text-anchor="middle" font-size="10" fill="#5a5247">issue access + refresh</text>
          <circle cx="240" cy="40" r="5" fill="#2a2620"/><text x="240" y="22" text-anchor="middle" font-family="Caveat" font-size="13">access expires</text><text x="240" y="62" text-anchor="middle" font-size="10" fill="#5a5247">15 min</text>
          <circle cx="400" cy="40" r="5" fill="#2a2620"/><text x="400" y="22" text-anchor="middle" font-family="Caveat" font-size="13">silent refresh</text><text x="400" y="62" text-anchor="middle" font-size="10" fill="#5a5247">rotate refresh token</text>
          <circle cx="580" cy="40" r="5" fill="#2a2620"/><text x="580" y="22" text-anchor="middle" font-family="Caveat" font-size="13">idle &gt; 60 min</text><text x="580" y="62" text-anchor="middle" font-size="10" fill="#5a5247">force re-auth</text>
          <circle cx="780" cy="40" r="5" fill="#D9773C"/><text x="780" y="22" text-anchor="middle" font-family="Caveat" font-size="13" fill="#D9773C">logout / revoke</text><text x="780" y="62" text-anchor="middle" font-size="10" fill="#5a5247">refresh blacklist</text>
        </g>
      </g>
    </svg>
  </div>

  <!-- Compliance -->
  <div class="lbl h" style="margin-top:22px;">⑤ Compliance · GDPR &amp; education law</div>
  <div class="grid-4" style="margin-top:6px;">
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Lawful basis</div>
      <div class="lbl sm" style="margin-top:4px;">contract (academic) · legitimate interest (analytics) · consent (marketing)</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Data minimisation</div>
      <div class="lbl sm" style="margin-top:4px;">collect only what's needed for the academic record. No biometrics. No marketing trackers.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">User rights</div>
      <div class="lbl sm" style="margin-top:4px;">access · export · rectify · erase · object — all via self-serve profile page</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Retention</div>
      <div class="lbl sm" style="margin-top:4px;">academic records 7 years · audit logs 7 years · access logs 12 months · then erased</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Audit logs</div>
      <div class="lbl sm" style="margin-top:4px;">every read of sensitive data, every write of grade or €. Append-only, tamper-evident.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Breach response</div>
      <div class="lbl sm" style="margin-top:4px;">documented runbook · 72-hour notification window · communication templates</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Data residency</div>
      <div class="lbl sm" style="margin-top:4px;">EU region. No cross-border transfer without SCCs. LLM calls anonymised.</div>
    </div>
    <div class="frame pad" style="padding:10px;">
      <div class="lbl h">Vendors / DPAs</div>
      <div class="lbl sm" style="margin-top:4px;">DPA signed with every processor: cloud, email, SMS, LLM provider.</div>
    </div>
  </div>

  <!-- AI guardrails -->
  <div class="lbl h" style="margin-top:22px;">⑥ AI guardrails ✦</div>
  <div class="frame pad ai" style="padding:14px; margin-top:6px; border:2px solid var(--accent); background: repeating-linear-gradient(45deg, rgba(217,119,60,0.08) 0 6px, transparent 6px 12px);">
    <div class="lbl h" style="font-size: 22px; color: var(--accent);">"AI can propose. Humans approve."</div>
    <div class="lbl" style="margin-top:6px; line-height:1.5; max-width: 760px;">
      The agent never commits a decision that affects a student's record, a teacher's schedule, or a parent's payment. It surfaces proposals — a human clicks <i>Apply</i>.
    </div>
    <div class="grid-3" style="margin-top:12px;">
      <div class="tile">
        <div class="lbl h">No autonomous grading</div>
        <div class="lbl sm" style="margin-top:4px;">AI never writes a grade. It can suggest "this submission looks like X" — teacher decides.</div>
      </div>
      <div class="tile">
        <div class="lbl h">No autonomous money moves</div>
        <div class="lbl sm" style="margin-top:4px;">AI drafts dunning emails. It does not send. Admin reviews + clicks <i>Send</i>.</div>
      </div>
      <div class="tile">
        <div class="lbl h">No autonomous schedule changes</div>
        <div class="lbl sm" style="margin-top:4px;">AI proposes room moves. Admin sees diff, capacity, students affected, then <i>Apply</i>.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Tools enforce rules</div>
        <div class="lbl sm" style="margin-top:4px;">Even if the model "wants" to overbook a room, the tool refuses. Business rules &gt; model output.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Scope inherited</div>
        <div class="lbl sm" style="margin-top:4px;">Agent only sees what the caller can see. Student calling AI = student-scoped reads only.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Full audit trail</div>
        <div class="lbl sm" style="margin-top:4px;">Every prompt, every proposal, every Apply click — logged. AI decisions are <b>reversible</b>.</div>
      </div>
      <div class="tile">
        <div class="lbl h">No PII to LLM</div>
        <div class="lbl sm" style="margin-top:4px;">Names + IDs replaced with tokens before any prompt leaves our perimeter. De-tokenised on the way back.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Hallucination floor</div>
        <div class="lbl sm" style="margin-top:4px;">Confidence threshold below which the agent says "I'm not sure" rather than guess.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Explain &amp; refuse</div>
        <div class="lbl sm" style="margin-top:4px;">Every proposal shows <i>why</i>. Users can flag/refuse — feeds back into evaluation set.</div>
      </div>
    </div>
  </div>

  <!-- OWASP top 10 summary -->
  <div class="lbl h" style="margin-top:22px;">⑦ OWASP top 10 · how we cover it</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 1fr 2fr; gap:4px;">
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A01 Broken access</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">RBAC at gateway + service · RLS in DB · scope tests in CI</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A02 Crypto failures</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">TLS everywhere · AES-256 at rest · KMS-managed keys</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A03 Injection</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">parameterised queries · ORM · input validation · CSP</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A04 Insecure design</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">threat modeling per feature · ADRs · pen test</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A05 Misconfiguration</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">IaC · automated config checks · least-privilege defaults</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A06 Vulnerable deps</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Dependabot · weekly CVE scan · SBOM published</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A07 Auth failures</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">SSO · MFA · short JWTs · rate limit · brute-force lockout</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A08 Integrity failures</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">signed images · verified deploys · GitOps audit trail</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A09 Logging failures</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">centralised logs · alert on suspicious patterns · 12mo retention</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">A10 SSRF</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">egress allow-list · no user-supplied URLs hit internal hosts</span></div>
    </div>
  </div>
</section>

<!-- ============ ★ END-TO-END STORY ============ -->
<section class="tab-pane" data-pane="story">
  <div class="pane-head">
    <div>
      <h2>End-to-end story · "Mr. Hadji publishes Wednesday's grades"</h2>
      <p>One real action, traced through every layer of the system. UI → API → service → DB → event → notification → audit log → AI signal. This is the file you hand the panel if they only have 2 minutes.</p>
    </div>
    <div class="legend"><b>What it ties together</b><br>L1 process · L3 architecture<br>L5 tech · L6 UI · L8 security</div>
  </div>

  <!-- The map -->
  <div class="lbl h">① The whole journey at a glance</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 380" style="width:100%; height:auto;">
      <defs>
        <marker id="astory" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" fill="#2a2620"/>
        </marker>
      </defs>
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <!-- lane labels -->
        <g font-family="Caveat" font-size="14" fill="#5a5247">
          <text x="80" y="30" text-anchor="middle">UI</text>
          <text x="80" y="100" text-anchor="middle">Gateway</text>
          <text x="80" y="170" text-anchor="middle">Service</text>
          <text x="80" y="240" text-anchor="middle">DB</text>
          <text x="80" y="310" text-anchor="middle">Bus + Notif</text>
          <text x="80" y="370" text-anchor="middle">Audit + AI ✦</text>
        </g>
        <g stroke="#2a2620" stroke-dasharray="3 4" stroke-width="0.8">
          <line x1="140" y1="20" x2="900" y2="20"/>
          <line x1="140" y1="60" x2="900" y2="60"/>
          <line x1="140" y1="130" x2="900" y2="130"/>
          <line x1="140" y1="200" x2="900" y2="200"/>
          <line x1="140" y1="270" x2="900" y2="270"/>
          <line x1="140" y1="340" x2="900" y2="340"/>
        </g>

        <!-- UI -->
        <rect x="160" y="10" width="160" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="240" y="28" text-anchor="middle" font-family="Caveat" font-size="14">① Mr. Hadji clicks Publish</text>
        <text x="240" y="42" text-anchor="middle" font-size="9" fill="#5a5247">grade table → modal confirm</text>

        <!-- Gateway -->
        <rect x="340" y="80" width="160" height="40" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="420" y="98" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">② Gateway · verify JWT</text>
        <text x="420" y="112" text-anchor="middle" font-size="9" fill="#5a5247">role=teacher · scope=campusB</text>

        <!-- Service -->
        <rect x="520" y="150" width="160" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="600" y="168" text-anchor="middle" font-family="Caveat" font-size="14">③ GradingSvc · RBAC + validate</text>
        <text x="600" y="182" text-anchor="middle" font-size="9" fill="#5a5247">teacher owns this class? values valid?</text>

        <!-- DB -->
        <rect x="520" y="220" width="160" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="600" y="238" text-anchor="middle" font-family="Caveat" font-size="14">④ Postgres write · TX</text>
        <text x="600" y="252" text-anchor="middle" font-size="9" fill="#5a5247">grades + outbox in one transaction</text>

        <!-- Bus -->
        <rect x="340" y="290" width="160" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="420" y="308" text-anchor="middle" font-family="Caveat" font-size="14">⑤ Kafka · GradePublished</text>
        <text x="420" y="322" text-anchor="middle" font-size="9" fill="#5a5247">partition by classId</text>

        <!-- Notif -->
        <rect x="520" y="290" width="160" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="600" y="308" text-anchor="middle" font-family="Caveat" font-size="14">⑥ NotifSvc · push 24 students</text>
        <text x="600" y="322" text-anchor="middle" font-size="9" fill="#5a5247">&lt; 5s delivery SLO</text>

        <!-- Audit + AI -->
        <rect x="160" y="350" width="160" height="40" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="240" y="368" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">⑦ AuditLog ✦</text>
        <text x="240" y="382" text-anchor="middle" font-size="9" fill="#5a5247">actor · before/after · 7yr</text>

        <rect x="700" y="350" width="160" height="40" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
        <text x="780" y="368" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">⑧ AI cohort signal ✦</text>
        <text x="780" y="382" text-anchor="middle" font-size="9" fill="#5a5247">"3 students at risk — alert mgr?"</text>

        <!-- UI back -->
        <rect x="340" y="10" width="160" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="420" y="28" text-anchor="middle" font-family="Caveat" font-size="14">⑨ UI · "Published ✓"</text>
        <text x="420" y="42" text-anchor="middle" font-size="9" fill="#5a5247">+ undo for 60s</text>

        <rect x="700" y="10" width="160" height="40" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
        <text x="780" y="28" text-anchor="middle" font-family="Caveat" font-size="14">⑩ Student phone · push</text>
        <text x="780" y="42" text-anchor="middle" font-size="9" fill="#5a5247">"New grade · Algo II · 14/20"</text>

        <!-- arrows -->
        <g stroke="#2a2620" stroke-width="1.4" fill="none" marker-end="url(#astory)">
          <line x1="240" y1="50" x2="380" y2="80"/>
          <line x1="500" y1="100" x2="540" y2="150"/>
          <line x1="600" y1="190" x2="600" y2="220"/>
          <line x1="540" y1="260" x2="460" y2="290"/>
          <line x1="500" y1="310" x2="520" y2="310"/>
          <line x1="600" y1="330" x2="780" y2="350" stroke="#D9773C"/>
          <line x1="600" y1="260" x2="240" y2="350" stroke="#D9773C"/>
          <line x1="540" y1="150" x2="500" y2="50"/>
          <line x1="680" y1="310" x2="780" y2="50"/>
        </g>
      </g>
    </svg>
  </div>

  <!-- Step-by-step zoom -->
  <div class="lbl h" style="margin-top:22px;">② What happens at each step</div>
  <div class="grid-2" style="margin-top:6px;">

    <div class="wf">
      <div class="wf-tag">①</div>
      <h3>UI · clicks "Publish"</h3>
      <div class="wf-sub">L6 · Teacher's gradebook screen, top-right action.</div>
      <div class="topbar"><span class="crumbs">Algo II · group A · 24 students</span>
        <div class="right"><span class="chip">draft saved</span><span class="chip fill">Publish ▸</span></div>
      </div>
      <div class="frame pad" style="padding:8px; margin-top:6px;">
        <div class="row" style="justify-content:space-between"><span class="lbl h">Confirm publish?</span></div>
        <div class="lbl sm" style="margin-top:4px;">24 students will be notified. Grades become read-only after 60s.</div>
        <div class="row" style="margin-top:6px; gap:4px;"><span class="chip">cancel</span><span class="chip fill">yes, publish</span></div>
      </div>
      <div class="lbl sm" style="margin-top:6px; color: var(--ink-soft);">Why a confirm modal: this triggers irreversible side-effects (push to phones, audit row).</div>
    </div>

    <div class="wf">
      <div class="wf-tag">②</div>
      <h3>Gateway · auth + scope</h3>
      <div class="wf-sub">L8 · JWT verified, RBAC scope extracted.</div>
      <div class="frame pad" style="padding:8px;">
        <div class="lbl sm"><span class="lbl mono">POST /api/v1/classes/algo-ii/grades:publish</span></div>
        <div class="lbl sm" style="margin-top:4px;"><span class="lbl mono">Authorization: Bearer eyJ&hellip;</span></div>
        <div class="lbl sm" style="margin-top:6px;">Gateway:</div>
        <ul class="lbl sm" style="margin:2px 0 0; padding-left:16px;">
          <li>verify RS256 signature</li>
          <li>extract <span class="lbl mono">role=teacher</span>, <span class="lbl mono">campus=B</span></li>
          <li>rate-limit check (1k/min/user)</li>
          <li>route to GradingSvc</li>
        </ul>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">③</div>
      <h3>Service · RBAC + business rules</h3>
      <div class="wf-sub">L3 + L7 · GradingSvc enforces "tools enforce rules".</div>
      <div class="frame pad" style="padding:8px;">
        <ul class="lbl sm" style="margin:0; padding-left:16px;">
          <li><span class="lbl mono">can(teacher, publish, classId)</span> → ✓</li>
          <li>class exists, belongs to campus B → ✓</li>
          <li>all values in [0..20] → ✓</li>
          <li>assessment exists &amp; open → ✓</li>
          <li>idempotency key not seen → ✓</li>
        </ul>
        <div class="lbl sm" style="margin-top:6px;">Any fail → 4xx with clear message, no DB write.</div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">④</div>
      <h3>DB write · transactional outbox</h3>
      <div class="wf-sub">L3 + L5 · Postgres, single transaction.</div>
      <div class="frame pad" style="padding:8px;">
        <ul class="lbl sm" style="margin:0; padding-left:16px;">
          <li><span class="lbl mono">UPDATE grades SET ... WHERE class_id = ?</span></li>
          <li><span class="lbl mono">INSERT INTO outbox (event, payload)</span></li>
          <li><span class="lbl mono">COMMIT</span></li>
        </ul>
        <div class="lbl sm" style="margin-top:6px;">Outbox + COMMIT in <i>one</i> transaction → can't lose the event even if Kafka is momentarily down.</div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">⑤</div>
      <h3>Bus · GradePublished event</h3>
      <div class="wf-sub">L3 · Kafka topic, partitioned by classId.</div>
      <div class="frame pad" style="padding:8px;">
        <pre class="lbl mono" style="margin:0; font-size:10px; white-space:pre-wrap;">{
  "type": "GradePublished",
  "v": 1,
  "classId": "algo-ii-2025",
  "studentIds": ["s_001", ...],
  "publishedBy": "t_hadji",
  "at": "2026-05-18T10:32:11Z"
}</pre>
        <div class="lbl sm" style="margin-top:6px;">Consumers: NotifSvc, AI svc, AcademicSvc (history projector).</div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">⑥</div>
      <h3>Notification · push to 24 students</h3>
      <div class="wf-sub">L3 · NotifSvc consumes, fans out per channel.</div>
      <div class="frame pad" style="padding:8px;">
        <ul class="lbl sm" style="margin:0; padding-left:16px;">
          <li>look up each student's prefs (Mongo)</li>
          <li>push to mobile (default)</li>
          <li>email if push fails</li>
          <li>SLO: 5s end-to-end</li>
          <li>retries on 5xx with exponential backoff</li>
          <li>permanent failures → DLQ</li>
        </ul>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">⑦</div>
      <h3>Audit log</h3>
      <div class="wf-sub">L8 · append-only, tamper-evident.</div>
      <div class="frame pad" style="padding:8px;">
        <pre class="lbl mono" style="margin:0; font-size:10px; white-space:pre-wrap;">{
  "actor": "t_hadji",
  "action": "grade.publish",
  "target": "class:algo-ii-2025",
  "before": [...],
  "after": [...],
  "aiSourced": false,
  "ip": "10.4.x.x",
  "at": "..."
}</pre>
        <div class="lbl sm" style="margin-top:6px;">Retained 7 years. Searchable by the audit dashboard.</div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">⑧</div>
      <h3>AI cohort signal ✦</h3>
      <div class="wf-sub">L8 · AI consumes, never writes.</div>
      <div class="frame pad ai" style="padding:8px; background: repeating-linear-gradient(45deg, rgba(217,119,60,0.10) 0 6px, transparent 6px 12px);">
        <div class="lbl sm">AI service consumes GradePublished, checks against cohort baseline.</div>
        <div class="tile ai" style="padding:6px 8px; margin-top:6px;">
          <div class="lbl h">✦ Suggestion</div>
          <div class="lbl sm">"3 students &lt; 8/20 on this assessment. Open tutoring slot? <i>Apply / Decline</i>"</div>
        </div>
        <div class="lbl sm" style="margin-top:6px;">Surfaces in Teacher inbox + Mgmt dashboard. <b>Never auto-applied.</b></div>
      </div>
    </div>

    <div class="wf">
      <div class="wf-tag">⑨ + ⑩</div>
      <h3>Loops close</h3>
      <div class="wf-sub">L6 · Teacher and students get confirmation.</div>
      <div class="grid-2" style="gap:8px;">
        <div class="frame pad" style="padding:8px;">
          <div class="lbl h">Teacher screen</div>
          <div class="tile accent" style="padding:6px 8px; margin-top:4px;">
            <span class="lbl sm">✓ Published · 24 students notified</span>
          </div>
          <div class="lbl sm" style="margin-top:4px;">Undo available for 60s.</div>
        </div>
        <div class="frame pad" style="padding:8px;">
          <div class="lbl h">Student phone</div>
          <div class="tile" style="padding:6px 8px; margin-top:4px;">
            <div class="lbl sm" style="color:var(--ink-soft);">NovaCampus · now</div>
            <div class="lbl">New grade · Algo II · 14/20</div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Timing -->
  <div class="lbl h" style="margin-top:22px;">③ Timing · 5 seconds end-to-end</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 100" style="width:100%; height:100px;">
      <g font-family="Kalam" font-size="10" fill="#2a2620">
        <line x1="40" y1="50" x2="880" y2="50" stroke="#2a2620" stroke-width="1.5"/>
        <!-- markers -->
        <g>
          <line x1="60" y1="40" x2="60" y2="60" stroke="#2a2620" stroke-width="1.5"/>
          <text x="60" y="32" text-anchor="middle">0 ms</text>
          <text x="60" y="78" text-anchor="middle" font-size="9" fill="#5a5247">click</text>

          <line x1="160" y1="40" x2="160" y2="60" stroke="#2a2620" stroke-width="1.5"/>
          <text x="160" y="32" text-anchor="middle">~80 ms</text>
          <text x="160" y="78" text-anchor="middle" font-size="9" fill="#5a5247">JWT verified</text>

          <line x1="280" y1="40" x2="280" y2="60" stroke="#2a2620" stroke-width="1.5"/>
          <text x="280" y="32" text-anchor="middle">~150 ms</text>
          <text x="280" y="78" text-anchor="middle" font-size="9" fill="#5a5247">RBAC + validate</text>

          <line x1="430" y1="40" x2="430" y2="60" stroke="#2a2620" stroke-width="1.5"/>
          <text x="430" y="32" text-anchor="middle">~240 ms</text>
          <text x="430" y="78" text-anchor="middle" font-size="9" fill="#5a5247">DB commit + outbox</text>

          <line x1="500" y1="40" x2="500" y2="60" stroke="#D9773C" stroke-width="1.5"/>
          <text x="500" y="32" text-anchor="middle" fill="#D9773C">~280 ms</text>
          <text x="500" y="78" text-anchor="middle" font-size="9" fill="#5a5247">UI confirms ✓</text>

          <line x1="640" y1="40" x2="640" y2="60" stroke="#2a2620" stroke-width="1.5"/>
          <text x="640" y="32" text-anchor="middle">~1 s</text>
          <text x="640" y="78" text-anchor="middle" font-size="9" fill="#5a5247">Kafka delivered</text>

          <line x1="780" y1="40" x2="780" y2="60" stroke="#D9773C" stroke-width="1.5"/>
          <text x="780" y="32" text-anchor="middle" fill="#D9773C">~3-5 s</text>
          <text x="780" y="78" text-anchor="middle" font-size="9" fill="#5a5247">phones buzz</text>
        </g>
      </g>
    </svg>
    <div class="lbl sm" style="margin-top:6px; color: var(--ink-soft);">User-perceived response: &lt;300ms (well under SLO). Push delivery: &lt;5s. Audit + AI signal continue async — invisible to the user.</div>
  </div>

  <!-- What each tab contributed -->
  <div class="lbl h" style="margin-top:22px;">④ Where each LOT contributed to this story</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="tile"><div class="lbl h">L1</div><div class="lbl sm">defined "publish grades" as a process &amp; surfaced the audit/visibility need</div></div>
    <div class="tile"><div class="lbl h">L2</div><div class="lbl sm">US-23 "bulk grade entry" + US-25 "view grades" sit on this flow</div></div>
    <div class="tile"><div class="lbl h">L3</div><div class="lbl sm">microservices · event bus · outbox · UML sequence · ERD</div></div>
    <div class="tile"><div class="lbl h">L5</div><div class="lbl sm">Kafka · Postgres · K8s · observability · SLOs · canary</div></div>
    <div class="tile"><div class="lbl h">L6</div><div class="lbl sm">gradebook screen · confirm modal · student notification card</div></div>
    <div class="tile"><div class="lbl h">L7</div><div class="lbl sm">decision: events over RPC · accept eventual consistency in UI</div></div>
    <div class="tile"><div class="lbl h">L8</div><div class="lbl sm">JWT · RBAC · audit log · AI guardrails (suggest, not commit)</div></div>
    <div class="tile ai"><div class="lbl h">AI ✦</div><div class="lbl sm">cohort signal lives entirely <i>after</i> the human action — read-only consumer</div></div>
    <div class="tile"><div class="lbl h">L9</div><div class="lbl sm">this is the demo flow shown live on slide 7</div></div>
  </div>
</section>

<!-- ============ LOT 9 · PITCH ============ -->
<section class="tab-pane" data-pane="pitch">
  <div class="pane-head">
    <div>
      <h2>Defense · slide outline &amp; demo flow</h2>
      <p>10 slides, 20 minutes, story arc from audit pain → solution → AI agent → roadmap. Plus prepped Q&amp;A.</p>
    </div>
    <div class="legend"><b>Toolkit</b><br>storytelling · demo flow<br>Q&amp;A prep</div>
  </div>

  <div class="lbl h">① Slide thumbnails</div>
  <div class="grid-4" style="margin-top:6px;">
    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">01 · cover</div>
      <div class="lbl big" style="margin-top:6px;">NovaCampus</div>
      <div class="lbl sm" style="color:var(--ink-soft)">"shaping tomorrow's minds"</div>
    </div>
    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">02 · the pain</div>
      <div class="lbl h" style="margin-top:6px;">The audit</div>
      <div class="skeleton-line full" style="margin-top:6px;"></div>
      <div class="skeleton-line mid" style="margin-top:4px;"></div>
    </div>
    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">03 · users</div>
      <div class="grid-2" style="gap:3px; margin-top:6px;">
        <div class="tile" style="min-height:18px; padding:3px;"></div>
        <div class="tile" style="min-height:18px; padding:3px;"></div>
        <div class="tile" style="min-height:18px; padding:3px;"></div>
        <div class="tile" style="min-height:18px; padding:3px;"></div>
      </div>
    </div>
    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">04 · context</div>
      <div class="lbl h" style="margin-top:6px;">System map</div>
      <svg viewBox="0 0 60 26" style="width:100%;"><circle cx="10" cy="13" r="4" stroke="#2a2620" fill="none"/><rect x="22" y="6" width="16" height="14" stroke="#2a2620" fill="none"/><circle cx="50" cy="13" r="4" stroke="#2a2620" fill="none"/><line x1="14" y1="13" x2="22" y2="13" stroke="#2a2620"/><line x1="38" y1="13" x2="46" y2="13" stroke="#2a2620"/></svg>
    </div>

    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">05 · architecture</div>
      <div class="grid-3" style="gap:3px; margin-top:6px;">
        <div class="tile" style="min-height:14px; padding:2px;"></div>
        <div class="tile" style="min-height:14px; padding:2px;"></div>
        <div class="tile" style="min-height:14px; padding:2px;"></div>
        <div class="tile" style="min-height:14px; padding:2px;"></div>
        <div class="tile" style="min-height:14px; padding:2px;"></div>
        <div class="tile ai" style="min-height:14px; padding:2px;"></div>
      </div>
    </div>
    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">06 · screens</div>
      <div class="lbl h" style="margin-top:6px;">UX walk</div>
      <div class="skeleton-line full" style="margin-top:6px;"></div>
      <div class="skeleton-line short" style="margin-top:4px;"></div>
    </div>
    <div class="frame pad accent" style="padding:8px; aspect-ratio: 16/10; border-color: var(--accent);">
      <div class="lbl sm" style="color:var(--accent)">07 · ✦ AI demo</div>
      <div class="lbl h" style="margin-top:6px; color:var(--accent);">live · resolver</div>
      <div class="skeleton-line full" style="margin-top:6px;"></div>
      <div class="skeleton-line mid" style="margin-top:4px;"></div>
    </div>
    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">08 · tech</div>
      <div class="lbl h" style="margin-top:6px;">Stack</div>
      <div class="skeleton-line full" style="margin-top:6px;"></div>
      <div class="skeleton-line full" style="margin-top:4px;"></div>
      <div class="skeleton-line mid" style="margin-top:4px;"></div>
    </div>

    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">09 · roadmap</div>
      <svg viewBox="0 0 60 20" style="width:100%;"><line x1="2" y1="10" x2="58" y2="10" stroke="#2a2620"/><circle cx="10" cy="10" r="2" fill="#2a2620"/><circle cx="25" cy="10" r="2" fill="#2a2620"/><circle cx="40" cy="10" r="2" fill="#D9773C"/><circle cx="55" cy="10" r="2" fill="#a89e8a"/></svg>
    </div>
    <div class="frame pad" style="padding:8px; aspect-ratio: 16/10;">
      <div class="lbl sm">10 · Q&amp;A</div>
      <div class="lbl h" style="margin-top:6px;">Thank you</div>
      <div class="lbl sm" style="color:var(--ink-soft); margin-top:6px;">questions →</div>
    </div>
  </div>

  <!-- Demo flow -->
  <div class="lbl h" style="margin-top:18px;">② Demo flow · 5 minutes</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 80" style="width:100%; height:80px;">
      <g font-family="Kalam" font-size="12" fill="#2a2620">
        <line x1="20" y1="40" x2="880" y2="40" stroke="#2a2620" stroke-width="1.6"/>
        <g>
          <circle cx="80" cy="40" r="6" fill="#2a2620"/><text x="80" y="22" text-anchor="middle" font-family="Caveat" font-size="14">login</text><text x="80" y="62" text-anchor="middle" font-size="10" fill="#5a5247">admin · campus B</text>
          <circle cx="220" cy="40" r="6" fill="#2a2620"/><text x="220" y="22" text-anchor="middle" font-family="Caveat" font-size="14">inbox</text><text x="220" y="62" text-anchor="middle" font-size="10" fill="#5a5247">conflict surfaces</text>
          <circle cx="360" cy="40" r="6" fill="#D9773C"/><text x="360" y="22" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">✦ AI proposal</text><text x="360" y="62" text-anchor="middle" font-size="10" fill="#5a5247">move B-204 → B-118</text>
          <circle cx="500" cy="40" r="6" fill="#2a2620"/><text x="500" y="22" text-anchor="middle" font-family="Caveat" font-size="14">apply</text><text x="500" y="62" text-anchor="middle" font-size="10" fill="#5a5247">event fires</text>
          <circle cx="640" cy="40" r="6" fill="#2a2620"/><text x="640" y="22" text-anchor="middle" font-family="Caveat" font-size="14">student app</text><text x="640" y="62" text-anchor="middle" font-size="10" fill="#5a5247">push within 60s</text>
          <circle cx="800" cy="40" r="6" fill="#2a2620"/><text x="800" y="22" text-anchor="middle" font-family="Caveat" font-size="14">mgmt KPI</text><text x="800" y="62" text-anchor="middle" font-size="10" fill="#5a5247">conflicts ↓</text>
        </g>
      </g>
    </svg>
  </div>

  <!-- Q&A prep -->
  <div class="lbl h" style="margin-top:18px;">③ Expected questions · prepared answers</div>
  <div class="grid-2" style="margin-top:6px;">
    <div class="tile"><div class="lbl h">"Why microservices? Isn't a monolith simpler?"</div><div class="lbl sm">→ ADR-001. Modules have very different load profiles &amp; data lifetimes; we keep the boundary small (6 services, not 30).</div></div>
    <div class="tile"><div class="lbl h">"How is data isolated between campuses?"</div><div class="lbl sm">→ ADR-005 + JWT scopes. Single DB per service, campusId column, row-level security, tested in CI.</div></div>
    <div class="tile ai"><div class="lbl h">"What if the AI hallucinates a room move?"</div><div class="lbl sm">→ Agent calls tools that already enforce capacity/clash checks. The model can suggest but never commit; humans approve.</div></div>
    <div class="tile"><div class="lbl h">"What's the cost of running this?"</div><div class="lbl sm">→ Managed PG + small K8s + 1 GPU node for AI. Numbers in the appendix slide.</div></div>
    <div class="tile"><div class="lbl h">"What did you intentionally NOT build?"</div><div class="lbl sm">→ HR/payroll, LMS content, alumni CRM. MoSCoW "Won't" — out of scope, can integrate later.</div></div>
    <div class="tile"><div class="lbl h">"How will success be measured?"</div><div class="lbl sm">→ 3 KPIs: room conflicts/month ↓, days-late on invoices ↓, audit-cycle prep time ↓.</div></div>
  </div>

  <!-- Storytelling arc -->
  <div class="lbl h" style="margin-top:22px;">④ Storytelling structure · the narrative arc</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <svg viewBox="0 0 900 180" style="width:100%; height:auto;">
      <g font-family="Kalam" font-size="11" fill="#2a2620">
        <!-- emotional arc curve -->
        <path d="M 30,140 C 120,140 150,100 220,90 C 300,80 340,140 420,150 C 500,160 550,80 640,55 C 720,35 780,30 870,30"
              fill="none" stroke="#D9773C" stroke-width="2" stroke-dasharray="5 4"/>
        <!-- baseline -->
        <line x1="30" y1="160" x2="870" y2="160" stroke="#2a2620"/>
        <!-- markers -->
        <g>
          <circle cx="80" cy="140" r="5" fill="#2a2620"/>
          <text x="80" y="175" text-anchor="middle" font-family="Caveat" font-size="14">setup</text>
          <text x="80" y="130" text-anchor="middle" font-size="10" fill="#5a5247">the school</text>

          <circle cx="220" cy="90" r="5" fill="#2a2620"/>
          <text x="220" y="175" text-anchor="middle" font-family="Caveat" font-size="14">tension</text>
          <text x="220" y="80" text-anchor="middle" font-size="10" fill="#5a5247">audit failure</text>

          <circle cx="420" cy="150" r="5" fill="#2a2620"/>
          <text x="420" y="175" text-anchor="middle" font-family="Caveat" font-size="14">low point</text>
          <text x="420" y="140" text-anchor="middle" font-size="10" fill="#5a5247">"craft-based"</text>

          <circle cx="560" cy="100" r="5" fill="#2a2620"/>
          <text x="560" y="175" text-anchor="middle" font-family="Caveat" font-size="14">approach</text>
          <text x="560" y="90" text-anchor="middle" font-size="10" fill="#5a5247">ERP + UX</text>

          <circle cx="700" cy="50" r="6" fill="#D9773C"/>
          <text x="700" y="175" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">✦ the win</text>
          <text x="700" y="40" text-anchor="middle" font-size="10" fill="#D9773C">AI demo · live</text>

          <circle cx="860" cy="30" r="5" fill="#2a2620"/>
          <text x="860" y="175" text-anchor="middle" font-family="Caveat" font-size="14">future</text>
          <text x="860" y="20" text-anchor="middle" font-size="10" fill="#5a5247">roadmap · 2× size</text>
        </g>
      </g>
    </svg>
    <div class="grid-3" style="margin-top:8px;">
      <div class="tile"><div class="lbl h">① Setup (slides 1-3)</div><div class="lbl sm">"Here's NovaCampus today — growing, 4 campuses, 2.8k students."</div></div>
      <div class="tile"><div class="lbl h">② Tension (slides 4-5)</div><div class="lbl sm">"The audit. The interviews. The four-schools-pretending-to-be-one problem."</div></div>
      <div class="tile accent"><div class="lbl h">③ Solution (slides 6-8)</div><div class="lbl sm">"One ERP. Role-based. Event-driven. Designed against constraints."</div></div>
      <div class="tile ai"><div class="lbl h">④ ✦ AI demo (slide 7)</div><div class="lbl sm">The hero moment. Live, in-product. Not a video.</div></div>
      <div class="tile"><div class="lbl h">⑤ Tech (slide 8)</div><div class="lbl sm">"Here's why we chose what we chose, and what we said no to."</div></div>
      <div class="tile"><div class="lbl h">⑥ Future (slides 9-10)</div><div class="lbl sm">"How this scales to 8 campuses. Thank you. Questions."</div></div>
    </div>
  </div>

  <!-- ELI5 architecture -->
  <div class="lbl h" style="margin-top:22px;">⑤ Architecture · explain it in 30 seconds</div>
  <div class="grid-2" style="margin-top:6px;">
    <div class="frame pad" style="padding:14px;">
      <div class="lbl sm" style="color: var(--ink-soft);">FOR THE PANEL · 30 sec version</div>
      <div class="lbl h" style="margin-top:6px;">"It's a teaching hospital, not a clinic."</div>
      <div class="lbl" style="margin-top:8px; line-height:1.5;">
        Old ERPs are like a clinic — one doctor, one room, one filing cabinet. When the
        school grew to four campuses, that cabinet exploded.<br><br>
        Ours is a <b>hospital</b>: separate <b>departments</b> (the services) — admissions,
        academics, finance, notifications, AI — each with their own staff and records,
        coordinated through a central <b>intercom</b> (the event bus). One reception desk
        (the API gateway) routes every visitor to the right place.<br><br>
        Adding a campus = adding more chairs in the waiting rooms, not building a new
        hospital.
      </div>
    </div>
    <div class="frame pad" style="padding:14px;">
      <div class="lbl sm" style="color: var(--ink-soft);">CONCEPT MAP · same idea, visually</div>
      <svg viewBox="0 0 400 240" style="width:100%; height:auto; margin-top:4px;">
        <g font-family="Kalam" font-size="11" fill="#2a2620">
          <!-- reception -->
          <rect x="20" y="100" width="80" height="40" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C" stroke-width="2"/>
          <text x="60" y="118" text-anchor="middle" font-family="Caveat" font-size="14" fill="#D9773C">Reception</text>
          <text x="60" y="132" text-anchor="middle" font-size="9" fill="#5a5247">(gateway)</text>

          <!-- departments -->
          <g>
            <rect x="150" y="20" width="80" height="34" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
            <text x="190" y="42" text-anchor="middle">Admissions</text>
            <rect x="150" y="64" width="80" height="34" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
            <text x="190" y="86" text-anchor="middle">Academics</text>
            <rect x="150" y="108" width="80" height="34" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
            <text x="190" y="130" text-anchor="middle">Finance</text>
            <rect x="150" y="152" width="80" height="34" rx="6" fill="rgba(255,255,255,0.7)" stroke="#2a2620"/>
            <text x="190" y="174" text-anchor="middle">Notifications</text>
            <rect x="150" y="196" width="80" height="34" rx="6" fill="rgba(217,119,60,0.10)" stroke="#D9773C"/>
            <text x="190" y="218" text-anchor="middle" fill="#D9773C">AI consult ✦</text>
          </g>

          <!-- intercom -->
          <rect x="280" y="90" width="100" height="60" rx="6" fill="rgba(42,38,32,0.06)" stroke="#2a2620" stroke-dasharray="4 4"/>
          <text x="330" y="118" text-anchor="middle" font-family="Caveat" font-size="14">Intercom</text>
          <text x="330" y="135" text-anchor="middle" font-size="9" fill="#5a5247">(events)</text>

          <!-- connections -->
          <g stroke="#2a2620" stroke-width="1.1" fill="none">
            <line x1="100" y1="115" x2="150" y2="37"/>
            <line x1="100" y1="118" x2="150" y2="80"/>
            <line x1="100" y1="120" x2="150" y2="125"/>
            <line x1="100" y1="123" x2="150" y2="170"/>
            <line x1="100" y1="125" x2="150" y2="210" stroke="#D9773C"/>

            <line x1="230" y1="37" x2="280" y2="100" stroke-dasharray="2 3"/>
            <line x1="230" y1="80" x2="280" y2="110" stroke-dasharray="2 3"/>
            <line x1="230" y1="125" x2="280" y2="120" stroke-dasharray="2 3"/>
            <line x1="230" y1="170" x2="280" y2="135" stroke-dasharray="2 3"/>
            <line x1="230" y1="210" x2="280" y2="145" stroke-dasharray="2 3" stroke="#D9773C"/>
          </g>
        </g>
      </svg>
    </div>
  </div>

  <!-- Demo backup plan -->
  <div class="lbl h" style="margin-top:22px;">⑥ Demo backup plan · "if the demo gods are angry"</div>
  <div class="grid-3" style="margin-top:6px;">
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Plan A · live demo</div>
      <div class="lbl sm" style="margin-top:4px; color:var(--ink-soft);">primary</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>local environment, pre-seeded data</li>
        <li>tested 24h before defense</li>
        <li>offline-capable demo dataset</li>
        <li>2 laptops · one as backup</li>
      </ul>
    </div>
    <div class="frame pad" style="padding:12px;">
      <div class="lbl h">Plan B · recorded screencast</div>
      <div class="lbl sm" style="margin-top:4px; color:var(--ink-soft);">if network / laptop fails</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>full demo flow pre-recorded</li>
        <li>narrated, &lt; 4 minutes</li>
        <li>USB stick + cloud copy</li>
        <li>plays on any laptop</li>
      </ul>
    </div>
    <div class="frame pad accent" style="padding:12px; border-color: var(--accent);">
      <div class="lbl h">Plan C · screenshots in slides</div>
      <div class="lbl sm" style="margin-top:4px; color:var(--ink-soft);">if all else fails</div>
      <ul class="lbl sm" style="margin:6px 0 0; padding-left:16px;">
        <li>annotated screenshots of every screen</li>
        <li>embedded directly in slide deck</li>
        <li>narrate the flow verbally</li>
        <li>printed deck handout as final fallback</li>
      </ul>
    </div>
  </div>

  <!-- Team speaking allocation -->
  <div class="lbl h" style="margin-top:22px;">⑦ Team speaking allocation</div>
  <div class="frame pad" style="padding:10px; margin-top:6px;">
    <div style="display:grid; grid-template-columns: 100px 1fr 1fr 60px; gap:4px;">
      <div class="lbl sm" style="font-weight:700;">Slides</div>
      <div class="lbl sm" style="font-weight:700;">Topic</div>
      <div class="lbl sm" style="font-weight:700;">Speaker</div>
      <div class="lbl sm" style="font-weight:700;">Time</div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">01–02</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Intro · audit · business case</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Business lead</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">3 min</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">03–04</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Users · context · stakeholders</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">UX lead</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">2 min</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">05</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Architecture · services · events</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Architect</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">3 min</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">06</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">UX walkthrough · 4 roles</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">UX lead</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">3 min</span></div>

      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">07 ✦</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">AI agent · LIVE demo</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">AI lead</span></div>
      <div class="tile accent" style="padding:4px 6px;"><span class="lbl sm">4 min</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">08</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Tech stack · why these choices</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Architect</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">2 min</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">09</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Roadmap · success metrics</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Business lead</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">2 min</span></div>

      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">10</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">Q&amp;A</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">whole team</span></div>
      <div class="tile" style="padding:4px 6px;"><span class="lbl sm">+10 min</span></div>
    </div>
    <div class="lbl sm" style="margin-top:8px; color: var(--ink-soft);">~ 20 min talk + 10 min Q&amp;A. Each speaker rehearses their slide solo, then together end-to-end.</div>
  </div>

  <!-- Known limitations -->
  <div class="lbl h" style="margin-top:22px;">⑧ Known limitations · what we're <i>not</i> claiming</div>
  <div class="frame pad" style="padding:14px; margin-top:6px;">
    <div class="lbl" style="margin-bottom:8px;">Saying this out loud disarms half the jury's questions.</div>
    <div class="grid-2">
      <div class="tile">
        <div class="lbl h">Prototype scope</div>
        <div class="lbl sm" style="margin-top:4px;">Mobile app is a prototype — not a production iOS/Android build. Demo runs on the web mock.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Synthetic data</div>
        <div class="lbl sm" style="margin-top:4px;">We tested with seeded data, not 6 years of real NovaCampus records. Migration risk is real.</div>
      </div>
      <div class="tile ai">
        <div class="lbl h">AI is supervised ✦</div>
        <div class="lbl sm" style="margin-top:4px;">The agent never commits a decision. Even at scale it stays human-in-the-loop. Autonomy is out of scope.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Real-world testing</div>
        <div class="lbl sm" style="margin-top:4px;">No live pilot yet. KPIs are projected from comparable SIS deployments &amp; the audit baseline.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Load testing</div>
        <div class="lbl sm" style="margin-top:4px;">We modelled load to 2,800 students; haven't stress-tested 10,000 yet. Sprint 6 work.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Out-of-scope modules</div>
        <div class="lbl sm" style="margin-top:4px;">HR payroll, LMS content, library, alumni CRM — explicitly "Won't" in MoSCoW.</div>
      </div>
      <div class="tile">
        <div class="lbl h">Integration assumptions</div>
        <div class="lbl sm" style="margin-top:4px;">We assume existing payment gateway exposes a usable API. Confirmation pending.</div>
      </div>
      <div class="tile">
        <div class="lbl h">i18n in v1</div>
        <div class="lbl sm" style="margin-top:4px;">FR + EN ready. AR-RTL in v1.1 — needs RTL-specific UX testing.</div>
      </div>
    </div>
  </div>

  <!-- Pre-defense checklist -->
  <div class="lbl h" style="margin-top:22px;">⑨ Pre-defense checklist</div>
  <div class="frame pad" style="padding:12px; margin-top:6px;">
    <div class="grid-3">
      <ul class="lbl sm" style="margin:0; padding-left:18px;">
        <li>☐ slides finalised + spelled-checked</li>
        <li>☐ printouts of slides as handouts</li>
        <li>☐ demo data seeded</li>
        <li>☐ Plan B screencast on USB</li>
      </ul>
      <ul class="lbl sm" style="margin:0; padding-left:18px;">
        <li>☐ each speaker rehearsed solo</li>
        <li>☐ team end-to-end run-through ×2</li>
        <li>☐ Q&amp;A round with practice jury</li>
        <li>☐ backup laptop tested</li>
      </ul>
      <ul class="lbl sm" style="margin:0; padding-left:18px;">
        <li>☐ adapters · HDMI · USB-C</li>
        <li>☐ fonts embedded in deck</li>
        <li>☐ phone on silent · sleep disabled</li>
        <li>☐ 8 hrs of sleep before</li>
      </ul>
    </div>
  </div>
</section>

<footer class="foot">
  <span>NovaCampus Alliance · internal wireframes · DRAFT v0.1</span>
  <span>tap ⚙ Tweaks · drawn for review, not implementation</span>
</footer>

</main>

<!-- Tweaks panel -->
<div id="tweaks">
  <h5>Tweaks <button id="close-tweaks">×</button></h5>
  <div class="group">
    <label>Accent color</label>
    <div class="swatches" id="sw-accent">
      <div class="sw on" data-c="oklch(0.66 0.16 55)" style="background:oklch(0.66 0.16 55)"></div>
      <div class="sw" data-c="oklch(0.55 0.13 200)" style="background:oklch(0.55 0.13 200)"></div>
      <div class="sw" data-c="oklch(0.55 0.16 145)" style="background:oklch(0.55 0.16 145)"></div>
      <div class="sw" data-c="oklch(0.55 0.18 25)" style="background:oklch(0.55 0.18 25)"></div>
      <div class="sw" data-c="oklch(0.50 0.16 290)" style="background:oklch(0.50 0.16 290)"></div>
    </div>
  </div>
  <div class="group">
    <label>Paper lines</label>
    <div class="row-opts" id="opt-lines">
      <button class="on" data-v="on">on</button>
      <button data-v="off">off</button>
    </div>
  </div>
  <div class="group">
    <label>Annotations</label>
    <div class="row-opts" id="opt-annot">
      <button class="on" data-v="on">show</button>
      <button data-v="off">hide</button>
    </div>
  </div>
  <div class="group">
    <label>Density</label>
    <div class="row-opts" id="opt-dens">
      <button data-v="loose">loose</button>
      <button class="on" data-v="normal">normal</button>
      <button data-v="tight">tight</button>
    </div>
  </div>
</div>

<script>
  // Tab switching
  const tabs = document.querySelectorAll('#tabs button[data-tab]');
  const panes = document.querySelectorAll('.tab-pane');
  tabs.forEach(b => b.addEventListener('click', () => {
    tabs.forEach(t => t.classList.toggle('active', t === b));
    panes.forEach(p => p.classList.toggle('active', p.dataset.pane === b.dataset.tab));
    window.scrollTo({top: 0, behavior: 'smooth'});
  }));

  // Tweaks
  const tweaks = document.getElementById('tweaks');
  document.getElementById('open-tweaks').addEventListener('click', () => tweaks.classList.toggle('open'));
  document.getElementById('close-tweaks').addEventListener('click', () => tweaks.classList.remove('open'));

  document.querySelectorAll('#sw-accent .sw').forEach(s => s.addEventListener('click', () => {
    document.querySelectorAll('#sw-accent .sw').forEach(x => x.classList.remove('on'));
    s.classList.add('on');
    document.documentElement.style.setProperty('--accent', s.dataset.c);
  }));

  function bindOpts(id, fn) {
    const root = document.getElementById(id);
    root.querySelectorAll('button').forEach(b => b.addEventListener('click', () => {
      root.querySelectorAll('button').forEach(x => x.classList.remove('on'));
      b.classList.add('on');
      fn(b.dataset.v);
    }));
  }
  bindOpts('opt-lines', v => document.body.classList.toggle('no-lines', v === 'off'));
  bindOpts('opt-annot', v => document.body.classList.toggle('no-annot', v === 'off'));
  bindOpts('opt-dens', v => {
    document.documentElement.style.setProperty('--gap', v === 'tight' ? '14px' : v === 'loose' ? '32px' : '22px');
    document.querySelectorAll('.variants').forEach(el => el.style.gap = v === 'tight' ? '14px' : v === 'loose' ? '32px' : '22px');
  });
</script>

</body>
</html>
