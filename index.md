---
layout: default
---

<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: #0f1115 !important;
    color: #e2e8f0;
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Syne:wght@400;600;800&display=swap');

  .rk-page {
    font-family: 'Syne', sans-serif;
    max-width: 860px;
    margin: 0 auto;
    padding: 0 1.5rem 4rem;
    position: relative;
  }

  .rk-page::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(29,158,117,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(29,158,117,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .rk-inner { position: relative; z-index: 1; }

  /* HEADER */
  .rk-header {
    padding: 3rem 0 2.5rem;
    border-bottom: 0.5px solid rgba(29,158,117,0.2);
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 2rem;
  }

  .rk-header-left { flex: 1; }

  .rk-badge-row {
    display: flex;
    gap: 8px;
    margin-bottom: 1.2rem;
    flex-wrap: wrap;
  }

  .rk-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 3px 10px;
    border-radius: 20px;
    border: 0.5px solid rgba(29,158,117,0.4);
    color: #1D9E75;
    background: rgba(29,158,117,0.08);
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .rk-badge.online { background: rgba(29,158,117,0.15); border-color: #1D9E75; }
  .rk-badge.online::before { content: '● '; animation: rk-blink 1.4s ease-in-out infinite; }

  @keyframes rk-blink { 0%,100% { opacity:1; } 50% { opacity:0.3; } }

  .rk-h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2rem, 5vw, 3.4rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    color: #f1f5f9;
    margin-bottom: 0.5rem;
  }

  .rk-h1 span { color: #1D9E75; }

  .rk-tagline {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: #64748b;
    margin-bottom: 1.5rem;
    letter-spacing: 0.02em;
  }

  .rk-about {
    font-size: 15px;
    line-height: 1.75;
    color: #94a3b8;
    max-width: 520px;
  }

  .rk-about strong { color: #e2e8f0; font-weight: 600; }

  .rk-avatar-ring {
    width: 96px;
    height: 96px;
    border-radius: 50%;
    border: 1.5px solid rgba(29,158,117,0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    background: rgba(29,158,117,0.07);
    font-family: 'JetBrains Mono', monospace;
    font-size: 28px;
    font-weight: 700;
    color: #1D9E75;
    letter-spacing: -0.05em;
    flex-shrink: 0;
  }

  /* LINKS BAR */
  .rk-links-bar {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    padding: 1.5rem 0;
    border-bottom: 0.5px solid rgba(255,255,255,0.05);
  }

  .rk-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #94a3b8;
    text-decoration: none;
    padding: 6px 14px;
    border: 0.5px solid rgba(255,255,255,0.1);
    border-radius: 20px;
    background: rgba(255,255,255,0.03);
    transition: all 0.2s;
  }

  .rk-pill:hover {
    color: #1D9E75;
    border-color: rgba(29,158,117,0.4);
    background: rgba(29,158,117,0.07);
    text-decoration: none;
  }

  .rk-pill .rk-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: currentColor;
    flex-shrink: 0;
  }

  /* SECTIONS */
  .rk-section { margin-top: 2.5rem; }

  .rk-section-head {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 1.25rem;
  }

  .rk-section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #1D9E75;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    white-space: nowrap;
  }

  .rk-section-line {
    flex: 1;
    height: 0.5px;
    background: linear-gradient(90deg, rgba(29,158,117,0.3), transparent);
  }

  /* PROJECTS */
  .rk-projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 12px;
  }

  .rk-card {
    background: rgba(255,255,255,0.02);
    border: 0.5px solid rgba(255,255,255,0.08);
    border-radius: 10px;
    padding: 1.1rem 1.2rem;
    text-decoration: none;
    display: block;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
    color: inherit;
  }

  .rk-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1.5px;
    background: transparent;
    transition: background 0.2s;
  }

  .rk-card:hover {
    border-color: rgba(29,158,117,0.3);
    background: rgba(29,158,117,0.04);
    text-decoration: none;
  }

  .rk-card:hover::before {
    background: linear-gradient(90deg, transparent, #1D9E75, transparent);
  }

  .rk-card-name {
    font-size: 14px;
    font-weight: 600;
    color: #e2e8f0;
    margin-bottom: 5px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .rk-card-name .rk-ext { font-size: 11px; color: #1D9E75; opacity: 0.7; }

  .rk-card-desc {
    font-size: 12px;
    color: #64748b;
    line-height: 1.5;
    font-family: 'JetBrains Mono', monospace;
  }

  /* STATS */
  .rk-stats-link { display: inline-block; }
  .rk-stats-link img {
    border-radius: 8px;
    border: 0.5px solid rgba(255,255,255,0.08);
    max-width: 100%;
    display: block;
  }

  /* CERTS */
  .rk-certs-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 10px;
  }

  .rk-cert {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 14px;
    background: rgba(255,255,255,0.02);
    border: 0.5px solid rgba(255,255,255,0.07);
    border-radius: 8px;
    text-decoration: none;
    transition: all 0.2s;
    color: inherit;
  }

  .rk-cert:hover {
    border-color: rgba(29,158,117,0.3);
    background: rgba(29,158,117,0.04);
    text-decoration: none;
  }

  .rk-cert img {
    width: 32px;
    height: 32px;
    object-fit: contain;
    border-radius: 4px;
    flex-shrink: 0;
  }

  .rk-cert-name {
    font-size: 13px;
    color: #cbd5e1;
    font-weight: 500;
  }

  /* QUOTE */
  .rk-quote {
    margin-top: 3rem;
    padding: 1.5rem 0;
    border-top: 0.5px solid rgba(255,255,255,0.05);
    text-align: center;
  }

  .rk-quote p {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: #475569;
    font-style: italic;
    letter-spacing: 0.02em;
  }

  .rk-quote p span { color: #1D9E75; }

  .rk-footer-note {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #334155;
    margin-top: 1rem;
    letter-spacing: 0.1em;
    text-align: center;
  }
</style>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">

<div class="rk-page">
<div class="rk-inner">

  <!-- HEADER -->
  <div class="rk-header">
    <div class="rk-header-left">
      <div class="rk-badge-row">
        <span class="rk-badge online">online</span>
        <span class="rk-badge">fintech · 13 yrs</span>
        <span class="rk-badge">homelab</span>
        <span class="rk-badge">open source</span>
      </div>
      <h1 class="rk-h1">Ramkrishnan<br><span>Thevar.</span></h1>
      <p class="rk-tagline">// technology manager · capital markets · self-hoster</p>
      <p class="rk-about">
        With over <strong>13 years in fintech</strong>, I specialise in capital markets, software development, and project management. Outside work, I tinker with <strong>Raspberry Pi</strong>, self-host everything I can, and stay current on trends through podcasts.
      </p>
    </div>
    <div class="rk-avatar-ring">rk.</div>
  </div>

  <!-- LINKS -->
  <div class="rk-links-bar">
    <a class="rk-pill" href="http://cloud.rklab.co.in/s/rkresume" target="_blank">
      <span class="rk-dot"></span> résumé
    </a>
    <a class="rk-pill" href="https://cloud.rklab.co.in/s/resumepodcast" target="_blank">
      <span class="rk-dot"></span> 🎙 listen to résumé
    </a>
    <a class="rk-pill" href="http://send.rklab.co.in" target="_blank">
      <span class="rk-dot"></span> share files
    </a>
    <a class="rk-pill" href="https://chessarena.com/profile/750754" target="_blank">
      <span class="rk-dot"></span> ♟ chess arena
    </a>
    <a class="rk-pill" href="https://rklab.co.in" target="_blank">
      <span class="rk-dot"></span> rklab.co.in ↗
    </a>
    <a class="rk-pill" href="https://status.rklab.co.in" target="_blank">
      <span class="rk-dot"></span> homelab status
    </a>
  </div>

  <!-- PROJECTS -->
  <div class="rk-section">
    <div class="rk-section-head">
      <span class="rk-section-label">projects</span>
      <div class="rk-section-line"></div>
    </div>
    <div class="rk-projects-grid">
      <a class="rk-card" href="https://carconnect.rklab.co.in" target="_blank">
        <div class="rk-card-name">CarConnect — QR Gen <span class="rk-ext">↗</span></div>
        <div class="rk-card-desc">QR-based vehicle contact system</div>
      </a>
      <a class="rk-card" href="https://rklab.co.in/ai" target="_blank">
        <div class="rk-card-name">SensAI <span class="rk-ext">↗</span></div>
        <div class="rk-card-desc">Self-hosted AI assistant on homelab</div>
      </a>
      <a class="rk-card" href="https://rklab.co.in/" target="_blank">
        <div class="rk-card-name">rkLaB v2 <span class="rk-ext">↗</span></div>
        <div class="rk-card-desc">Personal self-hosted infrastructure</div>
      </a>
      <a class="rk-card" href="https://www.linkedin.com/pulse/self-hosting-freak-ramkrishnan-thevar" target="_blank">
        <div class="rk-card-name">Home Automation <span class="rk-ext">↗</span></div>
        <div class="rk-card-desc">Self-hosting journey writeup on LinkedIn</div>
      </a>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="rk-section">
    <div class="rk-section-head">
      <span class="rk-section-label">github stats</span>
      <div class="rk-section-line"></div>
    </div>
    <a class="rk-stats-link" href="https://awesome-github-stats.azurewebsites.net/index.html??cardType=level&theme=github-dark&fontFamily=&preferLogin=false" target="_blank">
      <img alt="1ramkrishnan's GitHub Stats" src="https://awesome-github-stats.azurewebsites.net/user-stats/1ramkrishnan?cardType=level&theme=github-dark&fontFamily=&preferLogin=false" />
    </a>
  </div>

  <!-- CERTIFICATIONS -->
  <div class="rk-section">
    <div class="rk-section-head">
      <span class="rk-section-label">certifications</span>
      <div class="rk-section-line"></div>
    </div>
    <div class="rk-certs-grid">
      <a class="rk-cert" href="https://drive.google.com/file/d/1-ArkycQZgtb7_4Jw-Vuw6bB8QLHb6Or2/view" target="_blank">
        <img src="https://github.com/1ramkrishnan/1Ramkrishnan.github.io/raw/master/images/mean.png" alt="MEAN Stack">
        <span class="rk-cert-name">MEAN Stack</span>
      </a>
      <a class="rk-cert" href="https://drive.google.com/file/d/1-X6IL5UW_Asf6ra6_lbA0K0_W29xNbjS/view" target="_blank">
        <img src="https://github.com/1ramkrishnan/1Ramkrishnan.github.io/raw/master/images/aspnet.png" alt="ASP.NET">
        <span class="rk-cert-name">ASP.NET</span>
      </a>
      <a class="rk-cert" href="https://drive.google.com/file/d/1-EHClNZ8j6YAiBGMnvyKDqPVTUydGBlQ/view" target="_blank">
        <img src="https://i0.wp.com/www.msicertified.com/wp-content/uploads/2021/10/PMEC.png?resize=150%2C150&ssl=1" alt="PM Essentials">
        <span class="rk-cert-name">PM Essentials</span>
      </a>
      <a class="rk-cert" href="https://drive.google.com/file/d/1pW2_VcX14IB5j_13cmO8lE0toykxCAGS/view" target="_blank">
        <img src="https://raw.githubusercontent.com/1ramkrishnan/1Ramkrishnan.github.io/master/images/lsswb150.png" alt="Lean Six Sigma">
        <span class="rk-cert-name">Lean Six Sigma White Belt</span>
      </a>
      <a class="rk-cert" href="https://www.credly.com/badges/5af788da-a8b8-4315-bab3-145b4129537b/public_url" target="_blank">
        <img src="https://images.credly.com/size/680x680/images/b870667f-00a3-48d7-b988-9c02b441b883/image.png" alt="Credly Badge 1">
        <span class="rk-cert-name">Credly Badge 1</span>
      </a>
      <a class="rk-cert" href="https://www.credly.com/badges/3f34cc17-619e-4feb-8aff-4ead1b2e50ba/public_url" target="_blank">
        <img src="https://images.credly.com/images/8f006312-3154-45bf-a845-4a043641e83c/blob" alt="Credly Badge 2">
        <span class="rk-cert-name">Credly Badge 2</span>
      </a>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="rk-quote">
    <p>"you will find your purpose where you find your <span>happiness</span>" ✌️</p>
    <p class="rk-footer-note">// rklab.co.in · status.rklab.co.in · 1ramkrishnan.github.io</p>
  </div>

</div>
</div>
