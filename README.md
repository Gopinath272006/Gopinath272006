<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Gopinath Kaniyanppan — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Caveat:wght@400;600;700&family=Space+Mono:wght@400;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}

:root{
  --ink:#0d0d0d;
  --red:#cc2b2b;
  --red-light:#f5e8e8;
  --paper:#f8f8f5;
  --grid-line:#d8d8d0;
  --muted:#888;
  --border:#ddd;
  --white:#fff;
  --card-shadow:0 2px 20px rgba(0,0,0,0.07);
}

html{scroll-behavior:smooth}

body{
  background:var(--paper);
  color:var(--ink);
  font-family:'Inter',sans-serif;
  font-size:15px;
  line-height:1.7;
  overflow-x:hidden;
}

/* Grid paper background */
body::before{
  content:'';
  position:fixed;
  inset:0;
  background-image:
    linear-gradient(to right,var(--grid-line) 1px,transparent 1px),
    linear-gradient(to bottom,var(--grid-line) 1px,transparent 1px);
  background-size:28px 28px;
  opacity:0.35;
  pointer-events:none;
  z-index:0;
}

/* ── LAYOUT ─────────────────────── */
.page{position:relative;z-index:1;max-width:960px;margin:0 auto;padding:0 32px}

/* ── CORNER LABELS ──────────────── */
.corner-label{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  position:absolute;
  letter-spacing:0.04em;
}
.corner-label.red{color:var(--red)}

/* ── NAV ────────────────────────── */
nav{
  position:fixed;
  top:0;left:0;right:0;
  z-index:100;
  background:rgba(248,248,245,0.92);
  backdrop-filter:blur(12px);
  border-bottom:1px solid var(--border);
  padding:14px 40px;
  display:flex;
  align-items:center;
  justify-content:space-between;
}
.nav-logo{
  font-family:'Caveat',cursive;
  font-size:22px;
  font-weight:700;
  color:var(--ink);
  text-decoration:none;
}
.nav-links{display:flex;gap:28px;list-style:none}
.nav-links a{
  font-family:'Space Mono',monospace;
  font-size:11px;
  color:var(--muted);
  text-decoration:none;
  letter-spacing:0.05em;
  transition:color 0.2s;
}
.nav-links a:hover{color:var(--red)}
.nav-dot{
  width:8px;height:8px;
  border-radius:50%;
  background:var(--red);
  animation:pulse-dot 2s ease-in-out infinite;
}
@keyframes pulse-dot{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.5;transform:scale(0.8)}}

/* ── HERO ───────────────────────── */
#hero{
  min-height:100vh;
  display:grid;
  grid-template-columns:1fr 380px;
  gap:40px;
  align-items:center;
  padding-top:80px;
  position:relative;
}
.hero-meta-top{
  position:absolute;
  top:100px;right:0;
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  text-align:right;
  line-height:1.8;
}
.hero-meta-corner{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--red);
  position:absolute;
  top:100px;left:0;
}
.hero-tag{
  font-family:'Space Mono',monospace;
  font-size:11px;
  color:var(--red);
  letter-spacing:0.1em;
  margin-bottom:24px;
  opacity:0;
  animation:fadeUp 0.6s 0.2s forwards;
}
.hero-name{
  font-family:'Caveat',cursive;
  font-size:clamp(52px,7vw,88px);
  font-weight:700;
  line-height:1;
  letter-spacing:-0.01em;
  margin-bottom:20px;
  opacity:0;
  animation:fadeUp 0.7s 0.35s forwards;
}
.hero-role{
  font-family:'Caveat',cursive;
  font-size:24px;
  font-weight:400;
  color:var(--muted);
  margin-bottom:20px;
  opacity:0;
  animation:fadeUp 0.7s 0.5s forwards;
}
.hero-desc{
  font-size:15px;
  color:#555;
  max-width:460px;
  line-height:1.8;
  margin-bottom:36px;
  opacity:0;
  animation:fadeUp 0.7s 0.65s forwards;
}
.hero-btns{
  display:flex;gap:14px;flex-wrap:wrap;
  opacity:0;
  animation:fadeUp 0.7s 0.8s forwards;
}
.btn{
  font-family:'Space Mono',monospace;
  font-size:12px;
  padding:12px 24px;
  border-radius:0;
  cursor:pointer;
  text-decoration:none;
  letter-spacing:0.04em;
  transition:all 0.2s;
  display:inline-flex;align-items:center;gap:6px;
}
.btn-primary{
  background:var(--ink);
  color:var(--white);
  border:2px solid var(--ink);
}
.btn-primary:hover{background:var(--red);border-color:var(--red)}
.btn-outline{
  background:transparent;
  color:var(--red);
  border:2px solid var(--red);
}
.btn-outline:hover{background:var(--red);color:var(--white)}

/* Sketch portrait area */
.hero-portrait{
  position:relative;
  display:flex;
  align-items:center;
  justify-content:center;
  opacity:0;
  animation:fadeIn 1s 0.9s forwards;
}
.portrait-frame{
  width:300px;height:360px;
  border:1.5px solid var(--ink);
  position:relative;
  overflow:hidden;
}
.portrait-frame::before{
  content:'FIG 0. PORTRAIT';
  font-family:'Space Mono',monospace;
  font-size:9px;
  color:var(--muted);
  position:absolute;
  top:10px;right:10px;
  letter-spacing:0.08em;
}
.portrait-inner{
  width:100%;height:100%;
  display:flex;align-items:center;justify-content:center;
  background:#f0f0ec;
}
/* SVG sketch portrait */
.sketch-person{opacity:0.85}

/* Floating annotation */
.hero-annotation{
  position:absolute;
  font-family:'Caveat',cursive;
  font-size:14px;
  color:var(--muted);
}
.hero-annotation::after{
  content:'';
  display:block;
  width:40px;height:1px;
  background:var(--muted);
  margin-top:4px;
  border-bottom:none;
}
.ann-uni{
  bottom:-20px;right:-10px;
  color:var(--red);
  font-size:13px;
}

@keyframes fadeUp{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}

/* ── SECTION COMMON ─────────────── */
section{padding:100px 0 40px;position:relative}
.section-eyebrow{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--red);
  letter-spacing:0.15em;
  text-transform:uppercase;
  margin-bottom:12px;
}
.section-title{
  font-family:'Caveat',cursive;
  font-size:clamp(34px,4vw,48px);
  font-weight:700;
  line-height:1.1;
  margin-bottom:48px;
}
.section-divider{
  width:100%;
  height:1px;
  background:var(--border);
  margin-bottom:60px;
  position:relative;
}
.section-divider::before{
  content:attr(data-label);
  font-family:'Space Mono',monospace;
  font-size:9px;
  color:var(--muted);
  position:absolute;
  right:0;
  top:-10px;
  letter-spacing:0.08em;
}

/* ── ABOUT ──────────────────────── */
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:start}
.about-yaml{
  background:var(--ink);
  color:#98fb98;
  font-family:'Space Mono',monospace;
  font-size:12px;
  line-height:1.9;
  padding:28px 32px;
  border-radius:0;
  position:relative;
  overflow:hidden;
}
.about-yaml::before{
  content:'gopinath.config.yaml';
  display:block;
  color:#666;
  font-size:10px;
  margin-bottom:14px;
  padding-bottom:10px;
  border-bottom:1px solid #333;
}
.yaml-key{color:#7dd3fc}
.yaml-val{color:#fbbf24}
.yaml-comment{color:#4b5563}
.yaml-str{color:#86efac}
.about-text p{margin-bottom:16px;color:#444;line-height:1.85}
.about-stats{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:16px;
  margin-top:28px;
}
.stat-card{
  background:var(--white);
  border:1px solid var(--border);
  padding:20px;
  text-align:center;
}
.stat-num{
  font-family:'Caveat',cursive;
  font-size:36px;
  font-weight:700;
  color:var(--ink);
  display:block;
}
.stat-label{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  letter-spacing:0.05em;
}

/* ── SKILLS ─────────────────────── */
.skills-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:20px}
.skill-group{
  background:var(--white);
  border:1px solid var(--border);
  padding:24px;
  position:relative;
  transition:border-color 0.2s,transform 0.2s;
}
.skill-group:hover{border-color:var(--ink);transform:translateY(-3px)}
.skill-group-label{
  font-family:'Space Mono',monospace;
  font-size:9px;
  color:var(--red);
  letter-spacing:0.12em;
  text-transform:uppercase;
  margin-bottom:16px;
  display:flex;align-items:center;gap:8px;
}
.skill-group-label::after{content:'';flex:1;height:1px;background:var(--red-light)}
.skill-pills{display:flex;flex-wrap:wrap;gap:8px}
.skill-pill{
  font-family:'Space Mono',monospace;
  font-size:10px;
  background:var(--paper);
  border:1px solid var(--border);
  padding:5px 12px;
  color:var(--ink);
  letter-spacing:0.03em;
  transition:all 0.18s;
}
.skill-pill:hover{background:var(--ink);color:var(--white);border-color:var(--ink)}

/* Skill bar */
.skill-bar-list{display:flex;flex-direction:column;gap:14px;margin-top:40px}
.skill-bar-row{display:flex;align-items:center;gap:16px}
.skill-bar-name{
  font-family:'Space Mono',monospace;
  font-size:11px;
  color:var(--ink);
  width:130px;
  flex-shrink:0;
}
.skill-bar-track{
  flex:1;height:4px;
  background:var(--border);
  position:relative;
  overflow:hidden;
}
.skill-bar-fill{
  position:absolute;
  left:0;top:0;bottom:0;
  background:var(--ink);
  width:0;
  transition:width 1.2s cubic-bezier(0.16,1,0.3,1);
}
.skill-bar-fill.red{background:var(--red)}
.skill-bar-pct{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  width:32px;
  text-align:right;
}

/* ── PROJECTS ───────────────────── */
.projects-list{display:flex;flex-direction:column;gap:0}
.project-card{
  display:grid;
  grid-template-columns:1fr 320px;
  gap:0;
  border:1px solid var(--border);
  margin-bottom:24px;
  background:var(--white);
  transition:border-color 0.2s,box-shadow 0.2s;
  overflow:hidden;
}
.project-card:hover{border-color:var(--ink);box-shadow:4px 4px 0 var(--ink)}
.project-card.reverse{grid-template-columns:320px 1fr}
.project-info{padding:36px 40px}
.project-year{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--red);
  letter-spacing:0.1em;
  margin-bottom:10px;
}
.project-name{
  font-family:'Caveat',cursive;
  font-size:30px;
  font-weight:700;
  margin-bottom:12px;
  line-height:1.2;
}
.project-desc{color:#555;font-size:14px;line-height:1.8;margin-bottom:20px}
.project-tags{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:24px}
.project-tag{
  font-family:'Space Mono',monospace;
  font-size:10px;
  background:var(--paper);
  border:1px solid var(--border);
  padding:4px 10px;
  color:var(--muted);
}
.project-link{
  font-family:'Space Mono',monospace;
  font-size:11px;
  color:var(--ink);
  text-decoration:none;
  border-bottom:1.5px solid var(--ink);
  padding-bottom:2px;
  transition:color 0.2s,border-color 0.2s;
}
.project-link:hover{color:var(--red);border-color:var(--red)}
.project-visual{
  position:relative;
  overflow:hidden;
  min-height:260px;
  background:#f0f0ec;
  display:flex;align-items:center;justify-content:center;
}
.project-visual img{
  width:100%;height:100%;
  object-fit:cover;
  display:block;
  transition:transform 0.4s ease;
}
.project-card:hover .project-visual img{transform:scale(1.04)}
.project-visual-placeholder{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  text-align:center;
  padding:20px;
}

/* project visual overlays */
.proj-viz{width:100%;height:100%;position:relative;overflow:hidden}

/* ── ECOMMERCE STRIP ────────────── */
.ecom-strip{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:16px;
  margin-top:24px;
}
.ecom-card{
  background:var(--white);
  border:1px solid var(--border);
  padding:20px;
  text-align:center;
  transition:all 0.2s;
}
.ecom-card:hover{border-color:var(--ink);transform:translateY(-2px)}
.ecom-icon{font-size:28px;margin-bottom:10px}
.ecom-name{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--ink);
  word-break:break-all;
  margin-bottom:4px;
}
.ecom-stack{font-size:11px;color:var(--muted)}

/* ── EDUCATION ──────────────────── */
.edu-timeline{position:relative;padding-left:32px}
.edu-timeline::before{
  content:'';
  position:absolute;
  left:0;top:8px;bottom:8px;
  width:1.5px;
  background:var(--border);
}
.edu-entry{
  position:relative;
  margin-bottom:48px;
}
.edu-entry::before{
  content:'';
  position:absolute;
  left:-37px;top:6px;
  width:10px;height:10px;
  border-radius:50%;
  background:var(--red);
  border:2px solid var(--paper);
  outline:1.5px solid var(--red);
}
.edu-period{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--red);
  letter-spacing:0.08em;
  margin-bottom:8px;
}
.edu-degree{
  font-family:'Caveat',cursive;
  font-size:26px;
  font-weight:700;
  margin-bottom:4px;
}
.edu-institution{
  font-family:'Space Mono',monospace;
  font-size:11px;
  color:var(--muted);
  margin-bottom:8px;
}
.edu-detail{
  font-size:13px;
  color:#666;
}
.cgpa-badge{
  display:inline-block;
  background:var(--ink);
  color:var(--white);
  font-family:'Space Mono',monospace;
  font-size:10px;
  padding:4px 12px;
  margin-top:8px;
}

/* ── CONNECT ────────────────────── */
.connect-grid{display:grid;grid-template-columns:1fr 1fr;gap:0;border:1px solid var(--border)}
.connect-item{
  padding:28px 32px;
  border-right:1px solid var(--border);
  border-bottom:1px solid var(--border);
  display:flex;
  align-items:center;
  gap:20px;
  text-decoration:none;
  color:var(--ink);
  transition:background 0.2s;
}
.connect-item:hover{background:var(--ink);color:var(--white)}
.connect-item:hover .connect-icon{background:var(--white);color:var(--ink)}
.connect-item:hover .connect-label{color:rgba(255,255,255,0.6)}
.connect-icon{
  width:44px;height:44px;
  background:var(--paper);
  border:1px solid var(--border);
  display:flex;align-items:center;justify-content:center;
  font-size:18px;
  flex-shrink:0;
  transition:all 0.2s;
}
.connect-text{}
.connect-title{
  font-family:'Caveat',cursive;
  font-size:18px;
  font-weight:600;
}
.connect-label{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  margin-top:2px;
}

/* ── FOOTER ─────────────────────── */
footer{
  border-top:1px solid var(--border);
  padding:40px 0;
  margin-top:80px;
  display:flex;
  align-items:center;
  justify-content:space-between;
}
.footer-sig{
  font-family:'Caveat',cursive;
  font-size:28px;
  font-weight:700;
}
.footer-meta{
  font-family:'Space Mono',monospace;
  font-size:10px;
  color:var(--muted);
  text-align:right;
  line-height:2;
}

/* ── SCROLL ANIMATE ─────────────── */
.reveal{
  opacity:0;
  transform:translateY(28px);
  transition:opacity 0.7s ease,transform 0.7s ease;
}
.reveal.visible{opacity:1;transform:translateY(0)}

/* ── RESPONSIVE ─────────────────── */
@media(max-width:760px){
  #hero{grid-template-columns:1fr;min-height:auto;padding-top:100px}
  .hero-portrait{display:none}
  .about-grid,.skills-grid,.connect-grid{grid-template-columns:1fr}
  .project-card,.project-card.reverse{grid-template-columns:1fr}
  .project-card.reverse .project-visual{order:-1}
  .ecom-strip{grid-template-columns:1fr 1fr}
  nav{padding:12px 20px}
  .nav-links{gap:14px}
  .page{padding:0 20px}
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#hero">GK</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#connect">Connect</a></li>
  </ul>
  <div class="nav-dot"></div>
</nav>

<!-- HERO -->
<div class="page">
<section id="hero">
  <div class="corner-label red" style="top:90px;left:32px">— FINAL / MAIN v2.6</div>
  <div class="hero-meta-top">
    4th Year CS /<br/>Building since 2024
  </div>

  <div class="hero-left">
    <div class="hero-tag">// FULL-STACK DEVELOPER · AI ENTHUSIAST</div>
    <h1 class="hero-name">Gopinath<br/>Kaniyanppan</h1>
    <p class="hero-role">Full-Stack Developer &amp; AI Enthusiast</p>
    <p class="hero-desc">Passionate CS student building AI-powered applications and scalable web solutions. Crafting smart, automation-driven products that solve real-world problems.</p>
    <div class="hero-btns">
      <a href="#projects" class="btn btn-primary">View Projects →</a>
      <a href="https://gopinathk.me" target="_blank" class="btn btn-outline">gopinathk.me ↗</a>
    </div>
  </div>

  <div class="hero-portrait">
    <div class="portrait-frame">
      <div class="portrait-inner">
        <!-- Hand-drawn style SVG portrait -->
        <svg width="260" height="320" viewBox="0 0 260 320" fill="none" xmlns="http://www.w3.org/2000/svg" class="sketch-person">
          <!-- Body/shirt -->
          <path d="M60 280 Q60 240 80 220 L90 210 L130 225 L170 210 L180 220 Q200 240 200 280 L200 320 L60 320 Z" stroke="#1a1a1a" stroke-width="1.5" fill="#f5f5f0" stroke-linecap="round"/>
          <!-- Collar -->
          <path d="M110 215 L130 230 L150 215" stroke="#1a1a1a" stroke-width="1.5" fill="none" stroke-linecap="round"/>
          <!-- Neck -->
          <path d="M118 185 Q118 205 130 215 Q142 205 142 185" stroke="#1a1a1a" stroke-width="1.5" fill="#f0ede8" stroke-linecap="round"/>
          <!-- Head -->
          <ellipse cx="130" cy="155" rx="48" ry="58" stroke="#1a1a1a" stroke-width="1.5" fill="#f0ede8"/>
          <!-- Hair - messy/natural -->
          <path d="M85 140 Q82 110 90 95 Q100 75 115 68 Q130 62 145 68 Q162 76 170 95 Q178 114 175 138" stroke="#1a1a1a" stroke-width="2" fill="#2a2a2a" stroke-linecap="round"/>
          <path d="M88 128 Q85 108 92 90 Q105 70 130 65 Q155 68 168 88 Q176 108 173 130" stroke="#1a1a1a" stroke-width="1" fill="#2a2a2a"/>
          <!-- Hair detail strands -->
          <path d="M90 120 Q95 100 105 88" stroke="#1a1a1a" stroke-width="0.8" fill="none" opacity="0.6"/>
          <path d="M170 122 Q165 102 155 90" stroke="#1a1a1a" stroke-width="0.8" fill="none" opacity="0.6"/>
          <path d="M130 65 Q125 72 122 80" stroke="#1a1a1a" stroke-width="1" fill="none"/>
          <!-- Eyes -->
          <ellipse cx="112" cy="152" rx="8" ry="6" stroke="#1a1a1a" stroke-width="1.2" fill="white"/>
          <ellipse cx="148" cy="152" rx="8" ry="6" stroke="#1a1a1a" stroke-width="1.2" fill="white"/>
          <circle cx="113" cy="153" r="4" fill="#1a1a1a"/>
          <circle cx="149" cy="153" r="4" fill="#1a1a1a"/>
          <circle cx="115" cy="151" r="1.5" fill="white"/>
          <circle cx="151" cy="151" r="1.5" fill="white"/>
          <!-- Eyebrows -->
          <path d="M103 143 Q112 138 120 141" stroke="#1a1a1a" stroke-width="1.8" fill="none" stroke-linecap="round"/>
          <path d="M140 141 Q148 137 158 142" stroke="#1a1a1a" stroke-width="1.8" fill="none" stroke-linecap="round"/>
          <!-- Nose -->
          <path d="M128 160 Q125 172 122 176 Q128 180 138 176 Q135 172 132 160" stroke="#1a1a1a" stroke-width="1" fill="none" stroke-linecap="round"/>
          <!-- Lips / subtle smile -->
          <path d="M118 190 Q125 195 130 194 Q135 195 142 190" stroke="#1a1a1a" stroke-width="1.2" fill="none" stroke-linecap="round"/>
          <path d="M121 190 Q130 196 139 190" stroke="#1a1a1a" stroke-width="0.8" fill="#f0d0c0" stroke-linecap="round"/>
          <!-- Mustache hint -->
          <path d="M120 186 Q130 189 140 186" stroke="#1a1a1a" stroke-width="1" fill="none" stroke-linecap="round"/>
          <!-- Ear -->
          <path d="M82 148 Q76 155 78 162 Q82 168 88 165" stroke="#1a1a1a" stroke-width="1.2" fill="#f0ede8" stroke-linecap="round"/>
          <path d="M178 148 Q184 155 182 162 Q178 168 172 165" stroke="#1a1a1a" stroke-width="1.2" fill="#f0ede8" stroke-linecap="round"/>
          <!-- Shirt buttons/detail -->
          <line x1="130" y1="230" x2="130" y2="290" stroke="#1a1a1a" stroke-width="0.8" stroke-dasharray="2,4"/>
          <!-- Shirt texture lines -->
          <path d="M80 240 Q90 238 100 242" stroke="#1a1a1a" stroke-width="0.5" fill="none" opacity="0.4"/>
          <path d="M160 240 Q170 238 180 242" stroke="#1a1a1a" stroke-width="0.5" fill="none" opacity="0.4"/>
        </svg>
      </div>
    </div>
    <div class="hero-annotation ann-uni">Anna University ↗</div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-divider reveal" data-label="§ 01 / ABOUT"></div>
  <div class="section-eyebrow reveal">About</div>
  <h2 class="section-title reveal">Who I am</h2>
  <div class="about-grid reveal">
    <div class="about-yaml">
<span class="yaml-comment"># gopinath.config.yaml</span>
<span class="yaml-comment"># ─────────────────────</span>

<span class="yaml-key">name</span>: <span class="yaml-str">Gopinath Kaniyanppan</span>
<span class="yaml-key">alias</span>: <span class="yaml-str">gopinathk</span>
<span class="yaml-key">role</span>: <span class="yaml-str">Full-Stack Developer</span>
<span class="yaml-key">status</span>: <span class="yaml-val">🟢 Open to work</span>

<span class="yaml-key">education</span>:
  <span class="yaml-key">degree</span>: <span class="yaml-str">B.E. Computer Science</span>
  <span class="yaml-key">college</span>: <span class="yaml-str">HCET, Coimbatore</span>
  <span class="yaml-key">board</span>: <span class="yaml-str">Anna University</span>
  <span class="yaml-key">period</span>: <span class="yaml-val">2023 → 2027</span>
  <span class="yaml-key">cgpa</span>: <span class="yaml-val">8.0</span>

<span class="yaml-key">location</span>: <span class="yaml-str">Coimbatore, Tamil Nadu</span>
<span class="yaml-key">portfolio</span>: <span class="yaml-val">gopinathk.me</span>

<span class="yaml-key">focus</span>:
  - <span class="yaml-str">AI-powered applications</span>
  - <span class="yaml-str">Full-stack web development</span>
  - <span class="yaml-str">React Native mobile apps</span>
  - <span class="yaml-str">SEO · AEO · GEO</span>
    </div>
    <div class="about-text">
      <p>I'm a 4th-year Computer Science student at Hindusthan College of Engineering, Coimbatore — building real products since 2024.</p>
      <p>I specialise in AI-powered full-stack applications and have shipped production apps used by real businesses — from fintech collection tools to e-commerce storefronts handling live traffic.</p>
      <p>My work sits at the intersection of elegant UI, intelligent backend systems, and practical automation. I care deeply about performance, clean code, and products that actually solve problems.</p>
      <div class="about-stats">
        <div class="stat-card">
          <span class="stat-num">4+</span>
          <span class="stat-label">LIVE PROJECTS</span>
        </div>
        <div class="stat-card">
          <span class="stat-num">8.0</span>
          <span class="stat-label">CGPA</span>
        </div>
        <div class="stat-card">
          <span class="stat-num">3+</span>
          <span class="stat-label">E-COMMERCE SITES</span>
        </div>
        <div class="stat-card">
          <span class="stat-num">2024</span>
          <span class="stat-label">BUILDING SINCE</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-divider reveal" data-label="§ 02 / SKILLS"></div>
  <div class="section-eyebrow reveal">Tech Stack</div>
  <h2 class="section-title reveal">What I build with</h2>

  <div class="skills-grid reveal">
    <div class="skill-group">
      <div class="skill-group-label">Frontend</div>
      <div class="skill-pills">
        <span class="skill-pill">HTML5</span>
        <span class="skill-pill">CSS3</span>
        <span class="skill-pill">JavaScript</span>
        <span class="skill-pill">TypeScript</span>
        <span class="skill-pill">React</span>
        <span class="skill-pill">Tailwind</span>
        <span class="skill-pill">Vite</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-label">Mobile</div>
      <div class="skill-pills">
        <span class="skill-pill">React Native</span>
        <span class="skill-pill">Expo</span>
        <span class="skill-pill">Native CLI</span>
        <span class="skill-pill">Android</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-label">Backend &amp; DB</div>
      <div class="skill-pills">
        <span class="skill-pill">Node.js</span>
        <span class="skill-pill">Flask</span>
        <span class="skill-pill">Firebase</span>
        <span class="skill-pill">MongoDB</span>
        <span class="skill-pill">REST APIs</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-label">AI &amp; Automation</div>
      <div class="skill-pills">
        <span class="skill-pill">Python</span>
        <span class="skill-pill">TensorFlow</span>
        <span class="skill-pill">OpenCV</span>
        <span class="skill-pill">Gemini API</span>
        <span class="skill-pill">AES-256</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-label">SEO / AEO / GEO</div>
      <div class="skill-pills">
        <span class="skill-pill">Google Search Console</span>
        <span class="skill-pill">Bing Webmaster</span>
        <span class="skill-pill">Schema Markup</span>
        <span class="skill-pill">Core Web Vitals</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-label">Tools &amp; Design</div>
      <div class="skill-pills">
        <span class="skill-pill">Git</span>
        <span class="skill-pill">GitHub</span>
        <span class="skill-pill">Figma</span>
        <span class="skill-pill">Postman</span>
        <span class="skill-pill">VS Code</span>
      </div>
    </div>
  </div>

  <!-- Skill bars -->
  <div class="skill-bar-list reveal" style="margin-top:48px">
    <div class="skill-bar-row">
      <span class="skill-bar-name">React / RN</span>
      <div class="skill-bar-track"><div class="skill-bar-fill" data-pct="92"></div></div>
      <span class="skill-bar-pct">92%</span>
    </div>
    <div class="skill-bar-row">
      <span class="skill-bar-name">JavaScript</span>
      <div class="skill-bar-track"><div class="skill-bar-fill" data-pct="88"></div></div>
      <span class="skill-bar-pct">88%</span>
    </div>
    <div class="skill-bar-row">
      <span class="skill-bar-name">Python / Flask</span>
      <div class="skill-bar-track"><div class="skill-bar-fill red" data-pct="78"></div></div>
      <span class="skill-bar-pct">78%</span>
    </div>
    <div class="skill-bar-row">
      <span class="skill-bar-name">Firebase / DB</span>
      <div class="skill-bar-track"><div class="skill-bar-fill" data-pct="82"></div></div>
      <span class="skill-bar-pct">82%</span>
    </div>
    <div class="skill-bar-row">
      <span class="skill-bar-name">UI/UX (Figma)</span>
      <div class="skill-bar-track"><div class="skill-bar-fill red" data-pct="70"></div></div>
      <span class="skill-bar-pct">70%</span>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-divider reveal" data-label="§ 03 / PROJECTS"></div>
  <div class="section-eyebrow reveal">Projects</div>
  <h2 class="section-title reveal">Things I've built</h2>

  <div class="projects-list">

    <!-- Project 1: AI Chatbot -->
    <div class="project-card reveal">
      <div class="project-info">
        <div class="project-year">2024</div>
        <div class="project-name">AI Chatbot</div>
        <p class="project-desc">Cross-platform AI chatbot app with real-time intelligent conversations. Built using React Native and Flask backend, integrating Google's Gemini API for context-aware, natural responses across Android and iOS.</p>
        <div class="project-tags">
          <span class="project-tag">React Native</span>
          <span class="project-tag">Flask</span>
          <span class="project-tag">Gemini API</span>
          <span class="project-tag">Python</span>
        </div>
        <a href="https://github.com/Gopinath272006" target="_blank" class="project-link">View on GitHub →</a>
      </div>
      <div class="project-visual">
        <img src="https://images.unsplash.com/photo-1677442136019-21780ecad995?w=640&q=80&auto=format" alt="AI Chatbot visualization"/>
      </div>
    </div>

    <!-- Project 2: MARAI-X -->
    <div class="project-card reverse reveal">
      <div class="project-visual">
        <img src="https://images.unsplash.com/photo-1614064641938-3bbee52942c7?w=640&q=80&auto=format" alt="Encryption platform"/>
      </div>
      <div class="project-info">
        <div class="project-year">2025</div>
        <div class="project-name">MARAI-X</div>
        <p class="project-desc">Privacy-first client-side encryption platform. Zero-knowledge architecture — all encryption happens locally with AES-256. Secure encrypted containers with Android-based secure wipe protection. Your data never leaves your device.</p>
        <div class="project-tags">
          <span class="project-tag">React Native</span>
          <span class="project-tag">AES-256</span>
          <span class="project-tag">Android</span>
          <span class="project-tag">Cryptography</span>
        </div>
        <a href="https://github.com/Gopinath272006" target="_blank" class="project-link">View on GitHub →</a>
      </div>
    </div>

    <!-- Project 3: KG Finance -->
    <div class="project-card reveal">
      <div class="project-info">
        <div class="project-year">2026</div>
        <div class="project-name">KG-Finance</div>
        <p class="project-desc">Mobile-first loan collections management app for a real fintech client. Streamlines daily cash collections, payment tracking, overdue alerts, and customer account management for field agents.</p>
        <div class="project-tags">
          <span class="project-tag">React Native</span>
          <span class="project-tag">Firebase</span>
          <span class="project-tag">MongoDB</span>
          <span class="project-tag">FinTech</span>
        </div>
        <a href="https://github.com/Gopinath272006" target="_blank" class="project-link">View on GitHub →</a>
      </div>
      <div class="project-visual">
        <img src="https://images.unsplash.com/photo-1563013544-824ae1b704d3?w=640&q=80&auto=format" alt="Finance app"/>
      </div>
    </div>

  </div>

  <!-- E-commerce section -->
  <div style="margin-top:20px" class="reveal">
    <div class="section-eyebrow" style="margin-bottom:16px">E-Commerce Platforms — 2026</div>
    <p style="color:#555;font-size:14px;margin-bottom:28px;max-width:560px">Built three production e-commerce storefronts for real Tamil Nadu businesses. Full-featured: product catalog, cart, checkout, and order management using React + Tailwind + Vite + Firebase.</p>
    <div class="ecom-strip">
      <a href="https://kavinkrishnacrackers.in" target="_blank" class="ecom-card" style="text-decoration:none;color:inherit">
        <div class="ecom-icon">🎆</div>
        <div class="ecom-name">kavinkrishna<br/>crackers.in</div>
        <div class="ecom-stack">Crackers &amp; Fireworks</div>
      </a>
      <a href="https://thealankar.in" target="_blank" class="ecom-card" style="text-decoration:none;color:inherit">
        <div class="ecom-icon">💍</div>
        <div class="ecom-name">thealankar.in</div>
        <div class="ecom-stack">Fashion &amp; Jewellery</div>
      </a>
      <a href="https://kannanpattasukadai.in" target="_blank" class="ecom-card" style="text-decoration:none;color:inherit">
        <div class="ecom-icon">🛒</div>
        <div class="ecom-name">kannanpatta<br/>sukadai.in</div>
        <div class="ecom-stack">Retail Store</div>
      </a>
    </div>
  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="section-divider reveal" data-label="§ 04 / EDUCATION"></div>
  <div class="section-eyebrow reveal">Education</div>
  <h2 class="section-title reveal">Academic background</h2>

  <div class="edu-timeline reveal">
    <div class="edu-entry">
      <div class="edu-period">2023 → 2027</div>
      <div class="edu-degree">B.E. Computer Science &amp; Engineering</div>
      <div class="edu-institution">Hindusthan College of Engineering &amp; Technology, Coimbatore</div>
      <div class="edu-detail">Anna University affiliated. Currently in 3rd year with a consistent academic record.</div>
      <div class="cgpa-badge">CGPA : 8.0</div>
    </div>
    <div class="edu-entry">
      <div class="edu-period">2021 → 2023</div>
      <div class="edu-degree">Higher Secondary (HSC)</div>
      <div class="edu-institution">Sri Sankara Matriculation Higher Secondary School, Thiruvarur</div>
      <div class="edu-detail">Tamil Nadu State Board. HSC: 73% · SSLC: Pass</div>
    </div>
  </div>
</section>

<!-- CONNECT -->
<section id="connect">
  <div class="section-divider reveal" data-label="§ 05 / CONNECT"></div>
  <div class="section-eyebrow reveal">Connect</div>
  <h2 class="section-title reveal">Get in touch</h2>

  <div class="connect-grid reveal">
    <a href="https://gopinathk.me" target="_blank" class="connect-item">
      <div class="connect-icon">🌐</div>
      <div class="connect-text">
        <div class="connect-title">Portfolio</div>
        <div class="connect-label">gopinathk.me</div>
      </div>
    </a>
    <a href="https://github.com/Gopinath272006" target="_blank" class="connect-item">
      <div class="connect-icon">🐙</div>
      <div class="connect-text">
        <div class="connect-title">GitHub</div>
        <div class="connect-label">Gopinath272006</div>
      </div>
    </a>
    <a href="https://linkedin.com/in/gopinath-kanniyappan-626a372a4" target="_blank" class="connect-item">
      <div class="connect-icon">💼</div>
      <div class="connect-text">
        <div class="connect-title">LinkedIn</div>
        <div class="connect-label">gopinath-kanniyappan</div>
      </div>
    </a>
    <a href="mailto:gopinathkanniyappan27@gmail.com" class="connect-item">
      <div class="connect-icon">✉️</div>
      <div class="connect-text">
        <div class="connect-title">Email</div>
        <div class="connect-label">gopinathkanniyappan27@gmail.com</div>
      </div>
    </a>
    <a href="tel:+916382519502" class="connect-item" style="border-right:none">
      <div class="connect-icon">📞</div>
      <div class="connect-text">
        <div class="connect-title">Phone</div>
        <div class="connect-label">+91 6382519502</div>
      </div>
    </a>
    <div class="connect-item" style="border-right:none;cursor:default;background:var(--paper)">
      <div style="font-family:'Caveat',cursive;font-size:18px;color:var(--muted);text-align:center;width:100%">
        "Code. Design. Build. Repeat."
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-sig">Gopinath K</div>
  <div class="footer-meta">
    B.E. CSE · Anna University<br/>
    Coimbatore, Tamil Nadu<br/>
    © 2026 · gopinathk.me
  </div>
</footer>

</div><!-- /page -->

<script>
// Scroll reveal
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if(e.isIntersecting){
      e.target.classList.add('visible');
      // Animate skill bars inside
      e.target.querySelectorAll('.skill-bar-fill').forEach(bar => {
        setTimeout(() => { bar.style.width = bar.dataset.pct + '%'; }, 200);
      });
    }
  });
}, {threshold:0.1, rootMargin:'0px 0px -40px 0px'});

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

// Animate hero skill bars immediately if visible
document.querySelectorAll('.skill-bar-fill').forEach(bar => {
  const pct = bar.dataset.pct;
  if(pct) setTimeout(() => { bar.style.width = pct + '%'; }, 1200);
});

// Smooth nav highlight
const sections = document.querySelectorAll('section[id]');
const navLinks = document.querySelectorAll('.nav-links a');
window.addEventListener('scroll', () => {
  let current = '';
  sections.forEach(s => {
    if(window.scrollY >= s.offsetTop - 120) current = s.id;
  });
  navLinks.forEach(a => {
    a.style.color = a.getAttribute('href') === '#'+current ? 'var(--red)' : '';
  });
}, {passive:true});

// Parallax on hero portrait (subtle)
window.addEventListener('scroll', () => {
  const portrait = document.querySelector('.hero-portrait');
  if(portrait) portrait.style.transform = `translateY(${window.scrollY * 0.06}px)`;
}, {passive:true});
</script>
</body>
</html>
