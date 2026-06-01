# portfolio
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Aquaponics System — Anton Mueller</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=IBM+Plex+Mono:wght@400;500&family=IBM+Plex+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #fafaf8;
    --surface: #f2f1ed;
    --border: rgba(0,0,0,0.1);
    --border-mid: rgba(0,0,0,0.18);
    --text: #1a1a18;
    --muted: #6b6b67;
    --hint: #9e9e99;
    --accent: #2a4a3e;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'IBM Plex Sans', sans-serif;
    font-weight: 300;
    line-height: 1.6;
    padding: 3rem 2.5rem 4rem;
    max-width: 780px;
    margin: 0 auto;
  }

  /* ── HEADER ── */
  .kicker {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--hint);
    margin-bottom: 0.75rem;
    animation: fadeUp 0.5s ease both;
  }

  h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(30px, 5vw, 44px);
    font-weight: 700;
    line-height: 1.1;
    color: var(--text);
    margin-bottom: 0.75rem;
    animation: fadeUp 0.5s 0.07s ease both;
  }

  .subline {
    font-size: 15px;
    color: var(--muted);
    max-width: 540px;
    margin-bottom: 1.5rem;
    animation: fadeUp 0.5s 0.14s ease both;
  }

  /* ── TAGS ── */
  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 7px;
    margin-bottom: 2.25rem;
    animation: fadeUp 0.5s 0.2s ease both;
  }
  .tag {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10.5px;
    padding: 4px 11px;
    border: 0.5px solid var(--border-mid);
    border-radius: 3px;
    color: var(--muted);
    letter-spacing: 0.04em;
  }

  /* ── DIVIDER ── */
  hr {
    border: none;
    border-top: 0.5px solid var(--border);
    margin-bottom: 2rem;
    animation: fadeUp 0.5s 0.24s ease both;
  }

  /* ── MEDIA GRID ── */
  .media-grid {
    display: grid;
    grid-template-columns: 2fr 1fr;
    grid-template-rows: 210px 185px;
    gap: 6px;
    margin-bottom: 2.25rem;
    border-radius: 10px;
    overflow: hidden;
    animation: fadeUp 0.6s 0.3s ease both;
  }
  .img-wrap {
    overflow: hidden;
    position: relative;
    background: var(--surface);
  }
  .img-wrap img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.5s ease;
  }
  .img-wrap:hover img { transform: scale(1.05); }
  .img-wrap.tall { grid-row: span 2; grid-column: 2; }
  .img-label {
    position: absolute;
    bottom: 9px;
    left: 11px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9.5px;
    color: #fff;
    background: rgba(0,0,0,0.48);
    padding: 2px 8px;
    border-radius: 3px;
    letter-spacing: 0.07em;
  }

  /* ── STATS ── */
  .stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--border);
    border: 0.5px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 2.25rem;
    animation: fadeUp 0.5s 0.38s ease both;
  }
  .stat {
    background: var(--bg);
    padding: 1.1rem 1.25rem;
    text-align: center;
  }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    font-weight: 700;
    color: var(--text);
    line-height: 1;
    margin-bottom: 5px;
  }
  .stat-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--hint);
  }

  /* ── BODY TEXT ── */
  .body-text {
    font-size: 15px;
    line-height: 1.8;
    color: var(--muted);
    max-width: 640px;
    margin-bottom: 2rem;
    animation: fadeUp 0.5s 0.44s ease both;
  }
  .body-text strong {
    color: var(--text);
    font-weight: 500;
  }

  /* ── FEATURE CARDS ── */
  .features {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
    margin-bottom: 2rem;
    animation: fadeUp 0.5s 0.5s ease both;
  }
  .feature {
    display: flex;
    gap: 12px;
    align-items: flex-start;
    padding: 13px 15px;
    border: 0.5px solid var(--border);
    border-radius: 8px;
    background: var(--bg);
    transition: border-color 0.2s, background 0.2s;
  }
  .feature:hover {
    border-color: var(--border-mid);
    background: var(--surface);
  }
  .feat-icon {
    font-size: 18px;
    margin-top: 2px;
    flex-shrink: 0;
    color: var(--accent);
  }
  .feat-title {
    font-size: 13px;
    font-weight: 500;
    margin-bottom: 3px;
    color: var(--text);
  }
  .feat-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.55;
  }

  /* ── AWARD BAR ── */
  .award {
    display: flex;
    align-items: center;
    gap: 13px;
    padding: 14px 18px;
    background: var(--surface);
    border-radius: 8px;
    border: 0.5px solid var(--border);
    animation: fadeUp 0.5s 0.56s ease both;
  }
  .award-icon { font-size: 20px; color: var(--accent); }
  .award-title { font-size: 14px; font-weight: 500; color: var(--text); }
  .award-sub {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    color: var(--hint);
    margin-top: 2px;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(12px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 520px) {
    body { padding: 2rem 1.25rem 3rem; }
    .media-grid { grid-template-columns: 1fr; grid-template-rows: 200px 160px 200px; }
    .img-wrap.tall { grid-row: auto; grid-column: auto; }
    .features { grid-template-columns: 1fr; }
    .stats { grid-template-columns: repeat(3,1fr); }
  }
</style>
</head>
<body>

<p class="kicker">Engineering Design · Year 1 · Team Project</p>
<h1>Closed-Loop<br>Aquaponics System</h1>
<p class="subline">A vertical, greenhouse-integrated food production system combining fish waste nutrient cycling, closed-loop water recycling, and treated wastewater inputs.</p>

<div class="tags">
  <span class="tag">Vertical Stacking</span>
  <span class="tag">Water Recycling</span>
  <span class="tag">CAD / Fabrication</span>
  <span class="tag">Sustainable Design</span>
  <span class="tag">Systems Integration</span>
</div>

<hr />

<div class="media-grid">
  <div class="img-wrap">
    <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800&q=80" alt="3D CAD render" />
    <span class="img-label">3D system render</span>
  </div>
  <div class="img-wrap tall">
    <img src="https://images.unsplash.com/photo-1416879595882-3373a0480b5b?w=400&q=80" alt="Greenhouse" />
    <span class="img-label">Greenhouse structure</span>
  </div>
  <div class="img-wrap">
    <img src="https://images.unsplash.com/photo-1530836369250-ef72a3f5cda8?w=800&q=80" alt="Technical drawings" />
    <span class="img-label">Assembly drawings</span>
  </div>
</div>

<div class="stats">
  <div class="stat">
    <div class="stat-num">2nd</div>
    <div class="stat-label">Showcase place</div>
  </div>
  <div class="stat">
    <div class="stat-num">6</div>
    <div class="stat-label">Team members</div>
  </div>
  <div class="stat">
    <div class="stat-num">3×</div>
    <div class="stat-label">Water reuse loops</div>
  </div>
</div>

<p class="body-text">
  Designed and built as part of a first-year engineering design course, our team of six placed
  <strong>2nd at the Engineering Aquaponics Showcase.</strong>
  The system integrated vertical stacking, closed-loop water recycling, and treated wastewater as a nutrient input —
  combining multiple sustainable methods into one cohesive design. Aquaponics offers
  <strong>high yields at a fraction of the resource consumption</strong> of conventional farming.
  The greenhouse structure was designed to house the full system within a compact, scalable footprint.
</p>

<div class="features">
  <div class="feature">
    <svg class="feat-icon" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="19" x2="12" y2="5"/><polyline points="5 12 12 5 19 12"/></svg>
    <div>
      <div class="feat-title">Vertical stacking</div>
      <div class="feat-desc">Maximised grow area per square metre inside a fixed greenhouse footprint</div>
    </div>
  </div>
  <div class="feature">
    <svg class="feat-icon" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="1 4 1 10 7 10"/><path d="M3.51 15a9 9 0 1 0 .49-5"/></svg>
    <div>
      <div class="feat-title">Closed-loop water</div>
      <div class="feat-desc">Fish waste recirculated as plant nutrients, minimising fresh water draw</div>
    </div>
  </div>
  <div class="feature">
    <svg class="feat-icon" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2v6m0 0c-3.3 0-6 2.7-6 6s2.7 6 6 6 6-2.7 6-6-2.7-6-6-6z"/></svg>
    <div>
      <div class="feat-title">Wastewater input</div>
      <div class="feat-desc">Treated wastewater used as a nutrient input stream for the grow beds</div>
    </div>
  </div>
  <div class="feature">
    <svg class="feat-icon" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 21V9"/></svg>
    <div>
      <div class="feat-title">Greenhouse shell</div>
      <div class="feat-desc">Full structural design drawn to scale, dimensioned for fabrication</div>
    </div>
  </div>
</div>

<div class="award">
  <svg class="award-icon" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="8 6 12 2 16 6"/><path d="M12 2v13"/><path d="M5 20h14a2 2 0 0 0 1.84-2.75L12 12 3.16 17.25A2 2 0 0 0 5 20z"/></svg>
  <div>
    <div class="award-title">2nd Place — Engineering Aquaponics Showcase</div>
    <div class="award-sub">First-year design course · Team of six</div>
  </div>
</div>

</body>
</html>
