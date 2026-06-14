-----

## layout: null

<!DOCTYPE html>

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Ramkrishnan Thevar — Fintech · Capital Markets · Software Development">
  <meta property="og:title" content="[rk] · Ramkrishnan Thevar">
  <meta property="og:description" content="Technology Manager · Fintech · Self-hoster">
  <meta property="og:url" content="https://1ramkrishnan.github.io">
  <meta name="theme-color" content="#0f1115">
  <title>[rk] | Ramkrishnan Thevar</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:ital,wght@0,400;0,500;0,600;1,400&family=IBM+Plex+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

```
:root {
  --green: #30e17d;
  --bg: #0f1115;
  --surface: rgba(255,255,255,0.025);
  --border: rgba(255,255,255,0.07);
  --text: #c8d3e0;
  --muted: #64748b;
  --dim: #475569;
  --heading: #f0f4f8;
  --mono: 'IBM Plex Mono', monospace;
  --sans: 'IBM Plex Sans', sans-serif;
}

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--sans);
  min-height: 100vh;
  -webkit-font-smoothing: antialiased;
}

/* grid bg */
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

.wrap {
  position: relative;
  z-index: 1;
  max-width: 860px;
  margin: 0 auto;
  padding: 0 1.5rem 5rem;
}

/* ── NAV ── */
nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.4rem 0 1.3rem;
  border-bottom: 1px solid var(--border);
  margin-bottom: 3.5rem;
}

.nav-logo {
  font-family: var(--mono);
  font-size: 14px;
  font-weight: 600;
  color: var(--green);
  text-decoration: none;
  letter-spacing: 0.04em;
}

.nav-links {
  display: flex;
  gap: 1.5rem;
  list-style: none;
}

.nav-links a {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--dim);
  text-decoration: none;
  letter-spacing: 0.07em;
  text-transform: uppercase;
  transition: color 0.15s;
}
.nav-links a:hover { color: var(--green); }

/* ── HERO ── */
.hero {
  display: grid;
  grid-template-columns: 1fr auto;
  align-items: flex-start;
  gap: 2.5rem;
  padding-bottom: 3rem;
  border-bottom: 1px solid var(--border);
}

.status-pill {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  font-family: var(--mono);
  font-size: 10px;
  color: var(--green);
  border: 1px solid rgba(48,225,125,0.2);
  background: rgba(48,225,125,0.05);
  padding: 3px 11px 3px 9px;
  border-radius: 20px;
  margin-bottom: 1.1rem;
  letter-spacing: 0.04em;
}

.dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--green);
  flex-shrink: 0;
  animation: pulse 2.2s ease-in-out infinite;
}
@keyframes pulse { 0%,100%{opacity:1;}50%{opacity:0.25;} }

.eyebrow {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--green);
  letter-spacing: 0.12em;
  text-transform: uppercase;
  margin-bottom: 0.9rem;
  display: flex;
  align-items: center;
  gap: 8px;
}
.eyebrow::before {
  content: '';
  width: 18px; height: 1px;
  background: var(--green);
  flex-shrink: 0;
}

h1 {
  font-family: var(--sans);
  font-size: clamp(2.1rem, 5.5vw, 3.6rem);
  font-weight: 700;
  line-height: 1.05;
  letter-spacing: -0.03em;
  color: var(--heading);
  margin-bottom: 0.5rem;
}
h1 em { font-style: normal; color: var(--green); }

.subtitle {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--dim);
  margin-bottom: 1.4rem;
  letter-spacing: 0.04em;
}
.subtitle span { color: var(--muted); }

.bio {
  font-size: 14.5px;
  line-height: 1.8;
  color: #94a3b8;
  max-width: 520px;
}
.bio strong { color: #cbd5e1; font-weight: 600; }

/* ── MONOGRAM BADGE ── */
.badge {
  width: 82px; height: 82px;
  border-radius: 14px;
  border: 1px solid rgba(48,225,125,0.2);
  background: rgba(48,225,125,0.04);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  gap: 3px;
}
.badge .initials {
  font-family: var(--mono);
  font-size: 24px;
  font-weight: 600;
  color: var(--green);
  line-height: 1;
  letter-spacing: -0.04em;
}
.badge .badge-sub {
  font-family: var(--mono);
  font-size: 8px;
  color: var(--green);
  opacity: 0.4;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}

/* ── LINK PILLS ── */
.links {
  display: flex;
  flex-wrap: wrap;
  gap: 7px;
  margin-top: 1.6rem;
}

a.pill {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--muted);
  text-decoration: none;
  padding: 6px 13px;
  border: 1px solid var(--border);
  border-radius: 6px;
  background: var(--surface);
  transition: all 0.15s;
  letter-spacing: 0.02em;
}
a.pill:hover {
  color: var(--green);
  border-color: rgba(48,225,125,0.3);
  background: rgba(48,225,125,0.05);
}
a.pill.primary {
  color: var(--green);
  border-color: rgba(48,225,125,0.3);
  background: rgba(48,225,125,0.07);
}
a.pill.primary:hover {
  background: rgba(48,225,125,0.13);
}

/* ── SECTION HEADER ── */
section { margin-top: 2.75rem; }

.sh {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 1.1rem;
}
.sh-label {
  font-family: var(--mono);
  font-size: 10px;
  color: var(--green);
  letter-spacing: 0.14em;
  text-transform: uppercase;
  white-space: nowrap;
}
.sh-line {
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, rgba(48,225,125,0.2) 0%, transparent 100%);
}

/* ── PROJECTS ── */
.proj-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
  gap: 9px;
}

a.proj {
  display: block;
  text-decoration: none;
  padding: 0.9rem 1rem;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 10px;
  transition: all 0.15s;
  position: relative;
  overflow: hidden;
  color: inherit;
}
a.proj::after {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1.5px;
  background: transparent;
  transition: background 0.15s;
}
a.proj:hover {
  border-color: rgba(48,225,125,0.25);
  background: rgba(48,225,125,0.04);
  transform: translateY(-1px);
}
a.proj:hover::after {
  background: linear-gradient(90deg, transparent, rgba(48,225,125,0.55), transparent);
}

.proj-name {
  font-size: 13px;
  font-weight: 600;
  color: #e2e8f0;
  margin-bottom: 4px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.proj-arrow { color: var(--green); opacity: 0.55; font-size: 11px; }
.proj-desc {
  font-family: var(--mono);
  font-size: 10.5px;
  color: var(--dim);
  line-height: 1.5;
}

/* ── GITHUB STATS ── */
.stats-wrap {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 1.1rem;
  display: flex;
  justify-content: center;
}
.stats-wrap img {
  border-radius: 6px;
  max-width: 100%;
  display: block;
}

/* ── CERTS ── */
.cert-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 8px;
}

a.cert {
  display: flex;
  align-items: center;
  gap: 11px;
  text-decoration: none;
  padding: 9px 13px;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  transition: all 0.15s;
  color: inherit;
}
a.cert:hover {
  border-color: rgba(48,225,125,0.22);
  background: rgba(48,225,125,0.04);
}
a.cert img {
  width: 28px; height: 28px;
  object-fit: contain;
  border-radius: 4px;
  flex-shrink: 0;
}
.cert-name { font-size: 12px; color: #cbd5e1; font-weight: 500; }
.cert-type { font-family: var(--mono); font-size: 10px; color: var(--dim); margin-top: 2px; }

/* ── FOOTER ── */
footer {
  margin-top: 3.5rem;
  padding-top: 1.75rem;
  border-top: 1px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.quote {
  font-family: var(--mono);
  font-size: 11px;
  color: #2d3748;
  font-style: italic;
  letter-spacing: 0.02em;
}
.quote em { font-style: normal; color: var(--green); opacity: 0.6; }

.footer-sig {
  font-family: var(--mono);
  font-size: 10px;
  color: #1e293b;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

/* ── RESPONSIVE ── */
@media (max-width: 600px) {
  .hero { grid-template-columns: 1fr; }
  .badge { display: none; }
  .nav-links { display: none; }
  footer { flex-direction: column; }
}
@media (max-width: 440px) {
  .proj-grid, .cert-grid { grid-template-columns: 1fr; }
}
```

  </style>
</head>
<body>
<div class="wrap">

  <!-- NAV -->

  <nav>
    <a class="nav-logo" href="/">[ rk ]</a>
    <ul class="nav-links">
      <li><a href="https://rklab.co.in">rkLaB</a></li>
      <li><a href="https://status.rklab.co.in">status</a></li>
      <li><a href="http://cloud.rklab.co.in/s/rkresume">résumé</a></li>
    </ul>
  </nav>

  <!-- HERO -->

  <div class="hero">
    <div>
      <div class="status-pill"><span class="dot"></span>online · fintech · 13 yrs · homelab open source</div>
      <div class="eyebrow">Technology Manager</div>
      <h1>Ramkrishnan<br><em>Thevar.</em></h1>
      <p class="subtitle">// technology manager · capital markets · <span>self-hoster</span></p>
      <p class="bio">
        With over <strong>13 years in fintech</strong>, I specialise in capital markets, software development, and project management.
        Outside work, I tinker with <strong>Raspberry Pi</strong>, self-host everything I can, and stay current on trends through podcasts.
      </p>
      <div class="links">
        <a class="pill primary" href="http://cloud.rklab.co.in/s/rkresume">résumé ↗</a>
        <a class="pill" href="http://send.rklab.co.in">share files</a>
        <a class="pill" href="https://rklab.co.in">rklab.co.in ↗</a>
        <a class="pill" href="https://chessarena.com/profile/750754">♟ chess</a>
        <a class="pill" href="https://status.rklab.co.in">● homelab status</a>
        <a class="pill" href="https://cloud.rklab.co.in/s/resumepodcast" title="Listen to résumé">🎙</a>
      </div>
    </div>
    <div class="badge">
      <span class="initials">rk</span>
      <span class="badge-sub">rkLaB</span>
    </div>
  </div>

  <!-- PROJECTS -->

  <section>
    <div class="sh"><span class="sh-label">projects</span><span class="sh-line"></span></div>
    <div class="proj-grid">
      <a class="proj" href="https://carconnect.rklab.co.in">
        <div class="proj-name">CarConnect — QR Gen <span class="proj-arrow">↗</span></div>
        <div class="proj-desc">QR-based vehicle contact system</div>
      </a>
      <a class="proj" href="https://rklab.co.in/ai">
        <div class="proj-name">SensAI <span class="proj-arrow">↗</span></div>
        <div class="proj-desc">Self-hosted AI assistant on homelab</div>
      </a>
      <a class="proj" href="https://rklab.co.in/">
        <div class="proj-name">rkLaB v2 <span class="proj-arrow">↗</span></div>
        <div class="proj-desc">Personal self-hosted infrastructure</div>
      </a>
      <a class="proj" href="https://www.linkedin.com/pulse/self-hosting-freak-ramkrishnan-thevar">
        <div class="proj-name">Home Automation <span class="proj-arrow">↗</span></div>
        <div class="proj-desc">Self-hosting journey writeup on LinkedIn</div>
      </a>
    </div>
  </section>

  <!-- GITHUB STATS -->

  <section>
    <div class="sh"><span class="sh-label">github stats</span><span class="sh-line"></span></div>
    <div class="stats-wrap">
      <a href="https://awesome-github-stats.azurewebsites.net/index.html??cardType=level&theme=github-dark&fontFamily=&preferLogin=false">
        <img src="https://awesome-github-stats.azurewebsites.net/user-stats/1ramkrishnan?cardType=level&theme=github-dark&fontFamily=&preferLogin=false" alt="1ramkrishnan's GitHub Stats">
      </a>
    </div>
  </section>

  <!-- CERTIFICATIONS -->

  <section>
    <div class="sh"><span class="sh-label">certifications</span><span class="sh-line"></span></div>
    <div class="cert-grid">
      <a class="cert" href="https://drive.google.com/file/d/1-ArkycQZgtb7_4Jw-Vuw6bB8QLHb6Or2/view">
        <img src="https://github.com/1ramkrishnan/1Ramkrishnan.github.io/raw/master/images/mean.png" alt="MEAN Stack">
        <div><div class="cert-name">MEAN Stack</div><div class="cert-type">Full-stack Development</div></div>
      </a>
      <a class="cert" href="https://drive.google.com/file/d/1-X6IL5UW_Asf6ra6_lbA0K0_W29xNbjS/view">
        <img src="https://github.com/1ramkrishnan/1Ramkrishnan.github.io/raw/master/images/aspnet.png" alt="ASP.NET">
        <div><div class="cert-name">ASP.NET</div><div class="cert-type">Microsoft Web Framework</div></div>
      </a>
      <a class="cert" href="https://drive.google.com/file/d/1-EHClNZ8j6YAiBGMnvyKDqPVTUydGBlQ/view">
        <img src="https://i0.wp.com/www.msicertified.com/wp-content/uploads/2021/10/PMEC.png?resize=150,150&ssl=1" alt="PM Essentials">
        <div><div class="cert-name">PM Essentials</div><div class="cert-type">Project Management</div></div>
      </a>
      <a class="cert" href="https://drive.google.com/file/d/1pW2_VcX14IB5j_13cmO8lE0toykxCAGS/view">
        <img src="https://raw.githubusercontent.com/1ramkrishnan/1Ramkrishnan.github.io/master/images/lsswb150.png" alt="Lean Six Sigma">
        <div><div class="cert-name">Lean Six Sigma White Belt</div><div class="cert-type">Process Excellence</div></div>
      </a>
      <a class="cert" href="https://www.credly.com/badges/5af788da-a8b8-4315-bab3-145b4129537b/public_url">
        <img src="https://images.credly.com/size/680x680/images/b870667f-00a3-48d7-b988-9c02b441b883/image.png" alt="AWS Well-Architected">
        <div><div class="cert-name">Well-Architected Proficient</div><div class="cert-type">AWS · Credly</div></div>
      </a>
      <a class="cert" href="https://www.credly.com/badges/3f34cc17-619e-4feb-8aff-4ead1b2e50ba/public_url">
        <img src="https://images.credly.com/images/8f006312-3154-45bf-a845-4a043641e83c/blob" alt="AWS Partner Technical">
        <div><div class="cert-name">AWS Technical Accredited</div><div class="cert-type">AWS Partner · Credly</div></div>
      </a>
    </div>
  </section>

  <!-- FOOTER -->

  <footer>
    <p class="quote">"you will find your purpose where you find <em>your happiness</em>" ✌️</p>
    <span class="footer-sig">rklab · 2026</span>
  </footer>

</div>
</body>
</html>