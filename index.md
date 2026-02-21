
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Rûmeysa CAN | Portfolio</title>
  <meta property="og:type" content="website"/>
  <meta property="og:url" content="https://uruys.github.io/"/>
  <meta property="og:title" content="Rûmeysa CAN — Neurosciences computationnelles & BCI"/>
  <meta property="og:description" content="Portfolio académique — neurosciences computationnelles, bioinformatique, interfaces cerveau-machine."/>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Lora:ital,wght@1,400;1,500&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg:#08090d; --bg2:#0f1117; --bg3:#141720;
      --border:rgba(255,255,255,0.07);
      --text:#c8cdd8; --dim:#4a5060; --bright:#e8ecf4;
      --blue:#7eb8f7; --green:#67e8b0; --purple:#a78bfa;
      --orange:#f7a76e; --pink:#f472b6;
    }
    *,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{font-family:'JetBrains Mono',monospace;background:var(--bg);color:var(--text);font-size:13.5px;line-height:1.7;overflow-x:hidden}
    body::before{content:'';position:fixed;inset:0;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");opacity:.022;pointer-events:none;z-index:9999}

    /* NAV */
    nav{position:fixed;top:0;left:0;right:0;z-index:100;display:flex;align-items:center;justify-content:space-between;padding:0 3rem;height:54px;background:rgba(8,9,13,0.88);backdrop-filter:blur(16px);border-bottom:1px solid var(--border)}
    .nav-logo{font-family:'Syne',sans-serif;font-weight:800;font-size:12.5px;color:var(--bright);text-decoration:none;letter-spacing:.06em;text-transform:uppercase}
    .nav-links{display:flex;gap:2rem;list-style:none}
    .nav-links a{color:var(--dim);text-decoration:none;font-size:11px;letter-spacing:.08em;text-transform:uppercase;transition:color .2s}
    .nav-links a:hover{color:var(--blue)}

    /* LAYOUT */
    main{max-width:900px;margin:0 auto;padding:0 2rem}
    section{padding:5.5rem 0 3.5rem}

    /* HERO */
    #home{padding-top:120px;padding-bottom:4rem;min-height:92vh;display:grid;grid-template-columns:1fr 1fr;gap:3rem;align-items:center}
    .hero-eyebrow{font-size:10.5px;letter-spacing:.18em;text-transform:uppercase;color:var(--green);margin-bottom:1.1rem;display:flex;align-items:center;gap:.7rem}
    .hero-eyebrow::before{content:'';width:26px;height:1px;background:var(--green)}
    h1{font-family:'Syne',sans-serif;font-weight:800;font-size:clamp(2.2rem,4.5vw,3.2rem);line-height:1.06;color:var(--bright);letter-spacing:-.02em;margin-bottom:.5rem}
    .hero-sub{font-family:'Lora',serif;font-style:italic;font-size:1rem;color:var(--blue);margin-bottom:1.6rem;opacity:.9}
    .hero-desc{font-size:13px;line-height:1.85;color:var(--text);margin-bottom:2rem;max-width:420px}
    .hero-btns{display:flex;gap:.8rem;flex-wrap:wrap}
    .btn{display:inline-flex;align-items:center;gap:.45rem;padding:.5rem 1.1rem;border-radius:4px;font-family:'JetBrains Mono',monospace;font-size:11.5px;letter-spacing:.04em;text-decoration:none;transition:all .2s;cursor:pointer;border:none}
    .btn-primary{background:var(--blue);color:#08090d;font-weight:500}
    .btn-primary:hover{background:#a3cdfb}
    .btn-ghost{border:1px solid var(--border) !important;color:var(--dim)}
    .btn-ghost:hover{border-color:var(--purple) !important;color:var(--purple)}

    /* HERO VISUAL */
    .hero-right{position:relative;height:420px;border-radius:12px;overflow:hidden;background:var(--bg2);border:1px solid var(--border)}
    #heroCanvas{position:absolute;inset:0;width:100%;height:100%}
    .code-overlay{position:absolute;inset:0;pointer-events:none;overflow:hidden}
    .code-line{position:absolute;font-size:9.5px;white-space:nowrap;opacity:0;animation:floatUp linear infinite}
    @keyframes floatUp{0%{opacity:0;transform:translateY(8px)}8%{opacity:1}88%{opacity:.5}100%{opacity:0;transform:translateY(-22px)}}

    /* Terminal */
    .hero-terminal{position:absolute;bottom:16px;right:14px;width:210px;background:rgba(8,9,13,.9);border:1px solid rgba(126,184,247,.14);border-radius:8px;overflow:hidden;backdrop-filter:blur(10px)}
    .term-header{padding:5px 10px;background:rgba(255,255,255,.03);display:flex;align-items:center;gap:5px;border-bottom:1px solid rgba(255,255,255,.05)}
    .dot{width:7px;height:7px;border-radius:50%}
    .dot-r{background:#ff5f57}.dot-y{background:#febc2e}.dot-g{background:#28c840}
    .term-title{font-size:9px;color:var(--dim);margin-left:auto}
    .term-body{padding:7px 10px;font-size:9px;line-height:1.9}
    .kw{color:var(--purple)}.fn{color:var(--blue)}.st{color:var(--orange)}.cm{color:var(--dim)}.ok{color:var(--green)}
    .cursor{display:inline-block;width:5px;height:10px;background:var(--blue);animation:blink 1s infinite;vertical-align:middle}
    @keyframes blink{0%,49%{opacity:1}50%,100%{opacity:0}}

    /* Stats chips */
    .hero-stats{position:absolute;top:16px;left:14px;display:flex;flex-direction:column;gap:5px}
    .chip{background:rgba(8,9,13,.82);border:1px solid rgba(255,255,255,.07);border-radius:5px;padding:3px 8px;font-size:9px;color:var(--text);backdrop-filter:blur(8px);display:flex;align-items:center;gap:5px;opacity:0;animation:chipIn .4s ease forwards}
    .chip:nth-child(1){animation-delay:.2s}.chip:nth-child(2){animation-delay:.4s}.chip:nth-child(3){animation-delay:.6s}
    @keyframes chipIn{from{opacity:0;transform:translateX(-8px)}to{opacity:1;transform:translateX(0)}}
    .cdot{width:5px;height:5px;border-radius:50%}

    /* SECTION */
    .sec-label{font-size:10.5px;letter-spacing:.2em;text-transform:uppercase;color:var(--dim);margin-bottom:2.8rem;display:flex;align-items:center;gap:1rem}
    .sec-label::after{content:'';flex:1;height:1px;background:var(--border)}

    /* ABOUT */
    .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:2.5rem}
    .about-text{font-size:13px;line-height:1.9}
    .about-text p+p{margin-top:.9rem}
    .hl{color:var(--bright)}
    .skills-col{display:flex;flex-direction:column;gap:1.4rem}
    .sk-group h4{font-size:10px;letter-spacing:.15em;text-transform:uppercase;color:var(--green);margin-bottom:.55rem}
    .tags{display:flex;flex-wrap:wrap;gap:.35rem}
    .tag{display:inline-block;padding:.18rem .58rem;border-radius:3px;font-size:11px}
    .tb{background:rgba(126,184,247,.1);color:var(--blue);border:1px solid rgba(126,184,247,.2)}
    .tp{background:rgba(167,139,250,.1);color:var(--purple);border:1px solid rgba(167,139,250,.2)}
    .tg{background:rgba(103,232,176,.1);color:var(--green);border:1px solid rgba(103,232,176,.2)}
    .to{background:rgba(247,167,110,.1);color:var(--orange);border:1px solid rgba(247,167,110,.2)}
    .tk{background:rgba(255,255,255,.04);color:var(--dim);border:1px solid var(--border)}

    /* EXPERIENCE */
    .exp-item{display:grid;grid-template-columns:150px 1fr;gap:2rem;padding:2rem 0;border-bottom:1px solid var(--border)}
    .exp-item:first-child{border-top:1px solid var(--border)}
    .exp-date{font-size:11px;color:var(--dim);letter-spacing:.04em;padding-top:.2rem;line-height:1.5}
    .exp-body h3{font-family:'Syne',sans-serif;font-weight:600;font-size:.95rem;color:var(--bright);margin-bottom:.25rem}
    .exp-org{font-size:11.5px;color:var(--blue);margin-bottom:.7rem;opacity:.9}
    .exp-body p{font-size:12.5px;color:var(--text);line-height:1.8}
    .exp-body ul{margin-top:.5rem;padding-left:1.1rem;font-size:12px;line-height:1.85}
    .exp-body ul li{margin-bottom:.25rem}
    .exp-tags{display:flex;flex-wrap:wrap;gap:.35rem;margin-top:.7rem}

    /* EDUCATION */
    .edu-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.4rem}
    .edu-card{background:var(--bg2);border:1px solid var(--border);border-radius:8px;padding:1.4rem;transition:border-color .2s}
    .edu-card:hover{border-color:rgba(126,184,247,.28)}
    .edu-year{font-size:10.5px;color:var(--dim);letter-spacing:.08em;margin-bottom:.5rem}
    .edu-card h3{font-family:'Syne',sans-serif;font-weight:700;font-size:.9rem;color:var(--bright);margin-bottom:.25rem;line-height:1.3}
    .edu-school{font-size:11.5px;color:var(--blue);margin-bottom:.7rem}
    .edu-body{font-size:11.5px;color:var(--dim);line-height:1.75}

    /* PROJECTS */
    .proj-grid{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--border);border:1px solid var(--border);border-radius:8px;overflow:hidden}
    .proj-card{background:var(--bg2);padding:1.4rem;transition:background .2s}
    .proj-card:hover{background:var(--bg3)}
    .proj-card h3{font-family:'Syne',sans-serif;font-weight:600;font-size:.88rem;color:var(--bright);margin-bottom:.55rem;line-height:1.3}
    .proj-tags{display:flex;flex-wrap:wrap;gap:.3rem;margin-bottom:.7rem}
    .proj-card p{font-size:11.5px;color:var(--dim);line-height:1.75;margin-bottom:.9rem}
    .proj-link{display:inline-flex;align-items:center;gap:.35rem;font-size:10.5px;color:var(--blue);text-decoration:none;letter-spacing:.04em;transition:color .2s}
    .proj-link:hover{color:var(--bright)}

    /* FOOTER */
    footer{border-top:1px solid var(--border);padding:2rem 0 4rem;display:flex;justify-content:space-between;align-items:center;font-size:11px;color:var(--dim)}
    footer a{color:var(--dim);text-decoration:none;transition:color .2s}
    footer a:hover{color:var(--blue)}

    /* ANIMATIONS */
    @keyframes fadeUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}
    .fu{animation:fadeUp .55s ease forwards;opacity:0}
    .d1{animation-delay:.05s}.d2{animation-delay:.15s}.d3{animation-delay:.25s}.d4{animation-delay:.35s}.d5{animation-delay:.45s}

    /* RESPONSIVE */
    @media(max-width:680px){
      nav{padding:0 1.2rem}.nav-links{display:none}
      main{padding:0 1.2rem}
      #home{grid-template-columns:1fr;min-height:auto;padding-top:90px}
      .hero-right{height:260px}
      .about-grid,.edu-grid,.proj-grid{grid-template-columns:1fr}
      .exp-item{grid-template-columns:1fr;gap:.4rem}
    }
  </style>
</head>
<body>

<nav>
  <a href="#home" class="nav-logo">Rûmeysa CAN</a>
  <ul class="nav-links">
    <li><a href="#about">À propos</a></li>
    <li><a href="#experience">Expériences</a></li>
    <li><a href="#education">Formation</a></li>
    <li><a href="#projects">Projets</a></li>
  </ul>
</nav>

<main>

  <!-- HERO -->
  <section id="home">
    <div class="hero-left">
      <div class="hero-eyebrow fu d1">neurosciences computationnelles</div>
      <h1 class="fu d2">Salut ! Je suis<br>Rûmeysa 👋</h1>
      <p class="hero-sub fu d3">étudiante en L3 Sciences de la Vie — Sorbonne Paris Nord</p>
      <p class="hero-desc fu d4">Passionnée par les <strong class="hl">interfaces cerveau-machine</strong> et l'exploitation computationnelle des signaux biologiques et neuronaux. À l'intersection des neurosciences, de la bioinformatique, des statistiques et de l'IA.</p>
      <div class="hero-btns fu d5">
        <a href="https://github.com/uruys" class="btn btn-primary" target="_blank">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
          GitHub
        </a>
        <a href="#projects" class="btn btn-ghost">Voir mes projets →</a>
      </div>
    </div>

    <div class="hero-right">
      <canvas id="heroCanvas"></canvas>
      <div class="code-overlay" id="codeOverlay"></div>
      <div class="hero-stats">
        <div class="chip"><div class="cdot" style="background:var(--green)"></div>scRNA-seq · 8 432 cells</div>
        <div class="chip"><div class="cdot" style="background:var(--blue)"></div>EEG · 64 ch · 256 Hz</div>
        <div class="chip"><div class="cdot" style="background:var(--orange)"></div>BCI accuracy · 94.2%</div>
      </div>
      <div class="hero-terminal">
        <div class="term-header">
          <div class="dot dot-r"></div><div class="dot dot-y"></div><div class="dot dot-g"></div>
          <span class="term-title">analysis.py</span>
        </div>
        <div class="term-body">
          <div><span class="kw">import</span> <span class="fn">scanpy</span> <span class="kw">as</span> sc</div>
          <div><span class="kw">import</span> <span class="fn">mne</span>, numpy <span class="kw">as</span> np</div>
          <div><span class="cm"># normalize &amp; cluster</span></div>
          <div>sc.pp.normalize_total(<span class="st">adata</span>)</div>
          <div>sc.tl.leiden(<span class="st">adata</span>, res=<span class="fn">0.5</span>)</div>
          <div><span class="ok">→ 12 clusters found</span><span class="cursor"></span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="sec-label">À propos</div>
    <div class="about-grid">
      <div class="about-text">
        <p>Étudiante en <span class="hl">Licence 3 Sciences de la Vie</span> à l'Université Sorbonne Paris Nord, je me spécialise en neurosciences computationnelles, bioinformatique et IA appliquée au biomédical.</p>
        <p>Mon objectif est de m'orienter vers la <span class="hl">neuro-ingénierie et les interfaces cerveau-machine</span>, avec un intérêt particulier pour l'exploitation computationnelle des signaux biologiques et neuronaux.</p>
        <p>J'ai travaillé dans deux laboratoires — <span class="hl">NeuroPSI</span> (CNRS / Paris-Saclay) et <span class="hl">BME Lab</span> (Hôpital Saint-Joseph) — combinant analyse de données, bioinformatique et expériences en laboratoire.</p>
      </div>
      <div class="skills-col">
        <div class="sk-group">
          <h4>Neuro-ingénierie & BCI</h4>
          <div class="tags">
            <span class="tag tb">Interfaces cerveau-machine</span>
            <span class="tag tb">Signaux neuronaux</span>
            <span class="tag tb">Biocapteurs</span>
            <span class="tag tb">Électrophysiologie</span>
          </div>
        </div>
        <div class="sk-group">
          <h4>Bioinformatique & Stats</h4>
          <div class="tags">
            <span class="tag tp">scRNA-seq</span>
            <span class="tag tp">DESeq2</span>
            <span class="tag tp">Scanpy</span>
            <span class="tag tp">Machine Learning</span>
            <span class="tag tp">Statistiques appliquées</span>
          </div>
        </div>
        <div class="sk-group">
          <h4>Programmation & Outils</h4>
          <div class="tags">
            <span class="tag tg">Python</span>
            <span class="tag tg">R</span>
            <span class="tag tg">MATLAB</span>
            <span class="tag tg">SQL</span>
            <span class="tag tk">MNE-Python</span>
            <span class="tag tk">DeepLabCut</span>
            <span class="tag tk">Fiji/ImageJ</span>
            <span class="tag tk">Linux</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- EXPERIENCE -->
  <section id="experience">
    <div class="sec-label">Expériences de recherche</div>
    <div class="exp-item">
      <div class="exp-date">2024 – 2025</div>
      <div class="exp-body">
        <h3>Stagiaire — Neurosciences computationnelles</h3>
        <div class="exp-org">Institut des Neurosciences Paris-Saclay (NeuroPSI) · CNRS / Université Paris-Saclay</div>
        <p>Stage de recherche en neurosciences computationnelles axé sur l'analyse comportementale animale.</p>
        <ul>
          <li>Analyse de données comportementales issues de <em>DeepLabCut</em> pour le suivi des mouvements chez la souris.</li>
          <li>Extraction des coordonnées, calcul de métriques cinématiques (trajectoire, vitesse) et visualisation Python.</li>
        </ul>
        <div class="exp-tags">
          <span class="tag tg">Python</span><span class="tag tk">DeepLabCut</span>
          <span class="tag tb">Comportement animal</span><span class="tag tp">Cinématique</span>
        </div>
      </div>
    </div>
    <div class="exp-item">
      <div class="exp-date">2023 – 2024</div>
      <div class="exp-body">
        <h3>Stagiaire — Bioingénierie Médicale</h3>
        <div class="exp-org">BME Lab · Fondation Hôpital Saint-Joseph, Paris</div>
        <p>Stage axé sur l'analyse de signaux biologiques et les interfaces capteur-machine.</p>
        <ul>
          <li>Analyse et interprétation de signaux biologiques issus de biocapteurs.</li>
          <li>Exploration du pipeline acquisition → traitement → interaction machine dans le contexte des BCI.</li>
        </ul>
        <div class="exp-tags">
          <span class="tag tb">Biocapteurs</span><span class="tag tb">BCI</span>
          <span class="tag tg">Python</span><span class="tag tp">Traitement du signal</span>
        </div>
      </div>
    </div>
  </section>

  <!-- EDUCATION -->
  <section id="education">
    <div class="sec-label">Formation</div>
    <div class="edu-grid">
      <div class="edu-card">
        <div class="edu-year">2022 – présent</div>
        <h3>Licence Sciences de la Vie</h3>
        <div class="edu-school">Université Sorbonne Paris Nord</div>
        <p class="edu-body">Spécialisation : neurosciences computationnelles, bioinformatique, IA biomédicale.<br><br>Cours clés : Informatique · Statistiques · Neurosciences · Analyse de données · Imagerie médicale · Nanotechnologies · Ingénierie</p>
      </div>
      <div class="edu-card">
        <div class="edu-year">Certifications</div>
        <h3>Formations complémentaires</h3>
        <div class="edu-school">En ligne & Institutions</div>
        <p class="edu-body">· Statistiques appliquées<br>· SQL & bases de données relationnelles<br>· Machine Learning (fondamentaux)<br>· Bioinformatique<br>· Neurosciences computationnelles<br>· Anglais avancé — Niveau C1</p>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="sec-label">Projets</div>
    <div class="proj-grid">

      <div class="proj-card">
        <h3>Analyse EEG — Activité cérébrale & Épilepsie</h3>
        <div class="proj-tags"><span class="tag tb">EEG</span><span class="tag tb">Neurosciences</span><span class="tag tg">Python</span></div>
        <p>Analyse de signaux EEG comparant activité normale et crise épileptique. Visualisation, puissance spectrale et interprétation des différences.</p>
        <a href="https://github.com/uruys/eeg-neuroscience-analyse" class="proj-link" target="_blank">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
          GitHub
        </a>
      </div>

      <div class="proj-card">
        <h3>DeepLabCut — Comportement souris</h3>
        <div class="proj-tags"><span class="tag tb">Neurosciences comp.</span><span class="tag tk">DeepLabCut</span><span class="tag tg">Python</span><span class="tag to">Recherche</span></div>
        <p>Suivi de mouvement chez la souris. Métriques cinématiques (trajectoire, vitesse). Projet issu du NeuroPSI, CNRS / Paris-Saclay.</p>
        <a href="https://github.com/uruys/computational-neuroscience-analysis" class="proj-link" target="_blank">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
          GitHub
        </a>
      </div>

      <div class="proj-card">
        <h3>Single-cell RNA-seq — Clustering cellulaire</h3>
        <div class="proj-tags"><span class="tag tp">Bioinformatique</span><span class="tag tg">Python</span><span class="tag tk">Scanpy</span><span class="tag tp">scRNA-seq</span></div>
        <p>Analyse scRNA-seq avec Scanpy : normalisation, PCA, clustering Leiden, UMAP et heatmap pour identifier des sous-populations cellulaires.</p>
        <a href="https://github.com/uruys/Analyse-cell-rnaseq" class="proj-link" target="_blank">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
          GitHub
        </a>
      </div>

      <div class="proj-card">
        <h3>Bioinformatique — Lupus & PRDM1</h3>
        <div class="proj-tags"><span class="tag tp">Bioinformatique</span><span class="tag tp">DESeq2</span><span class="tag tg">R</span><span class="tag tk">Immunologie</span></div>
        <p>Analyse d'expression génique avec DESeq2 et volcano plot pour étudier le rôle de PRDM1 dans le lupus et les maladies auto-immunes.</p>
        <a href="https://github.com/uruys/Bioinformatics_Lupus_PRDM1" class="proj-link" target="_blank">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
          GitHub
        </a>
      </div>

      <div class="proj-card">
        <h3>Analyse de biocapteurs — BCI</h3>
        <div class="proj-tags"><span class="tag tb">Biocapteurs</span><span class="tag tb">BCI</span><span class="tag tg">Python</span></div>
        <p>Pipeline complet biocapteur → signal → machine : acquisition, traitement et décodage dans le contexte des interfaces cerveau-machine.</p>
        <a href="https://github.com/uruys/Projet_Biocapteurs" class="proj-link" target="_blank">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
          GitHub
        </a>
      </div>

      <div class="proj-card">
        <h3>Neurotechnologies & Parkinson</h3>
        <div class="proj-tags"><span class="tag tb">Neurotechnologies</span><span class="tag to">Article scientifique</span><span class="tag tk">Parkinson</span></div>
        <p>Article scientifique sur les BCI implantables dans la maladie de Parkinson — électrophysiologie, implants neuronaux, décodage cérébral.</p>
        <a href="https://github.com/uruys/Neurotech_Parkinson" class="proj-link" target="_blank">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
          GitHub
        </a>
      </div>

    </div>
  </section>

  <footer>
    <span>© 2025 Rûmeysa CAN</span>
    <a href="https://github.com/uruys" target="_blank">github.com/uruys</a>
  </footer>

</main>

<script>
(function(){
  const canvas = document.getElementById('heroCanvas');
  const overlay = document.getElementById('codeOverlay');
  const ctx = canvas.getContext('2d');
  let W, H, nodes, signals=[], t=0;

  function resize(){
    const r = canvas.parentElement.getBoundingClientRect();
    canvas.width=r.width; canvas.height=r.height; W=r.width; H=r.height; buildNodes();
  }

  function buildNodes(){
    nodes=[];
    const layers=[4,6,7,6,4];
    layers.forEach((cnt,li)=>{
      const x=W*0.10+li*(W*0.20);
      for(let j=0;j<cnt;j++){
        const y=H*0.10+(H*0.80/Math.max(cnt-1,1))*j;
        nodes.push({x,y,ox:x,oy:y,vx:(Math.random()-.5)*.1,vy:(Math.random()-.5)*.1,r:3+Math.random()*2.2,phase:Math.random()*Math.PI*2,layer:li,active:Math.random()>.2});
      }
    });
    for(let i=0;i<10;i++){
      nodes.push({x:Math.random()*W,y:Math.random()*H,ox:null,vx:(Math.random()-.5)*.35,vy:(Math.random()-.5)*.35,r:1.5+Math.random()*1.2,phase:Math.random()*Math.PI*2,layer:-1,active:Math.random()>.45});
    }
  }

  function spawnSignal(){
    if(Math.random()>.028||signals.length>9)return;
    const lm={};
    nodes.forEach(n=>{if(n.layer>=0)(lm[n.layer]=lm[n.layer]||[]).push(n);});
    const maxL=Math.max(...Object.keys(lm).map(Number));
    const fl=Math.floor(Math.random()*maxL);
    const from=lm[fl]?.[Math.floor(Math.random()*(lm[fl]?.length||1))];
    const to=lm[fl+1]?.[Math.floor(Math.random()*(lm[fl+1]?.length||1))];
    if(from&&to)signals.push({from,to,p:0,spd:.016+Math.random()*.02});
  }

  function draw(){
    ctx.clearRect(0,0,W,H);
    ctx.fillStyle='rgba(15,17,23,0.2)';
    ctx.fillRect(0,0,W,H);
    t+=.01; spawnSignal();

    for(let i=0;i<nodes.length;i++){
      for(let j=i+1;j<nodes.length;j++){
        const a=nodes[i],b=nodes[j];
        const d=Math.hypot(a.x-b.x,a.y-b.y);
        const linked=(a.layer>=0&&b.layer===a.layer+1&&d<185)||(a.layer<0&&d<62)||(b.layer<0&&d<62);
        if(linked&&d<200){
          const al=Math.min(.36,(1-d/200)*.5);
          ctx.strokeStyle=`hsla(${212+Math.sin(t+i*.2)*14},78%,66%,${al})`;
          ctx.lineWidth=.65;
          ctx.beginPath();ctx.moveTo(a.x,a.y);ctx.lineTo(b.x,b.y);ctx.stroke();
        }
      }
    }

    signals.forEach((s,si)=>{
      s.p+=s.spd;
      if(s.p>=1){signals.splice(si,1);return;}
      const x=s.from.x+(s.to.x-s.from.x)*s.p;
      const y=s.from.y+(s.to.y-s.from.y)*s.p;
      const g=ctx.createRadialGradient(x,y,0,x,y,9);
      g.addColorStop(0,'rgba(126,184,247,.9)');g.addColorStop(1,'rgba(126,184,247,0)');
      ctx.beginPath();ctx.arc(x,y,9,0,Math.PI*2);ctx.fillStyle=g;ctx.fill();
      ctx.beginPath();ctx.arc(x,y,2.5,0,Math.PI*2);ctx.fillStyle='#7eb8f7';ctx.fill();
    });

    nodes.forEach(n=>{
      if(n.ox!==null){n.vx+=(n.ox-n.x)*.0016;n.vy+=(n.oy-n.y)*.0016;n.vx*=.97;n.vy*=.97;}
      else{if(n.x<0||n.x>W)n.vx*=-1;if(n.y<0||n.y>H)n.vy*=-1;}
      n.x+=n.vx;n.y+=n.vy;
      const pulse=Math.sin(t*2+n.phase)*.5+.5;
      const r=n.r+(n.active?pulse*1.8:0);
      if(n.active){
        const g=ctx.createRadialGradient(n.x,n.y,0,n.x,n.y,r*4.5);
        g.addColorStop(0,`rgba(126,184,247,${.28*pulse})`);g.addColorStop(1,'rgba(126,184,247,0)');
        ctx.beginPath();ctx.arc(n.x,n.y,r*4.5,0,Math.PI*2);ctx.fillStyle=g;ctx.fill();
      }
      ctx.beginPath();ctx.arc(n.x,n.y,r,0,Math.PI*2);
      ctx.fillStyle=n.active?`rgba(126,184,247,${.6+pulse*.4})`:'rgba(74,80,96,.55)';
      ctx.fill();
    });
    requestAnimationFrame(draw);
  }

  resize(); window.addEventListener('resize',resize); draw();

  const snippets=[
    'import scanpy as sc','sc.pp.normalize_total(adata)','sc.tl.pca(adata)',
    'sc.tl.umap(adata)','sc.tl.leiden(adata)','sc.pp.highly_variable_genes(adata)',
    'from Bio import SeqIO','SeqIO.parse("seq.fasta","fasta")',
    'from scipy import stats','stats.ttest_ind(group_A, group_B)',
    'p.adjust(pvals, method="BH")','sns.heatmap(corr, annot=True)',
    'PCA(n_components=3).fit(X)','cross_val_score(clf, X, y, cv=5)',
    'import mne','raw.filter(1., 40.)','epochs = mne.Epochs(raw, events)',
    'np.fft.rfft(eeg_signal)','signal.welch(ch, fs=256)',
    'dlc.analyze_videos(cfg, videos)','bci.decode(neural_signal)',
    'library(DESeq2)','res <- results(DESeq(dds))',
    'ggplot(df,aes(x,y))+geom_point()','cor.test(x,y,method="spearman")',
  ];
  const colors=['rgba(126,184,247,0.32)','rgba(103,232,176,0.28)','rgba(167,139,250,0.28)','rgba(247,167,110,0.24)'];

  function spawnCode(){
    const el=document.createElement('div');
    el.className='code-line';
    el.textContent=snippets[Math.floor(Math.random()*snippets.length)];
    el.style.left=(6+Math.random()*55)+'%';
    el.style.bottom=(5+Math.random()*65)+'%';
    el.style.color=colors[Math.floor(Math.random()*colors.length)];
    el.style.animationDuration=(5+Math.random()*7)+'s';
    el.style.animationDelay=(Math.random()*2)+'s';
    overlay.appendChild(el);
    setTimeout(()=>el.remove(),14000);
  }
  for(let i=0;i<8;i++)setTimeout(spawnCode,i*200);
  setInterval(spawnCode,650);
})();
</script>
</body>
</html>artificielle.


