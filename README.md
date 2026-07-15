<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pulindu Godage — Full Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0B0F14;
    --card:#111721;
    --card-2:#0D1319;
    --border: rgba(255,255,255,0.08);
    --border-soft: rgba(255,255,255,0.06);
    --accent:#3B9EFF;
    --accent-2:#5CC8FF;
    --text:#F2F5F8;
    --text-dim:#9AA6B2;
    --text-faint:#5C6773;
    --font-head:'Poppins', sans-serif;
    --font-body:'Inter', sans-serif;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:var(--font-body);
    line-height:1.55;
    position:relative;
    overflow-x:hidden;
  }
  .bg-fixed{ position:fixed; inset:0; z-index:0; pointer-events:none; overflow:hidden;}
  .bg-grid{
    position:absolute; inset:-2px;
    background-image:
      linear-gradient(rgba(59,158,255,0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(59,158,255,0.05) 1px, transparent 1px);
    background-size:48px 48px;
    mask-image: radial-gradient(ellipse 75% 55% at 50% 15%, black 20%, transparent 75%);
  }
  .bg-glow{ position:absolute; border-radius:50%; filter:blur(100px); opacity:0.28;}
  .glow-1{ width:520px; height:520px; top:-160px; left:-120px; background:radial-gradient(circle, #1F6FEB, transparent 70%);}
  .glow-2{ width:560px; height:560px; top:120px; right:-200px; background:radial-gradient(circle, #39D6FF, transparent 70%); opacity:0.18;}

  .wrap{ position:relative; z-index:1; max-width:1040px; margin:0 auto; padding:56px 32px 40px;}

  .card{
    background:var(--card);
    border:1px solid var(--border);
    border-radius:18px;
  }

  section{ margin-bottom:44px; }

  /* ============ HERO ============ */
  .hero{
    padding:44px 48px;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:20px;
    align-items:center;
    overflow:hidden;
    position:relative;
  }
  .hero-name{
    font-family:var(--font-head);
    font-weight:800;
    font-size:44px;
    letter-spacing:-0.01em;
    color:#FFFFFF;
    margin-bottom:8px;
  }
  .hero-role{
    font-family:var(--font-head);
    font-weight:600;
    font-size:21px;
    color:var(--accent-2);
    margin-bottom:18px;
  }
  .hero-bio{
    color:var(--text-dim);
    font-size:15px;
    max-width:400px;
    margin-bottom:26px;
  }
  .contact-list{ display:flex; flex-direction:column; gap:13px; }
  .contact-item{ display:flex; align-items:center; gap:12px; font-size:14.5px; color:#D7DEE5; }
  .contact-item .ic-wrap{
    width:30px; height:30px; border-radius:8px;
    display:flex; align-items:center; justify-content:center;
    background:rgba(59,158,255,0.12);
    flex-shrink:0;
  }
  .contact-item svg{ width:15px; height:15px; color:var(--accent-2); }

  .hero-visual{ position:relative; height:300px; }
  .hex-badge{
    position:absolute;
    width:56px; height:56px;
    filter:drop-shadow(0 0 10px rgba(59,158,255,0.35));
    animation: floaty 5.5s ease-in-out infinite;
  }
  @keyframes floaty{ 0%,100%{transform:translateY(0);} 50%{transform:translateY(-9px);} }
  .hx1{ top:-6%; left:2%; animation-delay:0s;}
  .hx2{ top:-10%; left:42%; animation-delay:.6s;}
  .hx3{ top:0%; right:0%; animation-delay:1.1s;}
  .hx4{ top:38%; left:-6%; animation-delay:1.6s;}
  .hx5{ top:34%; right:-4%; animation-delay:.3s;}
  .hx6{ bottom:2%; right:14%; animation-delay:.9s;}

  /* ============ INTRO ============ */
  .intro{ text-align:center; padding:6px 0 8px; }
  .intro h2{
    font-family:var(--font-head);
    font-weight:700;
    font-size:27px;
    margin-bottom:8px;
  }
  .intro p{ color:var(--text-dim); font-size:15px; margin-bottom:20px;}
  .views-pill{
    display:inline-flex; align-items:center; gap:0;
    border-radius:100px;
    overflow:hidden;
    border:1px solid var(--border);
    font-size:13px;
    font-weight:500;
  }
  .views-pill span{ padding:9px 16px; display:flex; align-items:center; gap:7px;}
  .views-pill span:first-child{ color:var(--text-dim); background:var(--card);}
  .views-pill span:last-child{ background:var(--accent); color:#fff; font-weight:700;}
  .views-pill svg{ width:14px; height:14px; }

  /* ============ SECTION HEAD ============ */
  .head-row{ display:flex; align-items:center; gap:10px; margin-bottom:16px; padding-bottom:14px; border-bottom:1px solid var(--border-soft);}
  .head-row svg{ width:19px; height:19px; color:var(--accent);}
  .head-row h3{ font-family:var(--font-head); font-size:19px; font-weight:700;}

  /* ============ ABOUT ============ */
  .about-list{ list-style:none; display:flex; flex-direction:column; gap:12px; padding:6px 30px 4px 0;}
  .about-list li{ display:flex; gap:12px; font-size:14.5px; color:#D7DEE5; align-items:flex-start;}
  .about-list li .em{ flex-shrink:0; }

  /* ============ STACK ============ */
  .stack-row{ display:grid; grid-template-columns:130px 1fr; gap:10px; padding:18px 0; border-bottom:1px solid var(--border-soft);}
  .stack-row:last-child{ border-bottom:none; }
  .stack-row .cat-label{ font-size:14px; color:var(--text-dim); font-weight:500; padding-top:10px;}
  .stack-icons{ display:flex; flex-wrap:wrap; gap:26px;}
  .tech-item{ display:flex; flex-direction:column; align-items:center; gap:8px; width:58px;}
  .tech-item .box{
    width:52px; height:52px; border-radius:13px;
    display:flex; align-items:center; justify-content:center;
    box-shadow:0 6px 16px -6px rgba(0,0,0,0.5);
  }
  .tech-item .box svg{ width:28px; height:28px; }
  .tech-item .lbl{ font-size:11px; color:var(--text-dim); text-align:center; line-height:1.2;}

  /* ============ STATS ============ */
  .stats-grid{ display:grid; grid-template-columns:1.15fr 1fr 0.85fr; gap:18px; }
  .stat-card{ padding:22px 24px; }
  .stat-card h4{ font-family:var(--font-head); font-size:14.5px; font-weight:600; color:var(--accent-2); margin-bottom:16px;}
  .stat-card.split{ display:flex; align-items:center; justify-content:space-between; gap:14px;}
  .stat-list{ flex:1; }
  .stat-line{ display:flex; align-items:center; justify-content:space-between; padding:8px 0; font-size:13.5px;}
  .stat-line .l{ display:flex; align-items:center; gap:8px; color:var(--text-dim);}
  .stat-line .l svg{ width:14px; height:14px; color:var(--text-faint);}
  .stat-line .v{ font-weight:700; color:var(--text); font-family:var(--font-head); font-size:13.5px;}
  .grade{
    width:76px; height:76px; border-radius:50%;
    border:3px solid var(--accent);
    display:flex; align-items:center; justify-content:center;
    font-family:var(--font-head); font-weight:800; font-size:20px; color:var(--accent-2);
    box-shadow:0 0 22px -4px rgba(59,158,255,0.55);
    flex-shrink:0;
  }
  .donut-row{ display:flex; align-items:center; gap:20px;}
  .donut{
    width:100px; height:100px; border-radius:50%; flex-shrink:0;
    background: conic-gradient(#F7DF1E 0deg 139deg, #3178C6 139deg 194deg, #E76F00 194deg 335deg, #61DAFB 335deg 358deg, #6A737D 358deg 360deg);
    position:relative;
  }
  .donut::after{ content:''; position:absolute; inset:15px; border-radius:50%; background:var(--card); }
  .lang-legend{ display:flex; flex-direction:column; gap:7px; font-size:12.5px; }
  .lang-legend .row{ display:flex; align-items:center; gap:8px; color:var(--text-dim);}
  .lang-legend .sw{ width:8px; height:8px; border-radius:2px; flex-shrink:0;}
  .lang-legend b{ margin-left:auto; color:var(--text); font-weight:600;}
  .streak-card{ display:flex; flex-direction:column; align-items:center; text-align:center; padding:24px 20px;}
  .flame{ width:56px; height:56px; margin-bottom:6px; filter:drop-shadow(0 0 16px rgba(255,140,0,0.5));}
  .streak-num{ font-family:var(--font-head); font-weight:800; font-size:32px; color:#fff;}
  .streak-num span{ font-size:15px; font-weight:600; color:var(--text-dim); margin-left:4px;}
  .streak-note{ font-size:12.5px; color:var(--text-faint); margin-top:10px;}

  /* ============ CONNECT ============ */
  .connect-row{ display:grid; grid-template-columns:repeat(4,1fr); gap:14px;}
  .connect-item{
    display:flex; align-items:center; gap:10px;
    padding:14px 16px; border-radius:12px;
    font-size:14px; font-weight:500; color:var(--text);
    text-decoration:none;
  }
  .connect-item .ic{
    width:30px; height:30px; border-radius:8px;
    display:flex; align-items:center; justify-content:center; flex-shrink:0;
  }
  .connect-item svg{ width:15px; height:15px; }

  footer{ text-align:center; padding:20px 0 8px; color:var(--accent-2); font-family:var(--font-head); font-weight:600; font-size:16px;}

  @media (max-width:820px){
    .hero{ grid-template-columns:1fr; padding:32px 26px;}
    .hero-visual{ order:-1; height:220px;}
    .stats-grid{ grid-template-columns:1fr;}
    .connect-row{ grid-template-columns:repeat(2,1fr);}
    .wrap{ padding:36px 18px;}
  }
</style>
</head>
<body>

<div class="bg-fixed">
  <div class="bg-grid"></div>
  <div class="bg-glow glow-1"></div>
  <div class="bg-glow glow-2"></div>
</div>

<div class="wrap">

  <!-- HERO -->
  <section class="card hero">
    <div class="hero-left">
      <div class="hero-name">Pulindu Godage</div>
      <div class="hero-role">Full Stack Developer</div>
      <p class="hero-bio">Building scalable web applications and mobile apps with modern technologies.</p>
      <div class="contact-list">
        <div class="contact-item">
          <span class="ic-wrap"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 21s-7-6.2-7-11.5A7 7 0 0 1 12 2.5a7 7 0 0 1 7 7C19 14.8 12 21 12 21z"/><circle cx="12" cy="9.5" r="2.4"/></svg></span>
          Sri Lanka
        </div>
        <div class="contact-item">
          <span class="ic-wrap"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2.5" y="4.5" width="19" height="15" rx="2.4"/><path d="M3 6l9 7 9-7"/></svg></span>
          pulindugodage@gmail.com
        </div>
        <div class="contact-item">
          <span class="ic-wrap"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 15l6-6M8 13l-1.5 1.5a3.5 3.5 0 0 0 5 5L13 18M16 11l1.5-1.5a3.5 3.5 0 0 0-5-5L11 6"/></svg></span>
          pulindugodage.me
        </div>
      </div>
    </div>

    <div class="hero-visual">
      <svg viewBox="0 0 420 300" style="width:100%;height:100%;">
        <defs>
          <radialGradient id="lampGlow" cx="50%" cy="50%" r="50%">
            <stop offset="0" stop-color="#FFD98A" stop-opacity="0.55"/>
            <stop offset="1" stop-color="#FFD98A" stop-opacity="0"/>
          </radialGradient>
          <linearGradient id="monGlow" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0" stop-color="#123047"/>
            <stop offset="1" stop-color="#0A1620"/>
          </linearGradient>
          <linearGradient id="charGrad" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0" stop-color="#232B36"/>
            <stop offset="1" stop-color="#11151B"/>
          </linearGradient>
        </defs>

        <!-- lamp glow -->
        <circle cx="70" cy="90" r="70" fill="url(#lampGlow)"/>
        <!-- desk -->
        <rect x="40" y="235" width="330" height="10" rx="3" fill="#1B2431"/>
        <rect x="55" y="245" width="10" height="34" fill="#141B24"/>
        <rect x="345" y="245" width="10" height="34" fill="#141B24"/>
        <!-- lamp -->
        <rect x="58" y="215" width="6" height="22" fill="#3A4552"/>
        <path d="M40 215 L88 215 L74 192 L54 192 Z" fill="#3A4552"/>
        <!-- mug -->
        <rect x="315" y="212" width="22" height="22" rx="4" fill="#2B95D6"/>
        <path d="M337 216 h8 a6 6 0 0 1 0 12 h-8" fill="none" stroke="#2B95D6" stroke-width="3"/>

        <!-- monitors -->
        <g>
          <rect x="130" y="120" width="150" height="98" rx="6" fill="url(#monGlow)" stroke="#2B3B4D" stroke-width="2"/>
          <g font-family="monospace" font-size="6.5" fill="#5CC8FF" opacity="0.9">
            <text x="140" y="135">function build() {</text>
            <text x="148" y="146" fill="#3B9EFF">return app.run();</text>
            <text x="140" y="157">}</text>
            <text x="140" y="172" fill="#39D6FF">const stack = [</text>
            <text x="148" y="183" fill="#8FC1FF">'Spring','React'</text>
            <text x="140" y="194">];</text>
          </g>
          <rect x="196" y="218" width="18" height="10" fill="#1B2431"/>
        </g>
        <g transform="translate(70 138) rotate(-9)">
          <rect width="95" height="66" rx="5" fill="url(#monGlow)" stroke="#2B3B4D" stroke-width="2"/>
          <g font-family="monospace" font-size="5.6" fill="#5CC8FF" opacity="0.85">
            <text x="8" y="16">git push origin</text>
            <text x="8" y="27">✓ build passed</text>
            <text x="8" y="42">SELECT * FROM</text>
            <text x="8" y="52">users;</text>
          </g>
        </g>

        <!-- laptop -->
        <g transform="translate(255 238)">
          <path d="M0 0 h72 l10 16 h-92 z" fill="#1B2431"/>
          <rect x="6" y="-38" width="58" height="38" rx="3" fill="#141B24" stroke="#2B3B4D" stroke-width="1.5"/>
          <rect x="10" y="-34" width="50" height="30" fill="#0A1620"/>
          <g font-family="monospace" font-size="4.6" fill="#3B9EFF" opacity="0.8">
            <text x="13" y="-24">npm run dev</text>
            <text x="13" y="-16">✓ ready in 480ms</text>
          </g>
        </g>

        <!-- character (back view) -->
        <g transform="translate(150 130)">
          <path d="M10 108 C10 66 34 46 68 46 C102 46 126 66 126 108 L126 128 L10 128 Z" fill="url(#charGrad)"/>
          <circle cx="68" cy="30" r="26" fill="url(#charGrad)"/>
          <path d="M42 20 C42 2 94 2 94 20 C94 8 84 -2 68 -2 C52 -2 42 8 42 20 Z" fill="#0C1016"/>
          <rect x="46" y="70" width="44" height="8" rx="4" fill="#3B9EFF" opacity="0.5"/>
        </g>
        <rect x="196" y="222" width="4" height="4" fill="#0000"/>
      </svg>

      <!-- hex badges -->
      <svg class="hex-badge hx1" viewBox="0 0 100 100"><polygon points="50,3 93,26 93,74 50,97 7,74 7,26" fill="#0D1319" stroke="#3B9EFF" stroke-width="4"/><g fill="#5CC8FF" font-family="monospace" font-size="26" font-weight="700"><text x="50" y="58" text-anchor="middle">&lt;/&gt;</text></g></svg>
      <svg class="hex-badge hx2" viewBox="0 0 100 100"><polygon points="50,3 93,26 93,74 50,97 7,74 7,26" fill="#0D1319" stroke="#3B9EFF" stroke-width="4"/><path d="M35 55 q0 16 15 16 q15 0 15-11 q0-9-11-13 q-8-3-8-9 q0-5 6-5" fill="none" stroke="#E76F00" stroke-width="5" stroke-linecap="round"/><ellipse cx="50" cy="34" rx="10" ry="4" fill="none" stroke="#E76F00" stroke-width="3"/></svg>
      <svg class="hex-badge hx3" viewBox="0 0 100 100"><polygon points="50,3 93,26 93,74 50,97 7,74 7,26" fill="#0D1319" stroke="#3B9EFF" stroke-width="4"/><text x="50" y="60" text-anchor="middle" font-family="Poppins, sans-serif" font-weight="800" font-size="26" fill="#F7DF1E">JS</text></svg>
      <svg class="hex-badge hx4" viewBox="0 0 100 100"><polygon points="50,3 93,26 93,74 50,97 7,74 7,26" fill="#0D1319" stroke="#3B9EFF" stroke-width="4"/><g fill="none" stroke="#61DAFB" stroke-width="3"><ellipse cx="50" cy="50" rx="24" ry="9"/><ellipse cx="50" cy="50" rx="24" ry="9" transform="rotate(60 50 50)"/><ellipse cx="50" cy="50" rx="24" ry="9" transform="rotate(120 50 50)"/></g><circle cx="50" cy="50" r="5" fill="#61DAFB"/></svg>
      <svg class="hex-badge hx5" viewBox="0 0 100 100"><polygon points="50,3 93,26 93,74 50,97 7,74 7,26" fill="#0D1319" stroke="#3B9EFF" stroke-width="4"/><path d="M50 20 C40 40 30 50 30 62 a20 20 0 0 0 40 0 C70 50 60 40 50 20Z" fill="#47A248"/></svg>
      <svg class="hex-badge hx6" viewBox="0 0 100 100"><polygon points="50,3 93,26 93,74 50,97 7,74 7,26" fill="#0D1319" stroke="#3B9EFF" stroke-width="4"/><ellipse cx="50" cy="52" rx="26" ry="16" fill="none" stroke="#4479A1" stroke-width="4"/><path d="M50 36 v32" stroke="#4479A1" stroke-width="4"/></svg>
    </div>
  </section>

  <!-- INTRO -->
  <section class="intro">
    <h2>Hi 👋, I'm Pulindu Godage</h2>
    <p>Full Stack Software Developer from Sri Lanka 🇱🇰</p>
    <div class="views-pill">
      <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M2 12s4-7 10-7 10 7 10 7-4 7-10 7-10-7-10-7z"/><circle cx="12" cy="12" r="3"/></svg>Profile Views</span>
      <span>1.2K+</span>
    </div>
  </section>

  <!-- ABOUT -->
  <section class="card" style="padding:26px 30px;">
    <div class="head-row">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="8" r="4"/><path d="M4 21c0-4.4 3.6-7 8-7s8 2.6 8 7"/></svg>
      <h3>About Me</h3>
    </div>
    <ul class="about-list">
      <li><span class="em">🎓</span>Undergraduate Software Engineering Student</li>
      <li><span class="em">💻</span>Passionate about Full Stack Development</li>
      <li><span class="em">🌱</span>Currently learning Spring Boot, React, Next.js &amp; React Native</li>
      <li><span class="em">🔥</span>Interested in Web Development, Mobile Applications and Backend Development</li>
      <li><span class="em">⚡</span>Always learning new technologies and building practical solutions</li>
    </ul>
  </section>

  <!-- TECH STACK -->
  <section class="card" style="padding:26px 30px;">
    <div class="head-row">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2 2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
      <h3>Tech Stack</h3>
    </div>

    <div class="stack-row">
      <div class="cat-label">Languages</div>
      <div class="stack-icons">
        <div class="tech-item"><div class="box" style="background:#2C2416;"><svg viewBox="0 0 24 24" fill="none" stroke="#E76F00" stroke-width="2"><path d="M8 13c0 3 2 5 5 5s5-2 5-5-3-3-3-6" stroke-linecap="round"/><ellipse cx="13" cy="7" rx="4" ry="1.6" fill="none"/></svg></div><div class="lbl">Java</div></div>
        <div class="tech-item"><div class="box" style="background:#F7DF1E;"><span style="font-family:'Poppins';font-weight:800;font-size:16px;color:#111;">JS</span></div><div class="lbl">JavaScript</div></div>
        <div class="tech-item"><div class="box" style="background:#3178C6;"><span style="font-family:'Poppins';font-weight:800;font-size:15px;color:#fff;">TS</span></div><div class="lbl">TypeScript</div></div>
        <div class="tech-item"><div class="box" style="background:#E44D26;"><span style="font-family:'Poppins';font-weight:800;font-size:16px;color:#fff;">5</span></div><div class="lbl">HTML</div></div>
        <div class="tech-item"><div class="box" style="background:#264DE4;"><span style="font-family:'Poppins';font-weight:800;font-size:16px;color:#fff;">3</span></div><div class="lbl">CSS</div></div>
      </div>
    </div>

    <div class="stack-row">
      <div class="cat-label">Frontend</div>
      <div class="stack-icons">
        <div class="tech-item"><div class="box" style="background:#0D1319;"><svg viewBox="0 0 24 24" fill="none" stroke="#61DAFB" stroke-width="1.6"><ellipse cx="12" cy="12" rx="10" ry="4"/><ellipse cx="12" cy="12" rx="10" ry="4" transform="rotate(60 12 12)"/><ellipse cx="12" cy="12" rx="10" ry="4" transform="rotate(120 12 12)"/><circle cx="12" cy="12" r="1.8" fill="#61DAFB"/></svg></div><div class="lbl">React</div></div>
        <div class="tech-item"><div class="box" style="background:#000;border:1px solid #333;"><span style="font-family:'Poppins';font-weight:800;font-size:17px;color:#fff;">N</span></div><div class="lbl">Next.js</div></div>
        <div class="tech-item"><div class="box" style="background:#0D1319;"><svg viewBox="0 0 24 24" fill="none" stroke="#38BDF8" stroke-width="2"><path d="M6 12c1-4 3-5 6-5s4 2 6 5c-1-1-3-1-4 0-2 2-4 3-8 0z"/><path d="M2 16c1-4 3-5 6-5s4 2 6 5c-1-1-3-1-4 0-2 2-4 3-8 0z"/></svg></div><div class="lbl">Tailwind</div></div>
        <div class="tech-item"><div class="box" style="background:#7952B3;"><span style="font-family:'Poppins';font-weight:800;font-size:16px;color:#fff;">B</span></div><div class="lbl">Bootstrap</div></div>
      </div>
    </div>

    <div class="stack-row">
      <div class="cat-label">Backend</div>
      <div class="stack-icons">
        <div class="tech-item"><div class="box" style="background:#123018;"><svg viewBox="0 0 24 24" fill="#6DB33F"><path d="M12 3c-3 5-6 6-6 11a6 6 0 0 0 12 0c0-5-3-6-6-11z"/></svg></div><div class="lbl">Spring Boot</div></div>
        <div class="tech-item"><div class="box" style="background:#0D1319;"><svg viewBox="0 0 24 24" fill="#68A063"><path d="M12 2l9 5v10l-9 5-9-5V7z" opacity="0.9"/></svg></div><div class="lbl">Node.js</div></div>
        <div class="tech-item"><div class="box" style="background:#111;border:1px solid #333;"><span style="font-family:'Poppins';font-weight:700;font-size:12px;color:#fff;">exp</span></div><div class="lbl">Express</div></div>
      </div>
    </div>

    <div class="stack-row">
      <div class="cat-label">Database</div>
      <div class="stack-icons">
        <div class="tech-item"><div class="box" style="background:#0D1319;"><svg viewBox="0 0 24 24" fill="none" stroke="#4479A1" stroke-width="2"><ellipse cx="12" cy="7" rx="8" ry="3.2"/><path d="M4 7v10a8 3.2 0 0 0 16 0V7"/></svg></div><div class="lbl">MySQL</div></div>
        <div class="tech-item"><div class="box" style="background:#0D1319;"><svg viewBox="0 0 24 24" fill="#47A248"><path d="M12 2c-3 5-6 6-6 11a6 6 0 0 0 12 0c0-5-3-6-6-11z"/></svg></div><div class="lbl">MongoDB</div></div>
        <div class="tech-item"><div class="box" style="background:#FFCB2B;"><svg viewBox="0 0 24 24" fill="#111"><path d="M12 2l7 12h-5l4 8-11-13h5z"/></svg></div><div class="lbl">Firebase</div></div>
      </div>
    </div>

    <div class="stack-row">
      <div class="cat-label">Tools</div>
      <div class="stack-icons">
        <div class="tech-item"><div class="box" style="background:#F05032;"><svg viewBox="0 0 24 24" fill="#fff"><circle cx="12" cy="12" r="2.4"/><circle cx="12" cy="5" r="1.8"/><circle cx="12" cy="19" r="1.8"/><path d="M12 7v3M12 14v3" stroke="#fff" stroke-width="1.6"/></svg></div><div class="lbl">Git</div></div>
        <div class="tech-item"><div class="box" style="background:#111;border:1px solid #333;"><svg viewBox="0 0 24 24" fill="#fff"><path d="M12 2C6.48 2 2 6.58 2 12.25c0 4.53 2.87 8.37 6.84 9.73.5.1.68-.22.68-.49 0-.24-.01-1.03-.01-1.87-2.78.62-3.37-1.22-3.37-1.22-.46-1.19-1.11-1.51-1.11-1.51-.91-.64.07-.63.07-.63 1 .07 1.53 1.05 1.53 1.05.89 1.57 2.34 1.12 2.91.85.09-.66.35-1.12.63-1.38-2.22-.26-4.56-1.14-4.56-5.05 0-1.12.39-2.03 1.03-2.74-.1-.26-.45-1.31.1-2.73 0 0 .84-.28 2.75 1.05a9.3 9.3 0 0 1 5 0c1.91-1.33 2.75-1.05 2.75-1.05.55 1.42.2 2.47.1 2.73.64.71 1.03 1.62 1.03 2.74 0 3.92-2.34 4.79-4.57 5.04.36.32.68.95.68 1.92 0 1.39-.01 2.51-.01 2.85 0 .27.18.6.69.49A10.26 10.26 0 0 0 22 12.25C22 6.58 17.52 2 12 2z"/></svg></div><div class="lbl">GitHub</div></div>
        <div class="tech-item"><div class="box" style="background:#0D1319;"><svg viewBox="0 0 24 24" fill="none" stroke="#3B9EFF" stroke-width="2"><path d="M9 6l-6 6 6 6M15 6l6 6-6 6"/></svg></div><div class="lbl">VS Code</div></div>
        <div class="tech-item"><div class="box" style="background:#111;border:1px solid #333;"><span style="font-family:'Poppins';font-weight:800;font-size:13px;color:#FE315D;">IJ</span></div><div class="lbl">IntelliJ</div></div>
        <div class="tech-item"><div class="box" style="background:#FF6C37;"><svg viewBox="0 0 24 24" fill="#fff"><path d="M3 12l18-8-8 18-2-8z"/></svg></div><div class="lbl">Postman</div></div>
        <div class="tech-item"><div class="box" style="background:#0D1319;"><svg viewBox="0 0 24 24"><circle cx="9" cy="5" r="3" fill="#F24E1E"/><circle cx="9" cy="12" r="3" fill="#A259FF"/><circle cx="9" cy="19" r="3" fill="#0ACF83"/><circle cx="15" cy="8.5" r="3" fill="#FF7262"/><circle cx="15" cy="15.5" r="3" fill="#1ABCFE"/></svg></div><div class="lbl">Figma</div></div>
        <div class="tech-item"><div class="box" style="background:#2496ED;"><svg viewBox="0 0 24 24" fill="#fff"><rect x="4" y="10" width="3" height="3"/><rect x="8" y="10" width="3" height="3"/><rect x="12" y="10" width="3" height="3"/><rect x="8" y="6" width="3" height="3"/><path d="M2 13c1 6 5 7 10 7 6 0 9-3 10-8-2 1-16 1-20 1z"/></svg></div><div class="lbl">Docker</div></div>
      </div>
    </div>
  </section>

  <!-- STATS -->
  <section>
    <div class="head-row" style="border-bottom:none; margin-bottom:16px;">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 20V10M12 20V4M20 20v-7"/></svg>
      <h3>GitHub Stats</h3>
    </div>
    <div class="stats-grid">
      <div class="card stat-card split">
        <div class="stat-list">
          <h4>Pulindu's GitHub Stats</h4>
          <div class="stat-line"><span class="l"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="4" y="4" width="14" height="16" rx="2"/></svg>Total Repositories</span><span class="v">50+</span></div>
          <div class="stat-line"><span class="l"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2l3 6.5 7 .8-5.2 4.9 1.4 6.9L12 17.8 5.8 21.1l1.4-6.9L2 9.3l7-.8z"/></svg>Total Stars</span><span class="v">150+</span></div>
          <div class="stat-line"><span class="l"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="9"/><path d="M12 7v5l3 3"/></svg>Total Commits</span><span class="v">1.2K+</span></div>
          <div class="stat-line"><span class="l"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 3v18M18 9a3 3 0 1 0 0-6 3 3 0 0 0 0 6zM6 9a3 3 0 1 0 0-6 3 3 0 0 0 0 6zM18 9c0 6-6 6-12 6"/></svg>Total PRs</span><span class="v">30+</span></div>
          <div class="stat-line"><span class="l"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 3v18h18M7 15l4-6 4 3 5-8"/></svg>Contributions 2026</span><span class="v">350+</span></div>
        </div>
        <div class="grade">A+</div>
      </div>

      <div class="card stat-card">
        <h4>Most Used Languages</h4>
        <div class="donut-row">
          <div class="donut"></div>
          <div class="lang-legend">
            <div class="row"><span class="sw" style="background:#F7DF1E;"></span>Java<b>38.7%</b></div>
            <div class="row"><span class="sw" style="background:#3178C6;"></span>JavaScript<b>24.1%</b></div>
            <div class="row"><span class="sw" style="background:#E76F00;"></span>TypeScript<b>15.4%</b></div>
            <div class="row"><span class="sw" style="background:#61DAFB;"></span>HTML<b>10.6%</b></div>
            <div class="row"><span class="sw" style="background:#6A737D;"></span>CSS<b>6.2%</b></div>
          </div>
        </div>
      </div>

      <div class="card streak-card">
        <h4 style="align-self:flex-start;">GitHub Streak</h4>
        <svg class="flame" viewBox="0 0 24 24" fill="none">
          <path d="M12 2s6.5 6.2 6.5 12.4A6.5 6.5 0 0 1 5.5 14.4c0-3.2 2.1-4.3 2.1-7.4 1.1 1.1 2.1 2.1 2.1 4.3C11 9.6 12 6.9 12 2z" fill="url(#fg)"/>
          <defs><linearGradient id="fg" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#FFC24B"/><stop offset="1" stop-color="#FF7A00"/></linearGradient></defs>
        </svg>
        <div class="streak-num">47<span>days</span></div>
        <div class="streak-note">Keep coding, keep growing!</div>
      </div>
    </div>
  </section>

  <!-- CONNECT -->
  <section class="card" style="padding:26px 30px;">
    <div class="head-row">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="9"/><path d="M3 12h18M12 3c2.5 2.4 4 5.4 4 9s-1.5 6.6-4 9c-2.5-2.4-4-5.4-4-9s1.5-6.6 4-9z"/></svg>
      <h3>Connect With Me</h3>
    </div>
    <div class="connect-row">
      <a href="#" class="card connect-item">
        <span class="ic" style="background:#0A66C2;"><svg viewBox="0 0 24 24" fill="#fff"><path d="M6.94 5a2 2 0 1 1-4 0 2 2 0 0 1 4 0zM3.5 8.5h3.9V21H3.5zM9.5 8.5h3.7v1.7h.05c.52-.94 1.78-1.93 3.66-1.93 3.9 0 4.62 2.5 4.62 5.75V21h-3.9v-6.13c0-1.46-.03-3.33-2.03-3.33-2.04 0-2.35 1.58-2.35 3.22V21H9.5z"/></svg></span>
        LinkedIn
      </a>
      <a href="#" class="card connect-item">
        <span class="ic" style="background:#EA4335;"><svg viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2"><rect x="2.5" y="4.5" width="19" height="15" rx="2.4"/><path d="M3 6l9 7 9-7"/></svg></span>
        Email
      </a>
      <a href="#" class="card connect-item">
        <span class="ic" style="background:#3B9EFF;"><svg viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2"><circle cx="12" cy="12" r="9"/><path d="M3.5 12h17M12 3.5c2.5 2.4 3.8 5.4 3.8 8.5s-1.3 6.1-3.8 8.5c-2.5-2.4-3.8-5.4-3.8-8.5S9.5 5.9 12 3.5z"/></svg></span>
        Portfolio
      </a>
      <a href="#" class="card connect-item">
        <span class="ic" style="background:#111;border:1px solid #333;"><svg viewBox="0 0 24 24" fill="#fff"><path d="M12 2C6.48 2 2 6.58 2 12.25c0 4.53 2.87 8.37 6.84 9.73.5.1.68-.22.68-.49 0-.24-.01-1.03-.01-1.87-2.78.62-3.37-1.22-3.37-1.22-.46-1.19-1.11-1.51-1.11-1.51-.91-.64.07-.63.07-.63 1 .07 1.53 1.05 1.53 1.05.89 1.57 2.34 1.12 2.91.85.09-.66.35-1.12.63-1.38-2.22-.26-4.56-1.14-4.56-5.05 0-1.12.39-2.03 1.03-2.74-.1-.26-.45-1.31.1-2.73 0 0 .84-.28 2.75 1.05a9.3 9.3 0 0 1 5 0c1.91-1.33 2.75-1.05 2.75-1.05.55 1.42.2 2.47.1 2.73.64.71 1.03 1.62 1.03 2.74 0 3.92-2.34 4.79-4.57 5.04.36.32.68.95.68 1.92 0 1.39-.01 2.51-.01 2.85 0 .27.18.6.69.49A10.26 10.26 0 0 0 22 12.25C22 6.58 17.52 2 12 2z"/></svg></span>
        GitHub
      </a>
    </div>
  </section>

  <footer>“ Code. Learn. Improve. Repeat. 🚀 ”</footer>

</div>
</body>
</html>
