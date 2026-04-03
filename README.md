<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nikhil Suryawanshi – GitHub Profile Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&family=Cabinet+Grotesk:wght@400;500;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080c14;
    --surface: #0e1520;
    --card: #111927;
    --border: #1e2d42;
    --accent: #00d4ff;
    --accent2: #7c3aed;
    --accent3: #f59e0b;
    --text: #e2eaf5;
    --muted: #6b87a8;
    --green: #10b981;
    --red: #ef4444;
    --glow: 0 0 30px rgba(0,212,255,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.4;
  }

  /* ── GRID LINES ── */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  .page-wrapper {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px 80px;
  }

  /* ── SLIDE-IN ANIMATION ── */
  @keyframes slideInLeft {
    from { opacity: 0; transform: translateX(-60px); }
    to   { opacity: 1; transform: translateX(0); }
  }
  @keyframes slideInRight {
    from { opacity: 0; transform: translateX(60px); }
    to   { opacity: 1; transform: translateX(0); }
  }
  @keyframes slideInUp {
    from { opacity: 0; transform: translateY(50px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }
  @keyframes scanline {
    from { transform: translateY(-100%); }
    to   { transform: translateY(100vh); }
  }
  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-8px); }
  }
  @keyframes borderRotate {
    from { background-position: 0% 50%; }
    to   { background-position: 100% 50%; }
  }
  @keyframes typewriter {
    from { width: 0; }
    to   { width: 100%; }
  }
  @keyframes blink {
    0%, 100% { border-color: var(--accent); }
    50% { border-color: transparent; }
  }
  @keyframes countUp {
    from { opacity: 0; transform: translateY(20px) scale(0.8); }
    to   { opacity: 1; transform: translateY(0) scale(1); }
  }
  @keyframes shimmer {
    0% { background-position: -200% center; }
    100% { background-position: 200% center; }
  }

  .slide-left  { animation: slideInLeft  0.7s cubic-bezier(.22,1,.36,1) both; }
  .slide-right { animation: slideInRight 0.7s cubic-bezier(.22,1,.36,1) both; }
  .slide-up    { animation: slideInUp    0.7s cubic-bezier(.22,1,.36,1) both; }
  .fade-in     { animation: fadeIn       0.8s ease both; }

  /* ── SCANLINE EFFECT ── */
  .scanline {
    position: fixed;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(transparent, rgba(0,212,255,0.08), transparent);
    animation: scanline 8s linear infinite;
    pointer-events: none;
    z-index: 999;
  }

  /* ── HEADER ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 32px;
    align-items: center;
    padding: 48px 40px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    position: relative;
    overflow: hidden;
    margin-bottom: 24px;
  }

  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,212,255,0.05) 0%, transparent 50%, rgba(124,58,237,0.05) 100%);
  }

  .hero-corner {
    position: absolute;
    top: 20px; right: 20px;
    width: 80px; height: 80px;
    border-top: 2px solid var(--accent);
    border-right: 2px solid var(--accent);
    opacity: 0.3;
    border-radius: 0 8px 0 0;
  }
  .hero-corner-bl {
    top: auto; right: auto;
    bottom: 20px; left: 20px;
    border-top: none; border-right: none;
    border-bottom: 2px solid var(--accent2);
    border-left: 2px solid var(--accent2);
    border-radius: 0 0 0 8px;
  }

  .status-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(16,185,129,0.1);
    border: 1px solid rgba(16,185,129,0.3);
    border-radius: 100px;
    padding: 6px 14px;
    font-size: 11px;
    color: var(--green);
    margin-bottom: 16px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .status-dot {
    width: 7px; height: 7px;
    background: var(--green);
    border-radius: 50%;
    animation: pulse 2s ease-in-out infinite;
  }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(32px, 5vw, 52px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #ffffff 0%, #00d4ff 50%, #7c3aed 100%);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: shimmer 4s linear infinite;
  }

  .hero-role {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    color: var(--accent);
    margin: 10px 0 18px;
    letter-spacing: 0.1em;
  }

  .hero-role::before { content: '// '; opacity: 0.5; }

  .hero-desc {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.7;
    max-width: 480px;
  }

  .avatar-ring {
    width: 120px; height: 120px;
    border-radius: 50%;
    padding: 3px;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3));
    animation: float 4s ease-in-out infinite;
    flex-shrink: 0;
  }
  .avatar-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: var(--card);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 800;
    background: linear-gradient(135deg, #0e1520, #111927);
    color: var(--accent);
    letter-spacing: -1px;
  }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    margin-bottom: 24px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 22px 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s ease, border-color 0.3s ease;
  }
  .stat-card:hover {
    transform: translateY(-4px);
    border-color: var(--accent);
    box-shadow: var(--glow);
  }
  .stat-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .stat-card:hover::after { opacity: 1; }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 32px;
    font-weight: 800;
    color: var(--accent);
    display: block;
    animation: countUp 0.8s cubic-bezier(.22,1,.36,1) both;
  }
  .stat-label {
    font-size: 11px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-top: 4px;
  }

  /* ── SECTION ── */
  .section {
    margin-bottom: 24px;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 16px;
  }

  .section-label {
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 700;
    color: var(--accent);
    text-transform: uppercase;
    letter-spacing: 0.15em;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ── TIMELINE ── */
  .timeline {
    position: relative;
    padding-left: 28px;
  }
  .timeline::before {
    content: '';
    position: absolute;
    left: 8px; top: 8px; bottom: 8px;
    width: 1px;
    background: linear-gradient(to bottom, var(--accent), var(--accent2), transparent);
  }

  .job-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
    margin-bottom: 16px;
    position: relative;
    transition: border-color 0.3s, transform 0.3s;
  }
  .job-card:hover {
    border-color: var(--accent);
    transform: translateX(4px);
  }
  .job-card::before {
    content: '';
    position: absolute;
    left: -24px; top: 28px;
    width: 10px; height: 10px;
    border-radius: 50%;
    background: var(--accent);
    border: 2px solid var(--bg);
    box-shadow: 0 0 10px var(--accent);
  }

  .job-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 6px;
  }

  .job-company {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--text);
  }

  .job-period {
    font-size: 11px;
    color: var(--accent3);
    background: rgba(245,158,11,0.1);
    border: 1px solid rgba(245,158,11,0.2);
    border-radius: 100px;
    padding: 3px 10px;
    white-space: nowrap;
  }

  .job-title {
    font-size: 12px;
    color: var(--accent);
    margin-bottom: 14px;
    letter-spacing: 0.05em;
  }

  .project-tag {
    display: inline-block;
    font-size: 10px;
    color: var(--accent2);
    background: rgba(124,58,237,0.1);
    border: 1px solid rgba(124,58,237,0.2);
    border-radius: 4px;
    padding: 2px 8px;
    margin-bottom: 10px;
    letter-spacing: 0.05em;
  }

  .job-bullets { list-style: none; }
  .job-bullets li {
    font-size: 12.5px;
    color: var(--muted);
    line-height: 1.6;
    padding: 4px 0;
    display: flex;
    gap: 10px;
  }
  .job-bullets li::before {
    content: '▸';
    color: var(--accent);
    flex-shrink: 0;
  }

  /* ── TECH GRID ── */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 12px;
  }

  .tech-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    transition: all 0.3s ease;
    cursor: default;
  }
  .tech-card:hover {
    border-color: var(--accent);
    transform: translateY(-4px) scale(1.03);
    box-shadow: 0 10px 30px rgba(0,212,255,0.1);
  }

  .tech-icon {
    font-size: 24px;
    filter: grayscale(0.2);
  }

  .tech-name {
    font-size: 11px;
    color: var(--text);
    font-weight: 500;
    text-align: center;
  }

  .tech-level {
    width: 100%;
    height: 3px;
    background: var(--border);
    border-radius: 100px;
    overflow: hidden;
  }

  .tech-fill {
    height: 100%;
    border-radius: 100px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transition: width 1.5s cubic-bezier(.22,1,.36,1);
  }

  /* ── SKILLS CHIPS ── */
  .chip-cloud {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .chip {
    font-size: 11px;
    padding: 6px 14px;
    border-radius: 100px;
    border: 1px solid var(--border);
    color: var(--muted);
    transition: all 0.2s;
    cursor: default;
    letter-spacing: 0.03em;
  }
  .chip:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(0,212,255,0.05);
  }
  .chip.hot {
    border-color: rgba(0,212,255,0.4);
    color: var(--accent);
    background: rgba(0,212,255,0.06);
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 16px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
  }
  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }
  .project-card:hover::before { transform: scaleX(1); }
  .project-card:hover {
    border-color: var(--accent);
    transform: translateY(-4px);
    box-shadow: 0 20px 40px rgba(0,0,0,0.4);
  }

  .project-icon {
    font-size: 28px;
    margin-bottom: 12px;
    display: block;
  }

  .project-title {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    margin-bottom: 8px;
    color: var(--text);
  }

  .project-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.6;
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 14px;
  }

  .p-tag {
    font-size: 10px;
    padding: 3px 9px;
    border-radius: 4px;
    background: rgba(0,212,255,0.08);
    border: 1px solid rgba(0,212,255,0.15);
    color: var(--accent);
  }

  /* ── CONTACT ── */
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
  }

  .contact-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px;
    display: flex;
    align-items: center;
    gap: 14px;
    transition: all 0.3s;
    text-decoration: none;
    color: var(--text);
  }
  .contact-card:hover {
    border-color: var(--accent);
    transform: translateY(-3px);
    box-shadow: var(--glow);
  }

  .contact-icon {
    font-size: 20px;
    width: 40px; height: 40px;
    background: rgba(0,212,255,0.08);
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .contact-label {
    font-size: 10px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }
  .contact-val {
    font-size: 12px;
    color: var(--text);
    margin-top: 2px;
  }

  /* ── FOOTER QUOTE ── */
  .footer-quote {
    text-align: center;
    padding: 40px 20px;
    font-family: 'Syne', sans-serif;
    font-size: 18px;
    font-weight: 700;
    color: var(--border);
    letter-spacing: 0.05em;
    position: relative;
  }
  .footer-quote span {
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  /* ── ACHIEVEMENT PILLS ── */
  .achievements {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 12px;
  }
  .ach-pill {
    display: flex;
    align-items: center;
    gap: 7px;
    font-size: 11.5px;
    color: var(--text);
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 8px 14px;
  }
  .ach-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* ── DELAY UTILITIES ── */
  .d1 { animation-delay: 0.1s; }
  .d2 { animation-delay: 0.2s; }
  .d3 { animation-delay: 0.3s; }
  .d4 { animation-delay: 0.4s; }
  .d5 { animation-delay: 0.5s; }
  .d6 { animation-delay: 0.6s; }
  .d7 { animation-delay: 0.7s; }
  .d8 { animation-delay: 0.8s; }
  .d9 { animation-delay: 0.9s; }
  .d10 { animation-delay: 1.0s; }
  .d11 { animation-delay: 1.1s; }
  .d12 { animation-delay: 1.2s; }

  @media (max-width: 640px) {
    .hero { grid-template-columns: 1fr; }
    .avatar-ring { display: none; }
    .stats-row { grid-template-columns: repeat(2, 1fr); }
    .contact-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<div class="scanline"></div>

<div class="page-wrapper">

  <!-- ── HERO ── -->
  <div class="hero slide-left d1">
    <div class="hero-corner"></div>
    <div class="hero-corner hero-corner-bl"></div>
    <div>
      <div class="status-badge slide-left d2">
        <span class="status-dot"></span>
        Open to Remote Opportunities
      </div>
      <h1 class="hero-name slide-left d3">Nikhil<br>Suryawanshi</h1>
      <div class="hero-role slide-left d4">Senior Full-Stack Engineer · 5+ Years</div>
      <p class="hero-desc slide-left d5">
        Building enterprise-grade CRM systems, REST APIs & automation tools.
        Laravel · React · Vue · Node.js · AWS · Docker.
        Based in Nashik, India.
      </p>
      <div class="achievements slide-up d6">
        <div class="ach-pill">
          <span class="ach-dot" style="background:var(--accent)"></span>
          5+ Enterprise CRMs
        </div>
        <div class="ach-pill">
          <span class="ach-dot" style="background:var(--accent2)"></span>
          3 Chrome Extensions
        </div>
        <div class="ach-pill">
          <span class="ach-dot" style="background:var(--accent3)"></span>
          AWS · Docker · CI/CD
        </div>
        <div class="ach-pill">
          <span class="ach-dot" style="background:var(--green)"></span>
          RBAC · JWT · Shopify API
        </div>
      </div>
    </div>
    <div class="avatar-ring slide-right d4">
      <div class="avatar-inner">NS</div>
    </div>
  </div>

  <!-- ── STATS ── -->
  <div class="stats-row">
    <div class="stat-card slide-up d3">
      <span class="stat-num">5+</span>
      <div class="stat-label">Years Exp.</div>
    </div>
    <div class="stat-card slide-up d4">
      <span class="stat-num">10+</span>
      <div class="stat-label">Projects</div>
    </div>
    <div class="stat-card slide-up d5">
      <span class="stat-num">3</span>
      <div class="stat-label">Chrome Ext.</div>
    </div>
    <div class="stat-card slide-up d6">
      <span class="stat-num">∞</span>
      <div class="stat-label">Scalability</div>
    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <div class="section slide-up d5">
    <div class="section-header">
      <span class="section-label">⚙ Tech Stack</span>
      <div class="section-line"></div>
    </div>
    <div class="tech-grid">
      <div class="tech-card"><div class="tech-icon">🛡️</div><div class="tech-name">Laravel / PHP</div><div class="tech-level"><div class="tech-fill" style="width:95%"></div></div></div>
      <div class="tech-card"><div class="tech-icon">⚛️</div><div class="tech-name">React.js</div><div class="tech-level"><div class="tech-fill" style="width:90%"></div></div></div>
      <div class="tech-card"><div class="tech-icon">🟢</div><div class="tech-name">Vue.js</div><div class="tech-level"><div class="tech-fill" style="width:88%"></div></div></div>
      <div class="tech-card"><div class="tech-icon">🟡</div><div class="tech-name">Node.js</div><div class="tech-level"><div class="tech-fill" style="width:85%"></div></div></div>
      <div class="tech-card"><div class="tech-icon">🗄️</div><div class="tech-name">MySQL</div><div class="tech-level"><div class="tech-fill" style="width:92%"></div></div></div>
      <div class="tech-card"><div class="tech-icon">🍃</div><div class="tech-name">MongoDB</div><div class="tech-level"><div class="tech-fill" style="width:80%"></div></div></div>
      <div class="tech-card"><div class="tech-icon">☁️</div><div class="tech-name">AWS EC2</div><div class="tech-level"><div class="tech-fill" style="width:78%"></div></div></div>
      <div class="tech-card"><div class="tech-icon">🐳</div><div class="tech-name">Docker / CI/CD</div><div class="tech-level"><div class="tech-fill" style="width:82%"></div></div></div>
    </div>
  </div>

  <!-- ── SKILLS CHIPS ── -->
  <div class="section slide-up d6">
    <div class="section-header">
      <span class="section-label">🏷 Skills</span>
      <div class="section-line"></div>
    </div>
    <div class="chip-cloud">
      <span class="chip hot">REST API</span>
      <span class="chip hot">JWT Auth</span>
      <span class="chip hot">RBAC</span>
      <span class="chip hot">Shopify API</span>
      <span class="chip hot">Google Calendar API</span>
      <span class="chip">Chrome Extensions</span>
      <span class="chip">Express.js</span>
      <span class="chip">Git</span>
      <span class="chip">Agile / Scrum</span>
      <span class="chip">Workflow Automation</span>
      <span class="chip">System Architecture</span>
      <span class="chip">Performance Optimization</span>
    </div>
  </div>

  <!-- ── EXPERIENCE ── -->
  <div class="section slide-up d7">
    <div class="section-header">
      <span class="section-label">💼 Experience</span>
      <div class="section-line"></div>
    </div>
    <div class="timeline">

      <!-- Job 1 -->
      <div class="job-card slide-left d5">
        <div class="job-top">
          <div>
            <div class="job-company">Makedreams Technologies Pvt. Ltd.</div>
            <div class="job-title">Senior Software Developer</div>
          </div>
          <span class="job-period">Sep 2023 – Present</span>
        </div>
        <div style="margin-bottom:14px;">
          <div class="project-tag">Mokapen CRM · React + Laravel</div>
          <ul class="job-bullets">
            <li>Engineered multi-user CRM with RBAC and secure JWT authentication.</li>
            <li>Integrated Shopify API and Google Calendar for scheduling automation.</li>
            <li>Deployed on AWS EC2, configured Docker environments with CI/CD pipelines.</li>
            <li>Optimized MySQL queries — significantly improved system responsiveness.</li>
          </ul>
        </div>
        <div>
          <div class="project-tag">Elite Mortgage CRM · Vue + Laravel</div>
          <ul class="job-bullets">
            <li>Built loan workflow automation and document management modules.</li>
            <li>Real-time loan tracking and notification engine for operational transparency.</li>
          </ul>
        </div>
        <div style="margin-top:14px;">
          <div class="project-tag">Chrome Extensions Suite · React.js</div>
          <ul class="job-bullets">
            <li>Developed 3 Chrome Extensions (LinkedIn, Outlook, Gmail) for CRM data capture.</li>
            <li>Integrated with backend REST APIs for real-time synchronization.</li>
          </ul>
        </div>
      </div>

      <!-- Job 2 -->
      <div class="job-card slide-right d6">
        <div class="job-top">
          <div>
            <div class="job-company">Excelsior Research Pvt. Ltd.</div>
            <div class="job-title">Senior Software Developer</div>
          </div>
          <span class="job-period">Jan 2023 – Sep 2023</span>
        </div>
        <div class="project-tag">Support Desk · Pune</div>
        <ul class="job-bullets">
          <li>Built a scalable ticket management system with real-time notifications.</li>
          <li>Developed analytics dashboards using modern JavaScript technologies.</li>
          <li>Implemented REST API integrations for third-party services.</li>
        </ul>
      </div>

      <!-- Job 3 -->
      <div class="job-card slide-left d7">
        <div class="job-top">
          <div>
            <div class="job-company">Aspire Webs Infomatics</div>
            <div class="job-title">Software Developer</div>
          </div>
          <span class="job-period">Jan 2022 – Jan 2023</span>
        </div>
        <div class="project-tag">Hospital Management System · Laravel</div>
        <ul class="job-bullets">
          <li>Developed full-stack hospital system (patient admission, billing, bed tracking).</li>
          <li>Implemented secure authentication and optimized MySQL database performance.</li>
        </ul>
      </div>

    </div>
  </div>

  <!-- ── PROJECTS ── -->
  <div class="section slide-up d8">
    <div class="section-header">
      <span class="section-label">🚀 Featured Projects</span>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">

      <div class="project-card slide-up d6">
        <span class="project-icon">🏗️</span>
        <div class="project-title">CRM Toolkit</div>
        <div class="project-desc">Modular Laravel CRM with authentication, RBAC, and REST API foundation. Open-source & production-ready.</div>
        <div class="project-tags">
          <span class="p-tag">Laravel</span>
          <span class="p-tag">RBAC</span>
          <span class="p-tag">REST API</span>
        </div>
      </div>

      <div class="project-card slide-up d7">
        <span class="project-icon">🔌</span>
        <div class="project-title">Chrome Extension Suite</div>
        <div class="project-desc">LinkedIn, Gmail & Outlook extensions for automated CRM data capture with real-time backend sync.</div>
        <div class="project-tags">
          <span class="p-tag">React.js</span>
          <span class="p-tag">Manifest V3</span>
          <span class="p-tag">REST API</span>
        </div>
      </div>

      <div class="project-card slide-up d8">
        <span class="project-icon">🏥</span>
        <div class="project-title">Hospital Management System</div>
        <div class="project-desc">Full-stack system for patient tracking, automated billing, appointment scheduling & bed availability.</div>
        <div class="project-tags">
          <span class="p-tag">React</span>
          <span class="p-tag">Laravel</span>
          <span class="p-tag">MySQL</span>
        </div>
      </div>

      <div class="project-card slide-up d9">
        <span class="project-icon">🏦</span>
        <div class="project-title">Elite Mortgage CRM</div>
        <div class="project-desc">Loan workflow automation with document management, multi-role access control, and real-time tracking.</div>
        <div class="project-tags">
          <span class="p-tag">Vue.js</span>
          <span class="p-tag">Laravel</span>
          <span class="p-tag">Notifications</span>
        </div>
      </div>

    </div>
  </div>

  <!-- ── EDUCATION ── -->
  <div class="section slide-up d9">
    <div class="section-header">
      <span class="section-label">🎓 Education</span>
      <div class="section-line"></div>
    </div>
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:14px;">
      <div class="stat-card" style="text-align:left;padding:20px;">
        <div style="font-family:'Syne',sans-serif;font-size:13px;font-weight:700;color:var(--text)">M.Sc. Computer Science</div>
        <div style="font-size:11px;color:var(--accent);margin-top:4px;">Pune University · 2022</div>
      </div>
      <div class="stat-card" style="text-align:left;padding:20px;">
        <div style="font-family:'Syne',sans-serif;font-size:13px;font-weight:700;color:var(--text)">B.Sc. Computer Science</div>
        <div style="font-size:11px;color:var(--accent);margin-top:4px;">Pune University · 2019</div>
      </div>
    </div>
  </div>

  <!-- ── CONTACT ── -->
  <div class="section slide-up d10">
    <div class="section-header">
      <span class="section-label">📬 Connect</span>
      <div class="section-line"></div>
    </div>
    <div class="contact-grid">
      <a href="mailto:nikhilsuryawanshi000@gmail.com" class="contact-card">
        <div class="contact-icon">✉️</div>
        <div>
          <div class="contact-label">Email</div>
          <div class="contact-val">nikhilsuryawanshi000@gmail.com</div>
        </div>
      </a>
      <a href="https://github.com/Nikhil-Suryawanshii" target="_blank" class="contact-card">
        <div class="contact-icon">🐙</div>
        <div>
          <div class="contact-label">GitHub</div>
          <div class="contact-val">Nikhil-Suryawanshii</div>
        </div>
      </a>
      <a href="https://nikhil-suryawanshi.vercel.app/" target="_blank" class="contact-card">
        <div class="contact-icon">🌐</div>
        <div>
          <div class="contact-label">Portfolio</div>
          <div class="contact-val">nikhil-suryawanshi.vercel.app</div>
        </div>
      </a>
    </div>
  </div>

  <!-- ── FOOTER ── -->
  <div class="footer-quote slide-up d12">
    <span>Code. Build. Scale. Repeat.</span>
  </div>

</div>

</body>
</html>
