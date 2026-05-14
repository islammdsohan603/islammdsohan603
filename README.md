<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sohan Islam – GitHub Profile Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050a0f;
    --surface: #0d1117;
    --card: #111820;
    --border: #1e2d3d;
    --accent: #00e5ff;
    --accent2: #7c3aed;
    --accent3: #f59e0b;
    --text: #e2e8f0;
    --muted: #64748b;
    --green: #22c55e;
    --mono: 'Space Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--mono);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── Grid noise background ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 20px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── Glow orbs ── */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(120px);
    opacity: .18;
    pointer-events: none;
    z-index: 0;
    animation: drift 12s ease-in-out infinite alternate;
  }
  .orb1 { width: 500px; height: 500px; background: var(--accent); top: -200px; right: -100px; }
  .orb2 { width: 400px; height: 400px; background: var(--accent2); bottom: -100px; left: -100px; animation-delay: -6s; }
  @keyframes drift { from { transform: translate(0,0); } to { transform: translate(40px, 30px); } }

  /* ── Hero ── */
  .hero {
    border: 1px solid var(--border);
    border-radius: 16px;
    background: linear-gradient(135deg, rgba(0,229,255,.05), rgba(124,58,237,.05));
    padding: 48px 40px;
    margin-bottom: 28px;
    position: relative;
    overflow: hidden;
    animation: fadeUp .8s ease both;
  }
  .hero::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent), var(--accent2), transparent);
    animation: shimmer 3s linear infinite;
  }
  @keyframes shimmer { from { transform: translateX(-100%); } to { transform: translateX(100%); } }

  .badge-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 20px;
    animation: fadeUp .8s .1s ease both;
  }
  .badge {
    font-family: var(--mono);
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 999px;
    border: 1px solid;
    letter-spacing: .05em;
    text-transform: uppercase;
  }
  .badge-cyan { border-color: var(--accent); color: var(--accent); background: rgba(0,229,255,.08); }
  .badge-purple { border-color: var(--accent2); color: #a78bfa; background: rgba(124,58,237,.08); }
  .badge-amber { border-color: var(--accent3); color: var(--accent3); background: rgba(245,158,11,.08); }

  .hero-name {
    font-family: var(--sans);
    font-size: clamp(2rem, 6vw, 3.6rem);
    font-weight: 800;
    line-height: 1.1;
    background: linear-gradient(135deg, #fff 30%, var(--accent));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: fadeUp .8s .15s ease both;
  }

  .hero-tagline {
    margin-top: 12px;
    font-size: 15px;
    color: var(--muted);
    animation: fadeUp .8s .2s ease both;
  }
  .hero-tagline span { color: var(--accent); }

  .typing-wrap {
    margin-top: 20px;
    font-size: 14px;
    color: var(--accent);
    letter-spacing: .02em;
    min-height: 22px;
    animation: fadeUp .8s .25s ease both;
  }
  .cursor { display: inline-block; animation: blink .8s step-end infinite; }
  @keyframes blink { 50% { opacity: 0; } }

  /* ── Section title ── */
  .section-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    letter-spacing: .15em;
    text-transform: uppercase;
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-label::before {
    content: '//';
    color: var(--accent);
  }

  /* ── Cards grid ── */
  .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 28px; }
  @media(max-width: 600px) { .grid-2 { grid-template-columns: 1fr; } }

  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    transition: border-color .3s, transform .3s;
    animation: fadeUp .8s ease both;
  }
  .card:hover {
    border-color: var(--accent);
    transform: translateY(-4px);
  }
  .card-icon { font-size: 22px; margin-bottom: 10px; }
  .card-title { font-family: var(--sans); font-size: 15px; font-weight: 700; margin-bottom: 6px; }
  .card-desc { font-size: 12px; color: var(--muted); line-height: 1.7; }

  /* ── About list ── */
  .about-list { list-style: none; display: flex; flex-direction: column; gap: 10px; }
  .about-list li {
    font-size: 13px;
    color: var(--text);
    display: flex;
    align-items: flex-start;
    gap: 10px;
    line-height: 1.5;
  }
  .about-list li .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    margin-top: 6px;
    flex-shrink: 0;
  }

  /* ── Tech Stack ── */
  .stack-section { margin-bottom: 28px; animation: fadeUp .8s .3s ease both; }
  .stack-group { margin-bottom: 18px; }
  .stack-group-label {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: .1em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .pill-row { display: flex; flex-wrap: wrap; gap: 8px; }
  .pill {
    font-family: var(--mono);
    font-size: 12px;
    padding: 6px 14px;
    border-radius: 6px;
    border: 1px solid var(--border);
    background: rgba(255,255,255,.03);
    color: var(--text);
    transition: all .25s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }
  .pill::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    opacity: 0;
    transition: opacity .25s;
  }
  .pill span { position: relative; z-index: 1; }
  .pill:hover { border-color: var(--accent); color: var(--bg); transform: scale(1.05); }
  .pill:hover::before { opacity: 1; }

  /* ── Stats bar ── */
  .stats-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin-bottom: 28px; }
  @media(max-width: 500px) { .stats-row { grid-template-columns: 1fr 1fr; } }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    transition: border-color .3s, transform .3s;
    animation: fadeUp .8s ease both;
  }
  .stat-card:hover { border-color: var(--accent2); transform: translateY(-4px); }
  .stat-num {
    font-family: var(--sans);
    font-size: 2rem;
    font-weight: 800;
    color: var(--accent);
    display: block;
  }
  .stat-label { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: .08em; margin-top: 4px; }

  /* ── Contact ── */
  .contact-row { display: flex; flex-wrap: wrap; gap: 12px; margin-bottom: 28px; animation: fadeUp .8s .4s ease both; }
  .contact-btn {
    font-family: var(--mono);
    font-size: 12px;
    padding: 10px 20px;
    border-radius: 8px;
    border: 1px solid var(--border);
    background: var(--card);
    color: var(--text);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 8px;
    transition: all .25s;
  }
  .contact-btn:hover { border-color: var(--accent); color: var(--accent); background: rgba(0,229,255,.06); transform: translateY(-2px); }
  .contact-btn .icon { font-size: 15px; }

  /* ── Footer ── */
  .footer {
    text-align: center;
    font-size: 12px;
    color: var(--muted);
    padding-top: 20px;
    border-top: 1px solid var(--border);
    animation: fadeUp .8s .5s ease both;
  }
  .footer span { color: var(--accent); }

  /* ── Progress bar (skill) ── */
  .skill-bar-wrap { margin-bottom: 28px; animation: fadeUp .8s .35s ease both; }
  .skill-bar-item { margin-bottom: 14px; }
  .skill-bar-header { display: flex; justify-content: space-between; font-size: 12px; color: var(--muted); margin-bottom: 6px; }
  .skill-bar-header strong { color: var(--text); font-weight: 400; }
  .bar-track {
    height: 6px;
    background: var(--border);
    border-radius: 99px;
    overflow: hidden;
  }
  .bar-fill {
    height: 100%;
    border-radius: 99px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform-origin: left;
    animation: growBar 1.2s cubic-bezier(.22,1,.36,1) both;
  }
  @keyframes growBar { from { transform: scaleX(0); } to { transform: scaleX(1); } }
  .bar-fill:nth-child(1) { animation-delay: .1s; }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* Divider */
  .divider { height: 1px; background: var(--border); margin: 8px 0 28px; }

  /* inline code style */
  code { font-family: var(--mono); font-size: 12px; color: var(--accent); background: rgba(0,229,255,.08); padding: 2px 6px; border-radius: 4px; }

  /* section wrapper delay */
  .s1 { animation-delay: .05s; }
  .s2 { animation-delay: .1s; }
  .s3 { animation-delay: .15s; }
  .s4 { animation-delay: .2s; }
  .s5 { animation-delay: .25s; }
</style>
</head>
<body>

<div class="orb orb1"></div>
<div class="orb orb2"></div>

<div class="container">

  <!-- ── Hero ── -->
  <div class="hero">
    <div class="badge-row">
      <span class="badge badge-cyan">🟢 Open to Work</span>
      <span class="badge badge-purple">Frontend Dev</span>
      <span class="badge badge-amber">📍 Bangladesh</span>
    </div>
    <div class="hero-name">Sohan Islam</div>
    <div class="hero-tagline">
      Building <span>high-performance</span> web experiences with React & Next.js
    </div>
    <div class="typing-wrap" id="typer">&nbsp;<span class="cursor">▍</span></div>
  </div>

  <!-- ── About ── -->
  <div class="section-label">About Me</div>
  <div class="grid-2 s1">
    <div class="card">
      <div class="card-icon">👨‍💻</div>
      <div class="card-title">Frontend Developer</div>
      <div class="card-desc">Crafting clean, accessible, and blazing-fast UIs with React, Next.js and Tailwind CSS.</div>
    </div>
    <div class="card">
      <div class="card-icon">🎓</div>
      <div class="card-title">Education</div>
      <div class="card-desc">Computer Technology student at <strong>Polytechnic Institute</strong>. Completed full-stack course at <strong>Programming Hero</strong>.</div>
    </div>
    <div class="card">
      <div class="card-icon">⚡</div>
      <div class="card-title">Currently Learning</div>
      <div class="card-desc">Advanced full-stack patterns — server actions, authentication (Better Auth), and system design.</div>
    </div>
    <div class="card">
      <div class="card-icon">🧠</div>
      <div class="card-title">What Drives Me</div>
      <div class="card-desc">Real-world projects with real impact. Clean code, great UX, measurable performance gains.</div>
    </div>
  </div>

  <!-- ── GitHub Stats Numbers ── -->
  <div class="section-label s2">GitHub Snapshot</div>
  <div class="stats-row s2">
    <div class="stat-card">
      <span class="stat-num" id="c-repos">0</span>
      <div class="stat-label">Public Repos</div>
    </div>
    <div class="stat-card">
      <span class="stat-num" id="c-commits">0+</span>
      <div class="stat-label">Commits (2024)</div>
    </div>
    <div class="stat-card">
      <span class="stat-num" id="c-streak">0</span>
      <div class="stat-label">Day Streak</div>
    </div>
  </div>

  <!-- ── Skill bars ── -->
  <div class="section-label s3">Proficiency</div>
  <div class="skill-bar-wrap s3">
    <div class="skill-bar-item">
      <div class="skill-bar-header"><strong>React & Next.js</strong><span>90%</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:90%"></div></div>
    </div>
    <div class="skill-bar-item">
      <div class="skill-bar-header"><strong>Tailwind CSS / UI Design</strong><span>88%</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:88%"></div></div>
    </div>
    <div class="skill-bar-item">
      <div class="skill-bar-header"><strong>JavaScript (ES2024)</strong><span>82%</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:82%"></div></div>
    </div>
    <div class="skill-bar-item">
      <div class="skill-bar-header"><strong>Node.js / Express / MongoDB</strong><span>72%</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:72%"></div></div>
    </div>
    <div class="skill-bar-item">
      <div class="skill-bar-header"><strong>Firebase / Better Auth</strong><span>70%</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:70%"></div></div>
    </div>
  </div>

  <!-- ── Tech Stack ── -->
  <div class="section-label s4">Tech Stack</div>
  <div class="stack-section s4">
    <div class="stack-group">
      <div class="stack-group-label">// Frontend</div>
      <div class="pill-row">
        <div class="pill"><span>HTML5</span></div>
        <div class="pill"><span>CSS3</span></div>
        <div class="pill"><span>JavaScript</span></div>
        <div class="pill"><span>TypeScript</span></div>
        <div class="pill"><span>React</span></div>
        <div class="pill"><span>Next.js</span></div>
        <div class="pill"><span>Tailwind CSS</span></div>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">// Backend &amp; Database</div>
      <div class="pill-row">
        <div class="pill"><span>Node.js</span></div>
        <div class="pill"><span>Express.js</span></div>
        <div class="pill"><span>MongoDB</span></div>
        <div class="pill"><span>Firebase</span></div>
        <div class="pill"><span>Better Auth</span></div>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">// Tools &amp; Deployment</div>
      <div class="pill-row">
        <div class="pill"><span>Git</span></div>
        <div class="pill"><span>GitHub</span></div>
        <div class="pill"><span>Vercel</span></div>
        <div class="pill"><span>Netlify</span></div>
        <div class="pill"><span>VS Code</span></div>
      </div>
    </div>
  </div>

  <!-- ── Contact ── -->
  <div class="section-label s5">Connect</div>
  <div class="contact-row">
    <a class="contact-btn" href="https://www.linkedin.com/in/sohanislamwebdev/" target="_blank">
      <span class="icon">💼</span> LinkedIn
    </a>
    <a class="contact-btn" href="mailto:islammdsohan603@gmail.com">
      <span class="icon">📧</span> islammdsohan603@gmail.com
    </a>
    <a class="contact-btn" href="https://github.com/islammdsohan603" target="_blank">
      <span class="icon">🐙</span> GitHub
    </a>
  </div>

  <div class="footer">
    <p>Built with <span>❤️</span> in Bangladesh · <span>Open to remote & freelance opportunities</span></p>
  </div>

</div>

<script>
  // ── Typing animation ──
  const lines = [
    "const dev = 'Sohan Islam';",
    "// React • Next.js • Tailwind",
    "let status = 'open_to_work';",
    "// Building the web, one commit at a time",
    "export default () => <GreatCode />;",
  ];
  let li = 0, ci = 0, deleting = false;
  const el = document.getElementById('typer');
  function type() {
    const line = lines[li];
    if (!deleting) {
      ci++;
      el.innerHTML = line.slice(0, ci) + '<span class="cursor">▍</span>';
      if (ci === line.length) { deleting = true; setTimeout(type, 1800); return; }
      setTimeout(type, 55);
    } else {
      ci--;
      el.innerHTML = line.slice(0, ci) + '<span class="cursor">▍</span>';
      if (ci === 0) { deleting = false; li = (li + 1) % lines.length; setTimeout(type, 400); return; }
      setTimeout(type, 28);
    }
  }
  type();

  // ── Counter animation ──
  function animateCount(el, target, duration = 1200) {
    const start = performance.now();
    function frame(now) {
      const p = Math.min((now - start) / duration, 1);
      const ease = 1 - Math.pow(1 - p, 3);
      el.textContent = Math.round(ease * target);
      if (p < 1) requestAnimationFrame(frame);
    }
    requestAnimationFrame(frame);
  }
  setTimeout(() => {
    animateCount(document.getElementById('c-repos'), 24);
    animateCount(document.getElementById('c-commits'), 300, 1500);
    animateCount(document.getElementById('c-streak'), 45);
  }, 600);
</script>
</body>
</html>
