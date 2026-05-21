<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Ram Kumar | Personal Trainer – Pondicherry</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:ital,wght@0,300;0,400;0,600;0,700;1,300&family=Barlow+Condensed:wght@400;600;700&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --black: #05070a;      /* Deep Midnight Black */
      --dark: #0c1017;       /* Dark Charcoal Slate */
      --card: #131924;       /* Slate Grey Blue for cards */
      --accent: #ff6600;     /* Electric Orange */
      --accent2: #e04b00;    /* Darker Orange for gradients/hover */
      --secondary: #00d2ff;  /* Neon Cyan Blue for subtle links/highlights */
      --text: #ffffff;       /* Pure White */
      --muted: #8fa0b5;      /* Cool Steel Grey for secondary text */
      --border: #1e2633;     /* Subtle Blue-Grey dark border */
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--black);
      color: var(--text);
      font-family: 'Barlow', sans-serif;
      font-weight: 300;
      overflow-x: hidden;
    }

    /* ─── NOISE OVERLAY ─── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 9999;
      opacity: 0.2;
    }

    /* ─── NAV ─── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.2rem 4rem;
      background: rgba(5, 7, 10, 0.9);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.6rem;
      letter-spacing: 3px;
      color: var(--accent);
    }

    .nav-links {
      display: flex;
      gap: 2.5rem;
      list-style: none;
    }

    .nav-links a {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.85rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--muted);
      text-decoration: none;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--secondary); }

    /* ─── HERO ─── */
    #hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: center;
      padding: 8rem 4rem 4rem;
      position: relative;
      overflow: hidden;
    }

    .hero-bg {
      position: absolute;
      inset: 0;
      background:
        radial-gradient(ellipse 60% 80% at 80% 50%, rgba(255, 102, 0, 0.1) 0%, transparent 70%),
        radial-gradient(ellipse 40% 60% at 20% 80%, rgba(0, 210, 255, 0.08) 0%, transparent 60%);
    }

    .hero-lines {
      position: absolute;
      right: 0; top: 0; bottom: 0;
      width: 50%;
      background: repeating-linear-gradient(
        90deg,
        transparent,
        transparent 60px,
        rgba(0, 210, 255, 0.02) 60px,
        rgba(0, 210, 255, 0.02) 61px
      );
    }

    .hero-content { position: relative; z-index: 2; }

    .hero-tag {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.78rem;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--secondary);
      margin-bottom: 1.2rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }

    .hero-tag::before {
      content: '';
      display: block;
      width: 30px;
      height: 1px;
      background: var(--secondary);
    }

    h1 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(5rem, 9vw, 10rem);
      line-height: 0.9;
      letter-spacing: 2px;
      margin-bottom: 1.5rem;
      color: var(--text);
    }

    h1 span { color: var(--accent); }

    .hero-sub {
      font-size: 1.1rem;
      color: var(--muted);
      line-height: 1.7;
      max-width: 420px;
      margin-bottom: 2.5rem;
    }

    .hero-cta {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.85rem 2rem;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.9rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      text-decoration: none;
      border: none;
      cursor: pointer;
      transition: all 0.25s;
    }

    .btn-primary {
      background: var(--accent);
      color: white;
      font-weight: 700;
    }

    .btn-primary:hover {
      background: var(--accent2);
      transform: translateY(-2px);
      box-shadow: 0 8px 30px rgba(255, 102, 0, 0.35);
    }

    .btn-outline {
      border: 1px solid var(--text);
      color: var(--text);
      background: transparent;
    }

    .btn-outline:hover {
      border-color: var(--secondary);
      color: var(--secondary);
    }

    /* WhatsApp btn */
    .btn-whatsapp {
      background: #25D366;
      color: #fff;
      font-weight: 700;
    }
    .btn-whatsapp:hover {
      background: #1ebe5b;
      transform: translateY(-2px);
      box-shadow: 0 8px 30px rgba(37,211,102,0.3);
    }

    .hero-stats {
      position: relative;
      z-index: 2;
      display: flex;
      flex-direction: column;
      gap: 2rem;
      padding-left: 4rem;
      border-left: 1px solid var(--border);
    }

    .stat-block { display: flex; flex-direction: column; gap: 0.3rem; }

    .stat-number {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 4.5rem;
      line-height: 1;
      color: var(--secondary);
    }

    .stat-label {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.8rem;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--muted);
    }

    .stat-divider {
      width: 40px;
      height: 1px;
      background: var(--border);
    }

    /* ─── SECTION BASE ─── */
    section { 
      padding: 6rem 4rem; 
      scroll-margin-top: 80px;
    }

    .section-label {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.75rem;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 0.8rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }

    .section-label::before {
      content: '';
      display: block;
      width: 24px;
      height: 1px;
      background: var(--accent);
    }

    h2 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(2.5rem, 5vw, 4.5rem);
      letter-spacing: 2px;
      margin-bottom: 3rem;
      line-height: 1;
      color: var(--text);
    }

    /* ─── ABOUT ─── */
    #about { background: var(--dark); }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: start;
    }

    .about-text p {
      font-size: 1.05rem;
      line-height: 1.85;
      color: var(--text);
      margin-bottom: 1.5rem;
    }

    .about-text strong { color: var(--secondary); font-weight: 600; }

    .about-info {
      display: flex;
      flex-direction: column;
      gap: 1.2rem;
    }

    .info-row {
      display: flex;
      align-items: center;
      gap: 1rem;
      padding: 1rem 1.2rem;
      background: var(--card);
      border: 1px solid var(--border);
      border-left: 3px solid var(--accent);
    }

    .info-icon { font-size: 1.3rem; }

    .info-content { display: flex; flex-direction: column; }

    .info-key {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.7rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--muted);
    }

    .info-val {
      font-size: 0.95rem;
      color: var(--text);
      font-weight: 600;
    }

    /* ─── PROGRAMS ─── */
    #programs { background: var(--black); }

    .programs-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
    }

    .program-card {
      background: var(--dark);
      padding: 2.5rem 2rem;
      position: relative;
      overflow: hidden;
      transition: background 0.3s;
      cursor: default;
    }

    .program-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
      background: var(--secondary);
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.3s;
    }

    .program-card:hover { background: #0c1824; }
    .program-card:hover::before { transform: scaleX(1); }

    .program-icon {
      font-size: 2.5rem;
      margin-bottom: 1.2rem;
      display: block;
    }

    .program-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.6rem;
      letter-spacing: 1px;
      margin-bottom: 0.8rem;
      color: var(--text);
    }

    .program-desc {
      font-size: 0.9rem;
      color: var(--muted);
      line-height: 1.7;
    }

    .program-num {
      position: absolute;
      bottom: 1.5rem;
      right: 1.5rem;
      font-family: 'Bebas Neue', sans-serif;
      font-size: 3rem;
      color: rgba(0, 210, 255, 0.08);
      line-height: 1;
    }

    /* ─── EXPERIENCE ─── */
    #experience { background: var(--dark); }

    .timeline {
      position: relative;
      max-width: 750px;
    }

    .timeline::before {
      content: '';
      position: absolute;
      left: 0;
      top: 0; bottom: 0;
      width: 1px;
      background: var(--border);
    }

    .timeline-item {
      position: relative;
      padding-left: 3rem;
      padding-bottom: 3rem;
    }

    .timeline-item::before {
      content: '';
      position: absolute;
      left: -5px;
      top: 6px;
      width: 11px;
      height: 11px;
      background: var(--accent);
      border: 2px solid var(--black);
    }

    .timeline-period {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.75rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--secondary);
      margin-bottom: 0.5rem;
    }

    .timeline-gym {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.8rem;
      letter-spacing: 1px;
      margin-bottom: 0.5rem;
      color: var(--text);
    }

    .timeline-role {
      font-size: 0.9rem;
      color: var(--muted);
    }

    /* ─── TESTIMONIALS ─── */
    #testimonials { background: var(--black); }

    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }

    .testimonial-card {
      background: var(--card);
      border: 1px solid var(--border);
      padding: 2rem;
      position: relative;
      transition: border-color 0.3s, transform 0.3s;
    }

    .testimonial-card:hover {
      border-color: var(--accent);
      transform: translateY(-4px);
    }

    .quote-mark {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 5rem;
      line-height: 1;
      color: rgba(255, 102, 0, 0.15);
      margin-bottom: -1rem;
    }

    .testimonial-text {
      font-size: 0.95rem;
      line-height: 1.8;
      color: var(--text);
      margin-bottom: 1.5rem;
      font-style: italic;
    }

    .testimonial-author {
      display: flex;
      align-items: center;
      gap: 1rem;
    }

    .author-avatar {
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background: var(--accent);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.2rem;
      color: white;
      flex-shrink: 0;
    }

    .author-name {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1rem;
      letter-spacing: 1px;
      font-weight: 600;
      color: var(--text);
    }

    .author-detail {
      font-size: 0.78rem;
      color: var(--muted);
    }

    .stars {
      color: var(--secondary);
      font-size: 0.85rem;
      margin-top: 0.2rem;
    }

    /* ─── CONTACT ─── */
    #contact {
      background: var(--dark);
      text-align: center;
    }

    .contact-inner {
      max-width: 640px;
      margin: 0 auto;
    }

    .contact-desc {
      font-size: 1.05rem;
      color: var(--muted);
      line-height: 1.7;
      margin-bottom: 2.5rem;
    }

    .contact-methods {
      display: flex;
      justify-content: center;
      gap: 1.2rem;
      flex-wrap: wrap;
      margin-bottom: 3rem;
    }

    .contact-chip {
      display: flex;
      align-items: center;
      gap: 0.7rem;
      padding: 0.85rem 1.5rem;
      background: var(--card);
      border: 1px solid var(--border);
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.85rem;
      letter-spacing: 1px;
      color: var(--text);
      text-decoration: none;
      transition: all 0.25s;
    }

    .contact-chip:hover {
      border-color: var(--secondary);
      color: var(--secondary);
    }

    .whatsapp-cta {
      display: inline-flex;
      align-items: center;
      gap: 0.8rem;
      padding: 1.1rem 2.5rem;
      background: #25D366;
      color: #fff;
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.3rem;
      letter-spacing: 3px;
      text-decoration: none;
      transition: all 0.25s;
      margin-bottom: 1rem;
    }

    .whatsapp-cta:hover {
      background: #1ebe5b;
      transform: translateY(-3px);
      box-shadow: 0 12px 40px rgba(37,211,102,0.35);
    }

    .wa-note {
      font-size: 0.82rem;
      color: var(--muted);
    }

    /* ─── FOOTER ─── */
    footer {
      background: var(--black);
      border-top: 1px solid var(--border);
      padding: 2rem 4rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .footer-logo {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.3rem;
      letter-spacing: 3px;
      color: var(--accent);
    }

    .footer-copy {
      font-size: 0.8rem;
      color: var(--muted);
    }

    /* ─── SCROLL ANIMATIONS ─── */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: none;
    }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 900px) {
      nav { padding: 1.2rem 2rem; }
      .nav-links { display: none; }
      section { padding: 4rem 2rem; }
      #hero { grid-template-columns: 1fr; padding: 7rem 2rem 3rem; gap: 3rem; }
      .hero-stats { padding-left: 0; border-left: none; border-top: 1px solid var(--border); padding-top: 2rem; flex-direction: row; flex-wrap: wrap; gap: 2rem; }
      .about-grid { grid-template-columns: 1fr; gap: 3rem; }
      .programs-grid { grid-template-columns: 1fr 1fr; }
      .testimonials-grid { grid-template-columns: 1fr; }
      footer { flex-direction: column; gap: 1rem; text-align: center; }
    }

    @media (max-width: 600px) {
      h1 { font-size: 4.5rem; }
      .programs-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">RK FITNESS</div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#programs">Programs</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#testimonials">Clients</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section id="hero">
    <div class="hero-bg"></div>
    <div class="hero-lines"></div>

    <div class="hero-content reveal">
      <div class="hero-tag">Certified Personal Trainer · Pondicherry</div>
      <h1>RAM<br/><span>KUMAR</span></h1>
      <p class="hero-sub">
        10 years of transforming bodies and building discipline. 
        Weight loss · Muscle building · Functional fitness · Nutrition.
        Train smart. Live strong.
      </p>
      <div class="hero-cta">
        <a href="https://wa.me/919791264563?text=Hi%20Ram%2C%20I%20am%20interested%20in%20personal%20training." target="_blank" class="btn btn-whatsapp">
          <!-- WhatsApp Icon -->
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
          Chat on WhatsApp
        </a>
        <a href="#programs" class="btn btn-outline">View Programs</a>
      </div>
    </div>

    <div class="hero-stats reveal">
      <div class="stat-block">
        <div class="stat-number">10+</div>
        <div class="stat-label">Years Experience</div>
      </div>
      <div class="stat-divider"></div>
      <div class="stat-block">
        <div class="stat-number">3</div>
        <div class="stat-label">Gyms Worked</div>
      </div>
      <div class="stat-divider"></div>
      <div class="stat-block">
        <div class="stat-number">6</div>
        <div class="stat-label">Training Programs</div>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="section-label">About Me</div>
    <h2>Trainer. Coach.<br/>Motivator.</h2>
    <div class="about-grid">
      <div class="about-text reveal">
        <p>
          I'm <strong>Ram Kumar</strong>, a dedicated personal trainer based in Pondicherry with 
          over <strong>10 years of hands-on experience</strong> in fitness coaching. 
          My journey started at the gym floor and grew into a passion for helping people 
          unlock their true physical potential.
        </p>
        <p>
          Whether you want to shed fat, build muscle, or simply live a healthier life — 
          I create <strong>personalised training plans</strong> tailored to your body, 
          lifestyle, and goals. Every rep, every session counts.
        </p>
        <p>
          I have trained clients across all fitness levels — from absolute beginners to 
          competitive athletes — and I bring the same intensity, care, and dedication 
          to every single session.
        </p>
        <a href="https://wa.me/919791264563?text=Hi%20Ram%2C%20I%20want%20to%20start%20my%20fitness%20journey!" target="_blank" class="btn btn-primary" style="margin-top:1rem;">
          Start Your Journey
        </a>
      </div>

      <div class="about-info reveal">
        <div class="info-row">
          <span class="info-icon">👤</span>
          <div class="info-content">
            <span class="info-key">Full Name</span>
            <span class="info-val">Ram Kumar</span>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">🏋️</span>
          <div class="info-content">
            <span class="info-key">Specialisation</span>
            <span class="info-val">Personal Training / Gym Coaching</span>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">📍</span>
          <div class="info-content">
            <span class="info-key">Location</span>
            <span class="info-val">Pondicherry, India</span>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">📅</span>
          <div class="info-content">
            <span class="info-key">Experience</span>
            <span class="info-val">10+ Years in Fitness Industry</span>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">📞</span>
          <div class="info-content">
            <span class="info-key">Phone / WhatsApp</span>
            <span class="info-val">+91 97912 64563</span>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">✉️</span>
          <div class="info-content">
            <span class="info-key">Email</span>
            <span class="info-val">ramkuwait07th@gmail.com</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROGRAMS -->
  <section id="programs">
    <div class="section-label">What I Offer</div>
    <h2>Training Programs</h2>
    <div class="programs-grid reveal">

      <div class="program-card">
        <span class="program-icon">🔥</span>
        <div class="program-title">Weight Loss</div>
        <p class="program-desc">Targeted fat-burning workouts combined with nutrition strategies. Burn calories, boost metabolism, and reshape your body.</p>
        <span class="program-num">01</span>
      </div>

      <div class="program-card">
        <span class="program-icon">💪</span>
        <div class="program-title">Muscle Building</div>
        <p class="program-desc">Progressive resistance training to increase strength and size. Build lean muscle mass with structured hypertrophy plans.</p>
        <span class="program-num">02</span>
      </div>

      <div class="program-card">
        <span class="program-icon">⚡</span>
        <div class="program-title">Functional Fitness</div>
        <p class="program-desc">Real-world movement training for strength, stability, and injury prevention. Perform better in everyday life.</p>
        <span class="program-num">03</span>
      </div>

      <div class="program-card">
        <span class="program-icon">🧘</span>
        <div class="program-title">Wellness</div>
        <p class="program-desc">Holistic approach to health — mobility, flexibility, recovery, and mental well-being for a balanced lifestyle.</p>
        <span class="program-num">04</span>
      </div>

      <div class="program-card">
        <span class="program-icon">🏃‍♂️</span>
        <div class="program-title">Cardio Training</div>
        <p class="program-desc">Improve cardiovascular endurance, stamina, and heart health with structured cardio protocols tailored for you.</p>
        <span class="program-num">05</span>
      </div>

      <div class="program-card">
        <span class="program-icon">🥗</span>
        <div class="program-title">Nutrition Guidance</div>
        <p class="program-desc">Practical diet plans and nutritional coaching to fuel your training and accelerate results from inside out.</p>
        <span class="program-num">06</span>
      </div>

    </div>
  </section>

  <!-- EXPERIENCE -->
  <section id="experience">
    <div class="section-label">Career Journey</div>
    <h2>10 Years.<br/>3 Gyms. Countless<br/>Transformations.</h2>
    <div class="timeline reveal">

      <div class="timeline-item">
        <div class="timeline-period">Recent Experience</div>
        <div class="timeline-gym">SAN Fitness Studio</div>
        <div class="timeline-role">Personal Trainer &amp; Fitness Coach · Pondicherry</div>
      </div>

      <div class="timeline-item">
        <div class="timeline-period">Mid Career</div>
        <div class="timeline-gym">Next Level Fitness</div>
        <div class="timeline-role">Senior Gym Trainer &amp; Strength Coach · Pondicherry</div>
      </div>

      <div class="timeline-item">
        <div class="timeline-period">Early Career</div>
        <div class="timeline-gym">Extreme Fitness Gym</div>
        <div class="timeline-role">Gym Trainer &amp; Personal Coach · Pondicherry</div>
      </div>

    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section id="testimonials">
    <div class="section-label">Client Stories</div>
    <h2>Real Results.<br/>Real People.</h2>
    <div class="testimonials-grid">

      <!-- Client 1 -->
      <div class="testimonial-card reveal">
        <div class="quote-mark">"</div>
        <p class="testimonial-text">
          Training with Ram has completely changed my life. I lost 18 kg in 5 months 
          and feel stronger than ever. His dedication and personal attention make 
          every session worth it.
        </p>
        <div class="testimonial-author">
          <div class="author-avatar">C1</div>
          <div>
            <div class="author-name">Client Name</div>
            <div class="author-detail">Weight Loss · Pondicherry</div>
            <div class="stars">★★★★★</div>
          </div>
        </div>
      </div>

      <!-- Client 2 -->
      <div class="testimonial-card reveal">
        <div class="quote-mark">"</div>
        <p class="testimonial-text">
          I joined with zero gym experience and Ram guided me through every step. 
          His muscle building program is incredible — I gained 8 kg of muscle in 
          4 months. Highly recommend him!
        </p>
        <div class="testimonial-author">
          <div class="author-avatar">C2</div>
          <div>
            <div class="author-name">Client Name</div>
            <div class="author-detail">Muscle Building · Pondicherry</div>
            <div class="stars">★★★★★</div>
          </div>
        </div>
      </div>

      <!-- Client 3 -->
      <div class="testimonial-card reveal">
        <div class="quote-mark">"</div>
        <p class="testimonial-text">
          Ram's wellness and nutrition program helped me recover from chronic back pain 
          while getting fit. His functional fitness approach is exactly what my body needed.
        </p>
        <div class="testimonial-author">
          <div class="author-avatar">C3</div>
          <div>
            <div class="author-name">Client Name</div>
            <div class="author-detail">Wellness &amp; Nutrition · Pondicherry</div>
            <div class="stars">★★★★★</div>
          </div>
        </div>
      </div>

    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <div class="contact-inner">
      <div class="section-label" style="justify-content:center;">Get In Touch</div>
      <h2>Ready to<br/>Transform?</h2>
      <p class="contact-desc">
        Message me directly on WhatsApp to discuss your fitness goals, 
        check availability, or book your first personal training session.
        I'm based in Pondicherry and available for both gym and home sessions.
      </p>

      <!-- PRIMARY WhatsApp CTA -->
      <div style="margin-bottom:2rem;">
        <a 
          href="https://wa.me/919791264563?text=Hi%20Ram%2C%20I%20am%20interested%20in%20personal%20training.%20Can%20we%20connect%3F" 
          target="_blank" 
          class="whatsapp-cta"
        >
          <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
          Message on WhatsApp
        </a>
        <p class="wa-note">Tap to open WhatsApp chat directly · +91 97912 64563</p>
      </div>

      <!-- Other contact methods -->
      <div class="contact-methods">
        <a href="tel:+919791264563" class="contact-chip">
          📞 +91 97912 64563
        </a>
        <a href="mailto:ramkuwait07th@gmail.com" class="contact-chip">
          ✉️ ramkuwait07th@gmail.com
        </a>
        <span class="contact-chip">
          📍 Pondicherry, India
        </span>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-logo">Ram Kumar Fitness</div>
    <div class="footer-copy">© 2026 Ram Kumar · Personal Trainer · Pondicherry</div>
    <a 
      href="https://wa.me/919791264563?text=Hi%20Ram!" 
      target="_blank" 
      style="display:flex;align-items:center;gap:0.5rem;background:#25D366;color:#fff;padding:0.6rem 1.2rem;font-family:'Barlow Condensed',sans-serif;font-size:0.8rem;letter-spacing:2px;text-decoration:none;text-transform:uppercase;"
    >
      <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
      WhatsApp
    </a>
  </footer>

  <!-- SCROLL REVEAL SCRIPT -->
  <script>
    const reveals = document.querySelectorAll('.reveal');

    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry, i) => {
        if (entry.isIntersecting) {
          const siblings = entry.target.parentElement.querySelectorAll('.reveal');
          let delay = 0;
          siblings.forEach((sib, idx) => {
            if (sib === entry.target) delay = idx * 80;
          });
          setTimeout(() => {
            entry.target.classList.add('visible');
          }, delay);
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.12 });

    reveals.forEach(el => observer.observe(el));

    const sections = document.querySelectorAll('section[id]');
    const navLinks = document.querySelectorAll('.nav-links a');

    window.addEventListener('scroll', () => {
      let current = '';
      sections.forEach(sec => {
        if (window.scrollY >= sec.offsetTop - 120) current = sec.id;
      });
      navLinks.forEach(a => {
        a.style.color = a.getAttribute('href') === `#${current}` ? 'var(--secondary)' : '';
      });
    });
  </script>

</body>
</html>
