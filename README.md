<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mukherjee Legal Counsel | Advocate Punyabrata Mukherjee</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,400;1,600&family=Josefin+Sans:wght@300;400;600&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --navy: #0d1b2a;
      --navy-mid: #162236;
      --navy-light: #1e3050;
      --gold: #c9a84c;
      --gold-light: #e2c47a;
      --cream: #f5f0e8;
      --cream-dark: #ede6d8;
      --text-dark: #1a1a2e;
      --text-mid: #3a3a5c;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Josefin Sans', sans-serif;
      background: var(--navy);
      color: var(--cream);
      overflow-x: hidden;
    }

    /* ─── DISCLAIMER MODAL ─── */
    #disclaimer-overlay {
      position: fixed; inset: 0; z-index: 9999;
      background: rgba(10,16,26,0.97);
      display: flex; align-items: center; justify-content: center;
      padding: 20px;
      animation: fadeIn 0.5s ease;
    }
    #disclaimer-box {
      background: var(--navy-mid);
      border: 1px solid var(--gold);
      max-width: 780px; width: 100%;
      max-height: 90vh;
      overflow-y: auto;
      padding: 48px 44px;
      position: relative;
    }
    #disclaimer-box::before {
      content: '';
      position: absolute; top: 8px; left: 8px; right: 8px; bottom: 8px;
      border: 1px solid rgba(201,168,76,0.2);
      pointer-events: none;
    }
    .disc-emblem {
      text-align: center;
      margin-bottom: 24px;
    }
    .disc-emblem .scales {
      font-size: 38px;
      color: var(--gold);
      display: block;
    }
    .disc-emblem h2 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 22px;
      font-weight: 600;
      letter-spacing: 3px;
      color: var(--gold);
      text-transform: uppercase;
      margin-top: 8px;
    }
    .disc-rule {
      width: 80px; height: 1px;
      background: var(--gold);
      margin: 16px auto;
    }
    .disc-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 28px;
      font-weight: 700;
      color: var(--cream);
      text-align: center;
      margin-bottom: 24px;
    }
    .disc-body {
      font-size: 13px;
      line-height: 1.9;
      color: rgba(245,240,232,0.82);
      margin-bottom: 20px;
    }
    .disc-body ul {
      list-style: none;
      padding: 0;
    }
    .disc-body ul li {
      padding: 6px 0 6px 20px;
      position: relative;
      border-bottom: 1px solid rgba(201,168,76,0.1);
    }
    .disc-body ul li::before {
      content: '›';
      position: absolute; left: 0;
      color: var(--gold);
      font-size: 16px;
    }
    .disc-checkbox-row {
      display: flex; align-items: flex-start; gap: 12px;
      margin: 24px 0 28px;
      padding: 16px;
      background: rgba(201,168,76,0.06);
      border: 1px solid rgba(201,168,76,0.2);
    }
    .disc-checkbox-row input[type="checkbox"] {
      width: 18px; height: 18px;
      accent-color: var(--gold);
      flex-shrink: 0;
      margin-top: 2px;
      cursor: pointer;
    }
    .disc-checkbox-row label {
      font-size: 13px;
      color: var(--cream);
      cursor: pointer;
      line-height: 1.6;
    }
    #agree-btn {
      display: block; width: 100%;
      padding: 16px;
      background: var(--gold);
      color: var(--navy);
      border: none;
      font-family: 'Josefin Sans', sans-serif;
      font-size: 13px;
      font-weight: 600;
      letter-spacing: 3px;
      text-transform: uppercase;
      cursor: pointer;
      transition: background 0.3s;
      opacity: 0.4;
      pointer-events: none;
    }
    #agree-btn.active {
      opacity: 1;
      pointer-events: auto;
    }
    #agree-btn.active:hover { background: var(--gold-light); }

    /* ─── NAVBAR ─── */
    nav {
      position: fixed; top: 0; left: 0; right: 0;
      z-index: 1000;
      background: rgba(13,27,42,0.96);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(201,168,76,0.25);
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 48px;
      height: 70px;
    }
    .nav-brand {
      font-family: 'Cormorant Garamond', serif;
      font-size: 20px;
      font-weight: 600;
      color: var(--gold);
      text-decoration: none;
      letter-spacing: 1px;
    }
    .nav-links {
      display: flex; gap: 36px; list-style: none;
    }
    .nav-links a {
      color: rgba(245,240,232,0.75);
      text-decoration: none;
      font-size: 11px;
      letter-spacing: 2.5px;
      text-transform: uppercase;
      transition: color 0.3s;
    }
    .nav-links a:hover { color: var(--gold); }
    .nav-cta {
      background: transparent;
      border: 1px solid var(--gold);
      color: var(--gold) !important;
      padding: 8px 20px;
    }
    .nav-cta:hover { background: var(--gold) !important; color: var(--navy) !important; }

    /* ─── HERO ─── */
    #hero {
      min-height: 100vh;
      display: flex; align-items: center; justify-content: center;
      position: relative;
      overflow: hidden;
      background: var(--navy);
      padding: 100px 40px 60px;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background:
        radial-gradient(ellipse at 20% 50%, rgba(201,168,76,0.06) 0%, transparent 60%),
        radial-gradient(ellipse at 80% 20%, rgba(30,48,80,0.8) 0%, transparent 50%);
    }
    .hero-lines {
      position: absolute; inset: 0;
      background-image:
        linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
      background-size: 60px 60px;
    }
    .hero-content {
      position: relative; z-index: 2;
      text-align: center;
      max-width: 900px;
    }
    .hero-eyebrow {
      font-size: 11px;
      letter-spacing: 5px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 24px;
      animation: fadeUp 0.8s 0.2s both;
    }
    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(44px, 7vw, 88px);
      font-weight: 300;
      line-height: 1.08;
      color: var(--cream);
      margin-bottom: 12px;
      animation: fadeUp 0.8s 0.4s both;
    }
    .hero-title em {
      font-style: italic;
      color: var(--gold);
    }
    .hero-subtitle {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(16px, 2.5vw, 22px);
      font-weight: 400;
      color: rgba(245,240,232,0.65);
      margin-bottom: 40px;
      animation: fadeUp 0.8s 0.6s both;
    }
    .hero-divider {
      width: 60px; height: 1px;
      background: var(--gold);
      margin: 28px auto;
      animation: expandWidth 1s 0.8s both;
    }
    .hero-desc {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(16px, 2vw, 19px);
      line-height: 1.8;
      color: rgba(245,240,232,0.8);
      max-width: 680px;
      margin: 0 auto 48px;
      animation: fadeUp 0.8s 0.8s both;
    }
    .hero-btns {
      display: flex; gap: 16px; justify-content: center; flex-wrap: wrap;
      animation: fadeUp 0.8s 1s both;
    }
    .btn-primary {
      padding: 16px 40px;
      background: var(--gold);
      color: var(--navy);
      text-decoration: none;
      font-size: 11px;
      letter-spacing: 3px;
      text-transform: uppercase;
      font-weight: 600;
      transition: all 0.3s;
    }
    .btn-primary:hover { background: var(--gold-light); }
    .btn-outline {
      padding: 16px 40px;
      border: 1px solid rgba(201,168,76,0.5);
      color: var(--gold);
      text-decoration: none;
      font-size: 11px;
      letter-spacing: 3px;
      text-transform: uppercase;
      transition: all 0.3s;
    }
    .btn-outline:hover { border-color: var(--gold); background: rgba(201,168,76,0.08); }

    /* ─── STATS BAR ─── */
    .stats-bar {
      background: var(--gold);
      padding: 28px 48px;
      display: flex; justify-content: center; gap: 80px; flex-wrap: wrap;
    }
    .stat-item { text-align: center; }
    .stat-num {
      font-family: 'Cormorant Garamond', serif;
      font-size: 36px;
      font-weight: 700;
      color: var(--navy);
      line-height: 1;
    }
    .stat-label {
      font-size: 10px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: rgba(13,27,42,0.7);
      margin-top: 4px;
    }

    /* ─── SECTIONS ─── */
    section { padding: 100px 48px; }

    .section-eyebrow {
      font-size: 10px;
      letter-spacing: 5px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 12px;
    }
    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(32px, 4vw, 52px);
      font-weight: 300;
      color: var(--cream);
      line-height: 1.2;
      margin-bottom: 16px;
    }
    .section-rule {
      width: 50px; height: 1px;
      background: var(--gold);
      margin-bottom: 32px;
    }
    .section-body {
      font-family: 'Cormorant Garamond', serif;
      font-size: 18px;
      line-height: 1.85;
      color: rgba(245,240,232,0.78);
      max-width: 680px;
    }

    /* ─── PRACTICE AREAS ─── */
    #practice { background: var(--navy-mid); }
    .practice-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 1px;
      background: rgba(201,168,76,0.15);
      margin-top: 60px;
    }
    .practice-card {
      background: var(--navy);
      padding: 36px 32px;
      position: relative;
      overflow: hidden;
      transition: background 0.3s;
      cursor: default;
    }
    .practice-card::after {
      content: '';
      position: absolute; bottom: 0; left: 0;
      width: 0; height: 2px;
      background: var(--gold);
      transition: width 0.4s ease;
    }
    .practice-card:hover { background: var(--navy-light); }
    .practice-card:hover::after { width: 100%; }
    .pc-icon {
      font-size: 28px;
      margin-bottom: 16px;
      display: block;
    }
    .pc-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 22px;
      font-weight: 600;
      color: var(--gold);
      margin-bottom: 12px;
    }
    .pc-body {
      font-size: 13px;
      line-height: 1.8;
      color: rgba(245,240,232,0.65);
    }
    .pc-list {
      list-style: none;
      margin-top: 12px;
    }
    .pc-list li {
      font-size: 12px;
      color: rgba(245,240,232,0.55);
      padding: 3px 0;
      padding-left: 14px;
      position: relative;
    }
    .pc-list li::before {
      content: '—';
      position: absolute; left: 0;
      color: var(--gold);
    }

    /* ─── CTA STRIP ─── */
    #cta-strip {
      background:
        linear-gradient(135deg, var(--navy-light) 0%, var(--navy-mid) 100%);
      border-top: 1px solid rgba(201,168,76,0.2);
      border-bottom: 1px solid rgba(201,168,76,0.2);
      padding: 80px 48px;
      text-align: center;
    }
    .cta-heading {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(28px, 4vw, 48px);
      font-weight: 300;
      color: var(--cream);
      margin-bottom: 12px;
    }
    .cta-sub {
      font-size: 13px;
      letter-spacing: 2px;
      color: rgba(245,240,232,0.55);
      text-transform: uppercase;
      margin-bottom: 36px;
    }
    .cta-phone {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(32px, 5vw, 56px);
      font-weight: 600;
      color: var(--gold);
      text-decoration: none;
      display: block;
      margin-bottom: 8px;
    }
    .cta-hours {
      font-size: 12px;
      letter-spacing: 2px;
      color: rgba(245,240,232,0.5);
      text-transform: uppercase;
    }

    /* ─── CONTACT ─── */
    #contact { background: var(--navy); }
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 80px;
      margin-top: 60px;
    }
    .contact-detail {
      display: flex;
      gap: 16px;
      margin-bottom: 32px;
      align-items: flex-start;
    }
    .cd-icon {
      width: 40px; height: 40px;
      border: 1px solid rgba(201,168,76,0.4);
      display: flex; align-items: center; justify-content: center;
      color: var(--gold);
      font-size: 16px;
      flex-shrink: 0;
    }
    .cd-content h4 {
      font-size: 10px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 6px;
    }
    .cd-content p, .cd-content a {
      font-family: 'Cormorant Garamond', serif;
      font-size: 17px;
      color: rgba(245,240,232,0.8);
      text-decoration: none;
      line-height: 1.6;
    }
    .cd-content a:hover { color: var(--gold); }
    .contact-form-note {
      background: rgba(201,168,76,0.06);
      border: 1px solid rgba(201,168,76,0.2);
      padding: 40px;
    }
    .contact-form-note h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 26px;
      font-weight: 600;
      color: var(--cream);
      margin-bottom: 16px;
    }
    .contact-form-note p {
      font-family: 'Cormorant Garamond', serif;
      font-size: 17px;
      line-height: 1.8;
      color: rgba(245,240,232,0.7);
      margin-bottom: 28px;
    }

    /* ─── FOOTER ─── */
    footer {
      background: #080f18;
      border-top: 1px solid rgba(201,168,76,0.2);
      padding: 48px;
      text-align: center;
    }
    .footer-brand {
      font-family: 'Cormorant Garamond', serif;
      font-size: 22px;
      color: var(--gold);
      margin-bottom: 12px;
    }
    .footer-disc {
      font-size: 11px;
      color: rgba(245,240,232,0.35);
      line-height: 1.8;
      max-width: 700px;
      margin: 0 auto 24px;
    }
    .footer-copy {
      font-size: 11px;
      letter-spacing: 2px;
      color: rgba(245,240,232,0.25);
      text-transform: uppercase;
    }

    /* ─── MOBILE NAV HAMBURGER ─── */
    .hamburger {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      background: none;
      border: none;
      padding: 4px;
    }
    .hamburger span {
      display: block;
      width: 24px; height: 1px;
      background: var(--gold);
    }

    /* ─── ANIMATIONS ─── */
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes expandWidth {
      from { width: 0; } to { width: 60px; }
    }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 768px) {
      nav { padding: 0 24px; }
      .nav-links { display: none; }
      .hamburger { display: flex; }
      section { padding: 70px 24px; }
      .stats-bar { gap: 40px; padding: 24px; }
      .contact-grid { grid-template-columns: 1fr; gap: 40px; }
      .hero-btns { flex-direction: column; align-items: center; }
      #disclaimer-box { padding: 32px 24px; }
    }
  </style>
</head>
<body>

<!-- ═══════════════════════════════════════════
     DISCLAIMER MODAL
════════════════════════════════════════════ -->
<div id="disclaimer-overlay">
  <div id="disclaimer-box">
    <div class="disc-emblem">
      <span class="scales">⚖</span>
      <h2>Mukherjee Legal Counsel</h2>
    </div>
    <div class="disc-rule"></div>
    <h1 class="disc-title">Legal Disclaimer</h1>

    <div class="disc-body">
      <p style="margin-bottom:16px;">Under the rules of the Bar Council of India, advocates are prohibited from soliciting work or advertising their services. By accessing this website, you acknowledge and confirm the following:</p>
      <ul>
        <li>You are seeking information about Advocate Punyabrata Mukherjee/Mukhopadhyay voluntarily and without any solicitation, advertisement, or inducement.</li>
        <li>The information contained on this website is provided solely for general informational purposes regarding the professional practice and areas of work of Advocate Punyabrata Mukherjee/Mukhopadhyay.</li>
        <li>The content available on this website is not intended to constitute legal advice and should not be relied upon as such.</li>
        <li>Accessing this website or contacting the advocate through this website does not create an advocate-client relationship.</li>
        <li>Advocate Punyabrata Mukherjee/Mukhopadhyay shall not be responsible for any consequences arising from reliance on the information provided on this website. Independent legal advice should be sought for specific legal matters.</li>
        <li>The contents of this website are the intellectual property of Advocate Punyabrata Mukherjee/Mukhopadhyay.</li>
      </ul>
    </div>

    <div class="disc-checkbox-row">
      <input type="checkbox" id="disc-agree" onchange="toggleBtn(this)"/>
      <label for="disc-agree">I have read and understood the above disclaimer. I wish to proceed to the website voluntarily, without any solicitation or inducement.</label>
    </div>

    <button id="agree-btn" onclick="enterSite()">I Agree &amp; Proceed →</button>
  </div>
</div>


<!-- ═══════════════════════════════════════════
     NAVIGATION
════════════════════════════════════════════ -->
<nav>
  <a href="#hero" class="nav-brand">Mukherjee Legal Counsel</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#practice">Practice Areas</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="tel:+919804102281" class="nav-cta">Call Now</a></li>
  </ul>
  <button class="hamburger" onclick="toggleMobileMenu(this)">
    <span></span><span></span><span></span>
  </button>
</nav>


<!-- ═══════════════════════════════════════════
     HERO
════════════════════════════════════════════ -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-lines"></div>
  <div class="hero-content">
    <p class="hero-eyebrow">Established 2003 · Calcutta High Court &amp; Alipore Judge's Court</p>
    <h1 class="hero-title">
      Advocate<br/>
      <em>Punyabrata Mukherjee</em><br/>
      Mukhopadhyay
    </h1>
    <div class="hero-divider"></div>
    <p class="hero-desc">
      Welcome to the law offices of Punyabrata Mukherjee/Mukhopadhyay, providing legal counsel since 2003, with regular practice before the Alipore Judges' Court and other Courts. Specialising in Civil, Criminal, and Property Law, with a strong focus on property transactions, documentation, and litigation.
    </p>
    <div class="hero-btns">
      <a href="#practice" class="btn-primary">View Practice Areas</a>
      <a href="#contact" class="btn-outline">Get in Touch</a>
    </div>
  </div>
</section>


<!-- ═══════════════════════════════════════════
     STATS BAR
════════════════════════════════════════════ -->
<div class="stats-bar">
  <div class="stat-item">
    <div class="stat-num">20+</div>
    <div class="stat-label">Years of Practice</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">2</div>
    <div class="stat-label">Court Jurisdictions</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">8+</div>
    <div class="stat-label">Practice Areas</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">2003</div>
    <div class="stat-label">Year Established</div>
  </div>
</div>


<!-- ═══════════════════════════════════════════
     ABOUT
════════════════════════════════════════════ -->
<section id="about" style="background: var(--navy-mid);">
  <div style="max-width:1100px; margin:0 auto;">
    <p class="section-eyebrow">About the Advocate</p>
    <h2 class="section-title">A Legacy of Legal<br/><em style="font-style:italic; color:var(--gold);">Counsel &amp; Integrity</em></h2>
    <div class="section-rule"></div>
    <p class="section-body">
      Advocate Punyabrata Mukherjee/Mukhopadhyay has been providing legal services since 2003, enrolled under the Bar Council of West Bengal. With chambers in Kolkata, he regularly practices before the Alipore Judge's Court and the Calcut
