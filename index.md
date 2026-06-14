-----

## layout: default

<style>
  @import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:ital,wght@0,400;0,500;0,600;1,400&family=IBM+Plex+Sans:wght@300;400;500;600;700&display=swap');

  /* ── RESET JEKYLL CAYMAN THEME ── */
  header.site-header, .site-header, nav, .navbar,
  footer.site-footer, .site-footer, .page-header,
  [role="banner"], footer { display: none !important; }

  body {
    background: #0f1115 !important;
    color: #c8d3e0 !important;
    font-family: 'IBM Plex Sans', sans-serif !important;
    padding: 0 !important;
    margin: 0 !important;
    min-height: 100vh;
  }

  .main-content, .container-lg, .container-md, main {
    max-width: 100% !important;
    padding: 0 !important;
    margin: 0 !important;
  }

  *, *::before, *::after { box-sizing: border-box; }

  /* ── GRID BG ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(48,225,125,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(48,225,125,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  /* ── LAYOUT ── */
  .rk-wrap {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 0 1.5rem 5rem;
  }

  /* ── NAV BAR ── */
  .rk-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.4rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.05);
    margin-bottom: 3.5rem;
  }

  .rk-nav-logo {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 14px;
    font-weight: 600;
    color: #30e17d;
    text-decoration: none;
    letter-spacing: 0.04em;
  }

  .rk-nav-links {
    display: flex;
    gap: 1.5rem;
    list-style: none;
    margin: 0; padding: 0;
  }

  .rk-nav-links a {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    color: #64748b;
    text-decoration: none;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    transition: color 0.15s;
  }

  .rk-nav-links a:hover { color: #30e17d; }

  /* ── HERO ── */
  .rk-hero {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: flex-start;
    gap: 2.5rem;
    padding-bottom: 3rem;
    border-bottom: 1px solid rgba(255,255,255,0.05);
  }

  .rk-eyebrow {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    color: #30e17d;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .rk-eyebrow::before {
    content: '';
    display: inline-block;
    width: 20px;
    height: 1px;
    background: #30e17d;
    flex-shrink: 0;
  }

  .rk-name {
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: clamp(2.2rem, 5.5vw, 3.8rem);
    font-weight: 700;
    line-height: 1.04;
    letter-spacing: -0.03em;
    color: #f0f4f8;
    margin: 0 0 0.3rem;
  }

  .rk-name em {
    font-style: normal;
    color: #30e17d;
  }

  .rk-title-line {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 12px;
    color: #475569;
    margin-bottom: 1.4rem;
    letter-spacing: 0.04em;
  }

  .rk-title-line span { color: #64748b; }

  .rk-bio {
    font-size: 15px;
    line-height: 1.75;
    color: #94a3b8;
    max-width: 540px;
  }

  .rk-bio strong { color: #cbd5e1; font-weight: 600; }

  /* ── MONOGRAM ── */
  .rk-mono-badge {
    width: 88px;
    height: 88px;
    border-radius: 14px;
    border: 1px solid rgba(48,225,125,0.25);
    background: rgba(48,225,125,0.05);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    gap: 2px;
  }

  .rk-mono-badge .initials {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 26px;
    font-weight: 600;
    color: #30e17d;
    line-height: 1;
    letter-spacing: -0.04em;
  }

  .rk-mono-badge .tagline-sm {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 8px;
    color: #30e17d;
    opacity: 0.5;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  /* ── STATUS DOT ── */
  .rk-status-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: #30e17d;
    border: 1px solid rgba(48,225,125,0.2);
    background: rgba(48,225,125,0.06);
    padding: 3px 10px 3px 8px;
    border-radius: 20px;
    margin-bottom: 1.1rem;
  }

  .rk-status-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: #30e17d;
    animation: rk-pulse 2s ease-in-out infinite;
    flex-shrink: 0;
  }

  @keyframes rk-pulse { 0%,100%{opacity:1;}50%{opacity:0.3;} }

  /* ── QUICK LINKS ── */
  .rk-links {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 1.8rem;
  }

  .rk-link-pill {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    color: #64748b;
    text-decoration: none;
    padding: 6px 14px;
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 6px;
    background: rgba(255,255,255,0.025);
    transition: all 0.15s;
    letter-spacing: 0.02em;
  }

  .rk-link-pill:hover {
    color: #30e17d;
    border-color: rgba(48,225,125,0.35);
    background: rgba(48,225,125,0.06);
    text-decoration: none;
  }

  .rk-link-pill.primary {
    color: #30e17d;
    border-color: rgba(48,225,125,0.35);
    background: rgba(48,225,125,0.08);
  }

  .rk-link-pill.primary:hover {
    background: rgba(48,225,125,0.15);
  }

  /* ── SECTION HEADING ── */
  .rk-section { margin-top: 3rem; }

  .rk-sh {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 1.25rem;
  }

  .rk-sh-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: #30e17d;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    white-space: nowrap;
  }

  .rk-sh-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(48,225,125,0.25) 0%, transparent 100%);
  }

  /* ── PROJECTS GRID ── */
  .rk-proj-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(210px, 1fr));
    gap: 10px;
  }

  .rk-proj {
    display: block;
    text-decoration: none;
    padding: 1rem 1.1rem;
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 10px;
    transition: all 0.15s;
    position: relative;
    overflow: hidden;
    color: inherit;
  }

  .rk-proj::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: transparent;
    transition: background 0.15s;
  }

  .rk-proj:hover {
    border-color: rgba(48,225,125,0.25);
    background: rgba(48,225,125,0.04);
    text-decoration: none;
    transform: translateY(-1px);
  }

  .rk-proj:hover::after {
    background: linear-gradient(90deg, transparent, rgba(48,225,125,0.6), transparent);
  }

  .rk-proj-name {
    font-size: 13px;
    font-weight: 600;
    color: #e2e8f0;
    margin-bottom: 4px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .rk-proj-arrow { color: #30e17d; opacity: 0.6; font-size: 12px; }

  .rk-proj-desc {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    color: #475569;
    line-height: 1.55;
  }

  /* ── STATS ── */
  .rk-stats-wrap {
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 10px;
    padding: 1.25rem;
    display: flex;
    justify-content: center;
  }

  .rk-stats-wrap img {
    border-radius: 6px;
    max-width: 100%;
    display: block;
  }

  /* ── CERTS GRID ── */
  .rk-cert-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 8px;
  }

  .rk-cert {
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
    padding: 10px 14px;
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 8px;
    transition: all 0.15s;
    color: inherit;
  }

  .rk-cert:hover {
    border-color: rgba(48,225,125,0.25);
    background: rgba(48,225,125,0.04);
    text-decoration: none;
  }

  .rk-cert img {
    width: 30px; height: 30px;
    object-fit: contain;
    border-radius: 4px;
    flex-shrink: 0;
    filter: brightness(0.9);
  }

  .rk-cert-text {}
  .rk-cert-name { font-size: 12px; color: #cbd5e1; font-weight: 500; }
  .rk-cert-type { font-family: 'IBM Plex Mono', monospace; font-size: 10px; color: #475569; margin-top: 2px; }

  /* ── RESUME AUDIO ── */
  .rk-audio-card {
    background: rgba(48,225,125,0.04);
    border: 1px solid rgba(48,225,125,0.15);
    border-radius: 10px;
    padding: 1.1rem 1.25rem;
    display: flex;
    align-items: center;
    gap: 1rem;
    text-decoration: none;
    color: inherit;
    transition: all 0.15s;
  }

  .rk-audio-card:hover {
    background: rgba(48,225,125,0.08);
    border-color: rgba(48,225,125,0.3);
    text-decoration: none;
  }

  .rk-audio-icon {
    font-size: 20px;
    flex-shrink: 0;
  }

  .rk-audio-label {
    font-size: 13px;
    color: #e2e8f0;
    font-weight: 500;
  }

  .rk-audio-sub {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: #30e17d;
    opacity: 0.7;
    margin-top: 2px;
  }

  /* ── FOOTER QUOTE ── */
  .rk-footer {
    margin-top: 4rem;
    padding-top: 2rem;
    border-top: 1px solid rgba(255,255,255,0.05);
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .rk-quote {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    color: #334155;
    font-style: italic;
    letter-spacing: 0.02em;
  }

  .rk-quote em { font-style: normal; color: #30e17d; opacity: 0.7; }

  .rk-footer-sig {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: #1e293b;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 640px) {
    .rk-hero { grid-template-columns: 1fr; }
    .rk-mono-badge { display: none; }
    .rk-nav-links { display: none; }
    .rk-footer { flex-direction: column; }
  }

  @media (max-width: 480px) {
    .rk-proj-grid { grid-template-columns: 1fr; }
    .rk-cert-grid { grid-template-columns: 1fr; }
  }
</style>

<div class="rk-wrap">

  <!-- NAV -->

  <nav class="rk-nav">
    <a class="rk-nav-logo" href="https://1ramkrishnan.github.io">[ rk ]</a>
    <ul class="rk-nav-links">
      <li><a href="https://rklab.co.in">rkLaB</a></li>
      <li><a href="https://status.rklab.co.in">Status</a></li>
      <li><a href="http://cloud.rklab.co.in/s/rkresume">Résumé</a></li>
    </ul>
  </nav>

  <!-- HERO -->

  <section class="rk-hero">
    <div>
      <div class="rk-status-pill">
        <span class="rk-status-dot"></span>
        available · Mumbai, India
      </div>
      <div class="rk-eyebrow">Technology Manager</div>
      <h1 class="rk-name">Ramkrishnan<br><em>Thevar.</em></h1>
      <p class="rk-title-line">// fintech · capital markets · <span>self-hoster</span></p>
      <p class="rk-bio">
        Over <strong>13 years in fintech</strong> spanning capital markets, cards IT, software development, and project management.
        Outside work, I run <strong>rkLaB</strong> — a self-hosted homelab on Raspberry Pi clusters where curiosity runs 24/7.
      </p>
      <div class="rk-links">
        <a class="rk-link-pill primary" href="http://cloud.rklab.co.in/s/rkresume">résumé ↗</a>
        <a class="rk-link-pill" href="https://cloud.rklab.co.in/s/resumepodcast">🎙 listen</a>
        <a class="rk-link-pill" href="http://send.rklab.co.in">share files</a>
        <a class="rk-link-pill" href="https://rklab.co.in">rklab.co.in ↗</a>
        <a class="rk-link-pill" href="https://chessarena.com/profile/750754">♟ chess</a>
        <a class="rk-link-pill" href="https://status.rklab.co.in">● homelab status</a>
      </div>
    </div>
    <div class="rk-mono-badge">
      <span class="initials">rk</span>
      <span class="tagline-sm">rkLaB</span>
    </div>
  </section>

  <!-- PROJECTS -->

  <section class="rk-section">
    <div class="rk-sh">
      <span class="rk-sh-label">projects</span>
      <span class="rk-sh-line"></span>
    </div>
    <div class="rk-proj-grid">
      <a class="rk-proj" href="https://carconnect.rklab.co.in">
        <div class="rk-proj-name">CarConnect — QR Gen <span class="rk-proj-arrow">↗</span></div>
        <div class="rk-proj-desc">QR-based vehicle contact system</div>
      </a>
      <a class="rk-proj" href="https://rklab.co.in/ai">
        <div class="rk-proj-name">SensAI <span class="rk-proj-arrow">↗</span></div>
        <div class="rk-proj-desc">Self-hosted AI assistant on homelab</div>
      </a>
      <a class="rk-proj" href="https://rklab.co.in/">
        <div class="rk-proj-name">rkLaB v2 <span class="rk-proj-arrow">↗</span></div>
        <div class="rk-proj-desc">Personal self-hosted infrastructure</div>
      </a>
      <a class="rk-proj" href="https://www.linkedin.com/pulse/self-hosting-freak-ramkrishnan-thevar">
        <div class="rk-proj-name">Home Automation <span class="rk-proj-arrow">↗</span></div>
        <div class="rk-proj-desc">Self-hosting journey writeup on LinkedIn</div>
      </a>
    </div>
  </section>

  <!-- RESUME AUDIO -->

  <section class="rk-section">
    <div class="rk-sh">
      <span class="rk-sh-label">résumé</span>
      <span class="rk-sh-line"></span>
    </div>
    <a class="rk-audio-card" href="https://cloud.rklab.co.in/s/resumepodcast">
      <span class="rk-audio-icon">🎙</span>
      <div>
        <div class="rk-audio-label">Listen to my résumé</div>
        <div class="rk-audio-sub">audio · ~3 min · Technology Manager</div>
      </div>
    </a>
  </section>

  <!-- GITHUB STATS -->

  <section class="rk-section">
    <div class="rk-sh">
      <span class="rk-sh-label">github stats</span>
      <span class="rk-sh-line"></span>
    </div>
    <div class="rk-stats-wrap">
      <a href="https://awesome-github-stats.azurewebsites.net/index.html??cardType=level&theme=github-dark&fontFamily=&preferLogin=false">
        <img src="https://awesome-github-stats.azurewebsites.net/user-stats/1ramkrishnan?cardType=level&theme=github-dark&fontFamily=&preferLogin=false" alt="1ramkrishnan's GitHub Stats">
      </a>
    </div>
  </section>

  <!-- CERTIFICATIONS -->

  <section class="rk-section">
    <div class="rk-sh">
      <span class="rk-sh-label">certifications</span>
      <span class="rk-sh-line"></span>
    </div>
    <div class="rk-cert-grid">
      <a class="rk-cert" href="https://drive.google.com/file/d/1-ArkycQZgtb7_4Jw-Vuw6bB8QLHb6Or2/view">
        <img src="https://github.com/1ramkrishnan/1Ramkrishnan.github.io/raw/master/images/mean.png" alt="MEAN Stack">
        <div class="rk-cert-text">
          <div class="rk-cert-name">MEAN Stack</div>
          <div class="rk-cert-type">Full-stack Development</div>
        </div>
      </a>
      <a class="rk-cert" href="https://drive.google.com/file/d/1-X6IL5UW_Asf6ra6_lbA0K0_W29xNbjS/view">
        <img src="https://github.com/1ramkrishnan/1Ramkrishnan.github.io/raw/master/images/aspnet.png" alt="ASP.NET">
        <div class="rk-cert-text">
          <div class="rk-cert-name">ASP.NET</div>
          <div class="rk-cert-type">Microsoft Web Framework</div>
        </div>
      </a>
      <a class="rk-cert" href="https://drive.google.com/file/d/1-EHClNZ8j6YAiBGMnvyKDqPVTUydGBlQ/view">
        <img src="https://i0.wp.com/www.msicertified.com/wp-content/uploads/2021/10/PMEC.png?resize=150,150&ssl=1" alt="PM Essentials">
        <div class="rk-cert-text">
          <div class="rk-cert-name">PM Essentials</div>
          <div class="rk-cert-type">Project Management</div>
        </div>
      </a>
      <a class="rk-cert" href="https://drive.google.com/file/d/1pW2_VcX14IB5j_13cmO8lE0toykxCAGS/view">
        <img src="https://raw.githubusercontent.com/1ramkrishnan/1Ramkrishnan.github.io/master/images/lsswb150.png" alt="Lean Six Sigma">
        <div class="rk-cert-text">
          <div class="rk-cert-name">Lean Six Sigma White Belt</div>
          <div class="rk-cert-type">Process Excellence</div>
        </div>
      </a>
      <a class="rk-cert" href="https://www.credly.com/badges/5af788da-a8b8-4315-bab3-145b4129537b/public_url">
        <img src="https://images.credly.com/size/680x680/images/b870667f-00a3-48d7-b988-9c02b441b883/image.png" alt="AWS Well-Architected">
        <div class="rk-cert-text">
          <div class="rk-cert-name">Well-Architected Proficient</div>
          <div class="rk-cert-type">AWS · Credly</div>
        </div>
      </a>
      <a class="rk-cert" href="https://www.credly.com/badges/3f34cc17-619e-4feb-8aff-4ead1b2e50ba/public_url">
        <img src="https://images.credly.com/images/8f006312-3154-45bf-a845-4a043641e83c/blob" alt="AWS Technical Accredited">
        <div class="rk-cert-text">
          <div class="rk-cert-name">AWS Technical Accredited</div>
          <div class="rk-cert-type">AWS Partner · Credly</div>
        </div>
      </a>
    </div>
  </section>

  <!-- FOOTER -->

  <footer class="rk-footer">
    <p class="rk-quote">"you will find your purpose where you find <em>your happiness</em>" ✌️</p>
    <span class="rk-footer-sig">rklab · 2026</span>
  </footer>

</div>