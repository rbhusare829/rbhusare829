<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Rohit Bhusare — DevOps Portfolio Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Rajdhani:wght@300;500;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --cyan: #00fff2;
    --purple: #7b2fff;
    --pink: #ff00c8;
    --dark: #050505;
    --dark2: #0a0a12;
    --dark3: #0d0221;
    --glass: rgba(0,255,242,0.04);
    --glass-border: rgba(0,255,242,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--dark);
    color: #fff;
    font-family: 'Share Tech Mono', monospace;
    overflow-x: hidden;
    cursor: none;
  }

  /* CUSTOM CURSOR */
  .cursor {
    width: 20px; height: 20px;
    border: 2px solid var(--cyan);
    border-radius: 50%;
    position: fixed; pointer-events: none;
    transform: translate(-50%,-50%);
    transition: all 0.1s ease;
    z-index: 9999;
    box-shadow: 0 0 10px var(--cyan), 0 0 20px var(--cyan);
  }
  .cursor-dot {
    width: 5px; height: 5px;
    background: var(--pink);
    border-radius: 50%;
    position: fixed; pointer-events: none;
    transform: translate(-50%,-50%);
    z-index: 9999;
    box-shadow: 0 0 6px var(--pink);
  }

  /* ANIMATED BACKGROUND */
  .bg-grid {
    position: fixed; inset: 0;
    background-image:
      linear-gradient(rgba(0,255,242,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,242,0.03) 1px, transparent 1px);
    background-size: 50px 50px;
    animation: gridPulse 4s ease-in-out infinite alternate;
    z-index: 0;
  }
  @keyframes gridPulse {
    from { opacity: 0.5; }
    to { opacity: 1; }
  }

  /* FLOATING PARTICLES */
  .particles { position: fixed; inset: 0; z-index: 0; overflow: hidden; }
  .particle {
    position: absolute;
    border-radius: 50%;
    animation: floatUp linear infinite;
    opacity: 0;
  }
  @keyframes floatUp {
    0%   { transform: translateY(100vh) rotate(0deg); opacity: 0; }
    10%  { opacity: 1; }
    90%  { opacity: 0.6; }
    100% { transform: translateY(-100px) rotate(720deg); opacity: 0; }
  }

  /* SCANLINES */
  .scanlines {
    position: fixed; inset: 0; z-index: 1; pointer-events: none;
    background: repeating-linear-gradient(
      0deg, transparent, transparent 2px,
      rgba(0,0,0,0.08) 2px, rgba(0,0,0,0.08) 4px
    );
  }

  /* CORNER DECORATIONS */
  .corner { position: fixed; width: 60px; height: 60px; z-index: 5; }
  .corner-tl { top: 15px; left: 15px; border-top: 2px solid var(--cyan); border-left: 2px solid var(--cyan); }
  .corner-tr { top: 15px; right: 15px; border-top: 2px solid var(--pink); border-right: 2px solid var(--pink); }
  .corner-bl { bottom: 15px; left: 15px; border-bottom: 2px solid var(--purple); border-left: 2px solid var(--purple); }
  .corner-br { bottom: 15px; right: 15px; border-bottom: 2px solid var(--cyan); border-right: 2px solid var(--cyan); }

  /* CONTENT */
  .content { position: relative; z-index: 10; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    padding: 40px 20px;
    position: relative;
    text-align: center;
  }

  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 50%,
      rgba(123,47,255,0.12) 0%, transparent 70%);
  }

  .hero-glitch {
    font-family: 'Orbitron', monospace;
    font-size: clamp(42px, 7vw, 88px);
    font-weight: 900;
    color: var(--cyan);
    text-transform: uppercase;
    letter-spacing: 0.12em;
    line-height: 1;
    position: relative;
    text-shadow:
      0 0 10px var(--cyan),
      0 0 30px var(--cyan),
      0 0 60px rgba(0,255,242,0.4),
      0 0 100px rgba(0,255,242,0.2);
    animation: glitch 3s infinite;
  }
  @keyframes glitch {
    0%,94%,100% { transform: translate(0); filter: none; }
    95% { transform: translate(-3px, 2px); filter: hue-rotate(90deg); }
    96% { transform: translate(3px, -2px); text-shadow: -3px 0 var(--pink), 3px 0 var(--cyan); }
    97% { transform: translate(0); filter: none; }
    98% { transform: translate(2px, 1px); filter: brightness(1.5); }
    99% { transform: translate(-2px, -1px); filter: none; }
  }

  .hero-subtitle {
    font-family: 'Orbitron', monospace;
    font-size: clamp(12px, 2vw, 20px);
    color: rgba(255,255,255,0.6);
    letter-spacing: 0.35em;
    text-transform: uppercase;
    margin: 12px 0 30px;
  }

  .hero-role {
    font-family: 'Share Tech Mono', monospace;
    font-size: clamp(15px, 2.2vw, 22px);
    color: var(--pink);
    letter-spacing: 0.08em;
    text-shadow: 0 0 15px var(--pink), 0 0 30px rgba(255,0,200,0.4);
    margin-bottom: 10px;
  }

  /* TYPING LINE */
  .typing-line {
    font-family: 'Share Tech Mono', monospace;
    font-size: clamp(13px, 1.6vw, 18px);
    color: var(--cyan);
    opacity: 0.8;
    border-right: 2px solid var(--cyan);
    white-space: nowrap;
    overflow: hidden;
    animation: typeLoop 14s steps(40) infinite;
    max-width: 100%;
  }
  @keyframes typeLoop {
    0%,8% { width: 0; }
    18%,28% { width: 38ch; }
    36%,44% { width: 0; }
    50%,60% { width: 32ch; }
    68%,76% { width: 0; }
    82%,92% { width: 36ch; }
    100% { width: 0; }
  }

  /* NEON DIVIDER */
  .neon-divider {
    height: 2px;
    margin: 50px auto;
    max-width: 900px;
    background: linear-gradient(90deg,
      transparent 0%, var(--purple) 20%,
      var(--cyan) 50%, var(--pink) 80%, transparent 100%);
    box-shadow: 0 0 15px var(--cyan), 0 0 30px rgba(0,255,242,0.3);
    position: relative;
  }
  .neon-divider::before, .neon-divider::after {
    content: '◈';
    position: absolute; top: 50%;
    transform: translateY(-50%);
    color: var(--cyan);
    font-size: 18px;
    text-shadow: 0 0 10px var(--cyan);
  }
  .neon-divider::before { left: -10px; }
  .neon-divider::after  { right: -10px; }

  /* SECTION */
  section { padding: 60px 20px; max-width: 1100px; margin: 0 auto; }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: clamp(16px, 2.5vw, 26px);
    font-weight: 700;
    color: var(--cyan);
    text-transform: uppercase;
    letter-spacing: 0.2em;
    margin-bottom: 40px;
    display: flex; align-items: center; gap: 14px;
    text-shadow: 0 0 15px var(--cyan);
  }
  .section-title::before {
    content: '';
    width: 4px; height: 28px;
    background: linear-gradient(var(--cyan), var(--purple));
    border-radius: 2px;
    box-shadow: 0 0 10px var(--cyan);
  }
  .section-title::after {
    content: '';
    flex: 1; height: 1px;
    background: linear-gradient(90deg, var(--cyan), transparent);
    opacity: 0.4;
  }

  /* GLASS CARD */
  .glass-card {
    background: var(--glass);
    border: 1px solid var(--glass-border);
    border-radius: 16px;
    padding: 28px 32px;
    backdrop-filter: blur(12px);
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
  }
  .glass-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--cyan), transparent);
    opacity: 0.6;
  }
  .glass-card:hover {
    border-color: var(--cyan);
    box-shadow: 0 0 30px rgba(0,255,242,0.1), inset 0 0 30px rgba(0,255,242,0.03);
    transform: translateY(-3px);
  }

  /* TERMINAL */
  .terminal {
    background: #020202;
    border: 1px solid rgba(0,255,242,0.2);
    border-radius: 12px;
    overflow: hidden;
    font-family: 'Share Tech Mono', monospace;
  }
  .terminal-bar {
    background: #111;
    padding: 10px 16px;
    display: flex; gap: 8px; align-items: center;
    border-bottom: 1px solid rgba(0,255,242,0.1);
  }
  .t-dot { width: 12px; height: 12px; border-radius: 50%; }
  .t-red { background: #ff5f57; box-shadow: 0 0 6px #ff5f57; }
  .t-yellow { background: #ffbd2e; box-shadow: 0 0 6px #ffbd2e; }
  .t-green { background: #28c840; box-shadow: 0 0 6px #28c840; }
  .t-title {
    margin-left: auto; margin-right: auto;
    font-size: 12px; color: #555;
    font-family: 'Share Tech Mono', monospace;
  }
  .terminal-body { padding: 24px 28px; font-size: 14px; line-height: 1.8; }
  .t-prompt { color: var(--cyan); }
  .t-cmd { color: #fff; }
  .t-key { color: var(--pink); }
  .t-val { color: #a8ff78; }
  .t-str { color: #ffd700; }
  .t-comment { color: #555; }

  /* SKILLS */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 16px;
  }
  .skill-item {
    background: rgba(0,255,242,0.03);
    border: 1px solid rgba(0,255,242,0.1);
    border-radius: 10px;
    padding: 16px 20px;
    transition: all 0.3s;
  }
  .skill-item:hover {
    border-color: rgba(0,255,242,0.4);
    transform: translateX(4px);
  }
  .skill-header {
    display: flex; justify-content: space-between;
    margin-bottom: 10px; font-size: 14px;
  }
  .skill-name { color: #fff; font-weight: 600; }
  .skill-pct { color: var(--cyan); font-family: 'Orbitron', monospace; font-size: 13px; }
  .skill-bar-bg {
    height: 6px; background: rgba(255,255,255,0.06);
    border-radius: 3px; overflow: hidden;
  }
  .skill-bar-fill {
    height: 100%; border-radius: 3px;
    position: relative; animation: barGrow 1.5s ease forwards;
    transform-origin: left;
  }
  @keyframes barGrow { from { width: 0 !important; } }
  .bar-cyan  { background: linear-gradient(90deg, var(--purple), var(--cyan)); box-shadow: 0 0 8px var(--cyan); }
  .bar-pink  { background: linear-gradient(90deg, var(--purple), var(--pink)); box-shadow: 0 0 8px var(--pink); }
  .bar-green { background: linear-gradient(90deg, var(--cyan), #00ff88); box-shadow: 0 0 8px #00ff88; }

  /* TOOLS GRID */
  .tools-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
    gap: 14px;
  }
  .tool-chip {
    background: rgba(0,255,242,0.04);
    border: 1px solid rgba(0,255,242,0.12);
    border-radius: 10px;
    padding: 14px 10px;
    text-align: center;
    font-size: 12px;
    color: rgba(255,255,255,0.75);
    transition: all 0.3s ease;
    cursor: default;
    letter-spacing: 0.05em;
  }
  .tool-chip:hover {
    background: rgba(0,255,242,0.1);
    border-color: var(--cyan);
    color: var(--cyan);
    transform: translateY(-4px);
    box-shadow: 0 8px 25px rgba(0,255,242,0.15);
  }
  .tool-icon { font-size: 26px; display: block; margin-bottom: 6px; }

  /* STATS GRID */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
  }
  .stat-card {
    background: rgba(0,255,242,0.03);
    border: 1px solid rgba(0,255,242,0.12);
    border-radius: 14px;
    padding: 24px 20px;
    text-align: center;
    transition: all 0.3s;
  }
  .stat-card:hover {
    border-color: var(--cyan);
    box-shadow: 0 0 25px rgba(0,255,242,0.12);
    transform: scale(1.03);
  }
  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 36px; font-weight: 900;
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .stat-label { font-size: 11px; color: #555; letter-spacing: 0.15em; margin-top: 6px; }

  /* PROJECTS TABLE */
  .proj-table { width: 100%; border-collapse: collapse; font-size: 13px; }
  .proj-table th {
    font-family: 'Orbitron', monospace;
    font-size: 11px; letter-spacing: 0.15em;
    color: var(--cyan); text-align: left;
    padding: 12px 16px; border-bottom: 1px solid rgba(0,255,242,0.2);
    background: rgba(0,255,242,0.03);
  }
  .proj-table td { padding: 14px 16px; border-bottom: 1px solid rgba(255,255,255,0.04); color: rgba(255,255,255,0.8); }
  .proj-table tr:hover td { background: rgba(0,255,242,0.03); color: #fff; }
  .proj-rank { font-family: 'Orbitron', monospace; font-size: 15px; }
  .proj-name { color: var(--cyan); font-weight: 600; }
  .badge-live   { background: rgba(0,255,136,0.15); color: #00ff88; border: 1px solid #00ff88; padding: 3px 10px; border-radius: 20px; font-size: 10px; letter-spacing: 0.1em; }
  .badge-active { background: rgba(0,255,242,0.1); color: var(--cyan); border: 1px solid var(--cyan); padding: 3px 10px; border-radius: 20px; font-size: 10px; }
  .badge-flag   { background: rgba(255,0,200,0.15); color: var(--pink); border: 1px solid var(--pink); padding: 3px 10px; border-radius: 20px; font-size: 10px; }

  /* CONNECT */
  .connect-grid { display: flex; flex-wrap: wrap; gap: 14px; justify-content: center; }
  .social-btn {
    display: flex; align-items: center; gap: 10px;
    padding: 14px 24px;
    border-radius: 10px; font-size: 14px; font-family: 'Orbitron', monospace;
    font-weight: 700; letter-spacing: 0.08em;
    text-decoration: none; border: 1px solid;
    transition: all 0.3s ease; cursor: pointer;
    text-transform: uppercase;
  }
  .btn-linkedin { color: #0A66C2; border-color: #0A66C2; background: rgba(10,102,194,0.08); }
  .btn-linkedin:hover { background: rgba(10,102,194,0.2); box-shadow: 0 0 20px rgba(10,102,194,0.3); transform: translateY(-3px); }
  .btn-gmail  { color: #EA4335; border-color: #EA4335; background: rgba(234,67,53,0.08); }
  .btn-gmail:hover  { background: rgba(234,67,53,0.2); box-shadow: 0 0 20px rgba(234,67,53,0.3); transform: translateY(-3px); }
  .btn-github { color: var(--cyan); border-color: var(--cyan); background: rgba(0,255,242,0.05); }
  .btn-github:hover { background: rgba(0,255,242,0.15); box-shadow: 0 0 20px rgba(0,255,242,0.25); transform: translateY(-3px); }
  .btn-port   { color: var(--pink); border-color: var(--pink); background: rgba(255,0,200,0.05); }
  .btn-port:hover   { background: rgba(255,0,200,0.15); box-shadow: 0 0 20px rgba(255,0,200,0.25); transform: translateY(-3px); }

  /* FOOTER */
  .footer {
    text-align: center; padding: 60px 20px 40px;
    background: linear-gradient(0deg, rgba(0,255,242,0.04), transparent);
    border-top: 1px solid rgba(0,255,242,0.08);
    font-size: 13px; color: #444; letter-spacing: 0.1em;
    position: relative; z-index: 10;
  }
  .footer-motto {
    font-family: 'Orbitron', monospace;
    font-size: clamp(13px, 2vw, 18px);
    color: var(--cyan); margin-bottom: 10px;
    text-shadow: 0 0 20px var(--cyan);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.6; } }

  /* SCROLL */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--dark); }
  ::-webkit-scrollbar-thumb { background: var(--cyan); border-radius: 2px; }

  /* BADGE ROW */
  .badges { display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; margin: 20px 0; }
  .nbadge {
    padding: 6px 16px; border-radius: 20px; font-size: 12px;
    font-family: 'Share Tech Mono', monospace; letter-spacing: 0.1em;
    border: 1px solid; animation: badgePulse 3s ease-in-out infinite;
  }
  .nb-cyan  { color: var(--cyan); border-color: var(--cyan); background: rgba(0,255,242,0.06); }
  .nb-pink  { color: var(--pink); border-color: var(--pink); background: rgba(255,0,200,0.06); animation-delay: 1s; }
  .nb-purple{ color: #a78bff; border-color: #7b2fff; background: rgba(123,47,255,0.08); animation-delay: 2s; }
  @keyframes badgePulse { 0%,100% { box-shadow: none; } 50% { box-shadow: 0 0 12px currentColor; } }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-dot" id="cursorDot"></div>
<div class="bg-grid"></div>
<div class="particles" id="particles"></div>
<div class="scanlines"></div>
<div class="corner corner-tl"></div>
<div class="corner corner-tr"></div>
<div class="corner corner-bl"></div>
<div class="corner corner-br"></div>

<div class="content">

  <!-- ── HERO ── -->
  <div class="hero">
    <div class="hero-glitch">ROHIT BHUSARE</div>
    <div class="hero-subtitle">◈ &nbsp; rbhusare829 &nbsp; ◈ &nbsp; Maharashtra, India &nbsp; ◈</div>
    <div class="hero-role">⚡ Senior DevOps Engineer &nbsp;|&nbsp; AWS Cloud Architect &nbsp;|&nbsp; Automation Wizard ⚡</div>
    <div style="height:8px"></div>
    <div class="typing-line">🚀 Deploying to Production... Automating Everything...</div>
    <div style="height:32px"></div>
    <div class="badges">
      <span class="nbadge nb-cyan">☁️ AWS Cloud</span>
      <span class="nbadge nb-pink">🐳 Docker & K8s</span>
      <span class="nbadge nb-purple">🏗️ Terraform IaC</span>
      <span class="nbadge nb-cyan">🔁 Jenkins CI/CD</span>
      <span class="nbadge nb-pink">🛡️ DevSecOps</span>
      <span class="nbadge nb-purple">📊 Prometheus + Grafana</span>
    </div>
  </div>

  <div class="neon-divider"></div>

  <!-- ── ABOUT ── -->
  <section>
    <div class="section-title">System Profile — whoami</div>
    <div class="terminal">
      <div class="terminal-bar">
        <div class="t-dot t-red"></div>
        <div class="t-dot t-yellow"></div>
        <div class="t-dot t-green"></div>
        <div class="t-title">rbhusare829@devops-city:~$ bash</div>
      </div>
      <div class="terminal-body">
        <div><span class="t-prompt">$ </span><span class="t-cmd">cat /etc/profile.json</span></div>
        <br/>
        <div><span class="t-comment">// ── IDENTITY ──────────────────────────────────────────</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"name"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-comment">:</span> <span class="t-str">"Rohit Bhusare"</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"role"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-comment">:</span> <span class="t-str">"Senior DevOps Engineer | Cloud Architect"</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"location"</span>&nbsp;&nbsp;<span class="t-comment">:</span> <span class="t-str">"Maharashtra, India 🇮🇳"</span></div>
        <br/>
        <div><span class="t-comment">// ── STACK ──────────────────────────────────────────────</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"cloud"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-comment">:</span> <span class="t-val">[ EC2, EKS, Lambda, RDS, S3, VPC, IAM, CDN ]</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"iac"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-comment">:</span> <span class="t-val">[ Terraform, Ansible, CDK, CloudFormation ]</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"containers"</span><span class="t-comment">:</span> <span class="t-val">[ Docker, Kubernetes, Helm, ECS, Fargate ]</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"cicd"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-comment">:</span> <span class="t-val">[ Jenkins, GitHub Actions, ArgoCD, GitLab ]</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"monitoring"</span><span class="t-comment">:</span> <span class="t-val">[ Prometheus, Grafana, ELK Stack, CloudWatch ]</span></div>
        <div>&nbsp;&nbsp;<span class="t-key">"languages"</span> <span class="t-comment">:</span> <span class="t-val">[ Python, Bash, YAML, HCL, Node.js ]</span></div>
        <br/>
        <div><span class="t-prompt">$ </span><span class="t-cmd">echo $PHILOSOPHY</span></div>
        <div><span style="color:#a8ff78">▶ "⚡ Automate Everything. Break Nothing. Ship Fast."</span></div>
        <br/>
        <div><span class="t-prompt">$ </span><span class="t-cmd">echo $STATUS</span></div>
        <div><span style="color:#00ff88">▶ 🟢 ONLINE — Available for Cloud Projects & Consulting</span></div>
      </div>
    </div>
  </section>

  <div class="neon-divider"></div>

  <!-- ── TOOLS ── -->
  <section>
    <div class="section-title">Tech Arsenal</div>
    <div class="tools-grid">
      <div class="tool-chip"><span class="tool-icon">☁️</span>AWS</div>
      <div class="tool-chip"><span class="tool-icon">🐳</span>Docker</div>
      <div class="tool-chip"><span class="tool-icon">☸️</span>Kubernetes</div>
      <div class="tool-chip"><span class="tool-icon">🏗️</span>Terraform</div>
      <div class="tool-chip"><span class="tool-icon">🔁</span>Jenkins</div>
      <div class="tool-chip"><span class="tool-icon">🐧</span>Linux</div>
      <div class="tool-chip"><span class="tool-icon">🔀</span>Git</div>
      <div class="tool-chip"><span class="tool-icon">🌐</span>Nginx</div>
      <div class="tool-chip"><span class="tool-icon">📦</span>Ansible</div>
      <div class="tool-chip"><span class="tool-icon">⚙️</span>GitHub Actions</div>
      <div class="tool-chip"><span class="tool-icon">📊</span>Prometheus</div>
      <div class="tool-chip"><span class="tool-icon">📈</span>Grafana</div>
      <div class="tool-chip"><span class="tool-icon">📋</span>ELK Stack</div>
      <div class="tool-chip"><span class="tool-icon">🐍</span>Python</div>
      <div class="tool-chip"><span class="tool-icon">🛡️</span>SonarQube</div>
      <div class="tool-chip"><span class="tool-icon">🔐</span>Vault</div>
    </div>
  </section>

  <div class="neon-divider"></div>

  <!-- ── SKILLS ── -->
  <section>
    <div class="section-title">Skill Matrix</div>
    <div class="skills-grid">
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">☁️ AWS Cloud</span><span class="skill-pct">90%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-cyan" style="width:90%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">🐧 Linux / Shell</span><span class="skill-pct">90%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-green" style="width:90%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">🐳 Docker</span><span class="skill-pct">85%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-cyan" style="width:85%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">🔁 CI/CD Pipelines</span><span class="skill-pct">85%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-pink" style="width:85%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">☸️ Kubernetes / EKS</span><span class="skill-pct">78%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-cyan" style="width:78%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">🏗️ Terraform</span><span class="skill-pct">72%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-pink" style="width:72%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">🐍 Python</span><span class="skill-pct">72%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-green" style="width:72%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">📦 Ansible</span><span class="skill-pct">68%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-cyan" style="width:68%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">📊 Prometheus + Grafana</span><span class="skill-pct">65%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-pink" style="width:65%"></div></div>
      </div>
      <div class="skill-item">
        <div class="skill-header"><span class="skill-name">🛡️ DevSecOps</span><span class="skill-pct">60%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill bar-green" style="width:60%"></div></div>
      </div>
    </div>
  </section>

  <div class="neon-divider"></div>

  <!-- ── PROJECTS ── -->
  <section>
    <div class="section-title">Top 10 DevOps Projects</div>
    <div class="glass-card">
      <table class="proj-table">
        <thead>
          <tr>
            <th>#</th><th>Project</th><th>Description</th><th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr><td class="proj-rank">🥇</td><td class="proj-name">AWS Infrastructure Automation</td><td>Modular Terraform — VPC, EC2, RDS, S3, IAM</td><td><span class="badge-live">LIVE</span></td></tr>
          <tr><td class="proj-rank">🥈</td><td class="proj-name">Jenkins CI/CD Mega Pipeline</td><td>Code→SAST→Build→Scan→ECR→EKS deploy</td><td><span class="badge-live">LIVE</span></td></tr>
          <tr><td class="proj-rank">🥉</td><td class="proj-name">Kubernetes Microservices</td><td>EKS prod — HPA, RBAC, Ingress, Helm charts</td><td><span class="badge-live">LIVE</span></td></tr>
          <tr><td class="proj-rank">4️⃣</td><td class="proj-name">Dockerized App Deployment</td><td>Multi-container — Docker Compose, Nginx SSL</td><td><span class="badge-live">LIVE</span></td></tr>
          <tr><td class="proj-rank">5️⃣</td><td class="proj-name">GitHub Actions CI/CD</td><td>Automated build, test, security, deploy</td><td><span class="badge-active">ACTIVE</span></td></tr>
          <tr><td class="proj-rank">6️⃣</td><td class="proj-name">Prometheus + Grafana Stack</td><td>Full K8s observability + Alertmanager</td><td><span class="badge-active">ACTIVE</span></td></tr>
          <tr><td class="proj-rank">7️⃣</td><td class="proj-name">ELK Logging Platform</td><td>Centralized — Elasticsearch, Logstash, Kibana</td><td><span class="badge-active">ACTIVE</span></td></tr>
          <tr><td class="proj-rank">8️⃣</td><td class="proj-name">Nginx Reverse Proxy Infra</td><td>SSL/TLS, rate limiting, WAF, Certbot</td><td><span class="badge-active">ACTIVE</span></td></tr>
          <tr><td class="proj-rank">9️⃣</td><td class="proj-name">Auto Scaling Architecture</td><td>AWS ASG + CloudWatch metrics + Spot instances</td><td><span class="badge-active">ACTIVE</span></td></tr>
          <tr><td class="proj-rank">🔟</td><td class="proj-name">End-to-End DevOps Platform</td><td>Full GitOps — Git→Jenkins→ECR→EKS→Monitor</td><td><span class="badge-flag">FLAGSHIP</span></td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <div class="neon-divider"></div>

  <!-- ── STATS ── -->
  <section>
    <div class="section-title">GitHub Stats</div>
    <div class="stats-grid">
      <div class="stat-card"><div class="stat-num" id="c1">0</div><div class="stat-label">TOTAL COMMITS</div></div>
      <div class="stat-card"><div class="stat-num" id="c2">0</div><div class="stat-label">REPOSITORIES</div></div>
      <div class="stat-card"><div class="stat-num" id="c3">0</div><div class="stat-label">PULL REQUESTS</div></div>
      <div class="stat-card"><div class="stat-num" id="c4">0</div><div class="stat-label">ISSUES SOLVED</div></div>
      <div class="stat-card"><div class="stat-num" id="c5">0</div><div class="stat-label">CONTRIBUTIONS</div></div>
      <div class="stat-card"><div class="stat-num" id="c6">0</div><div class="stat-label">FOLLOWERS</div></div>
    </div>
    <br/>
    <div style="text-align:center;opacity:0.5;font-size:13px;">
      Live GitHub widgets load on GitHub — visit <strong style="color:var(--cyan)">github.com/rbhusare829</strong> to see real stats
    </div>
  </section>

  <div class="neon-divider"></div>

  <!-- ── CONNECT ── -->
  <section>
    <div class="section-title">Connect — Let's Build Together</div>
    <div class="connect-grid">
      <a class="social-btn btn-linkedin" href="https://linkedin.com/in/rohit-bhusare" target="_blank">💼 LinkedIn</a>
      <a class="social-btn btn-gmail" href="mailto:rbhusare829@gmail.com">📧 Gmail</a>
      <a class="social-btn btn-github" href="https://github.com/rbhusare829" target="_blank">🐙 GitHub</a>
      <a class="social-btn btn-port" href="https://rbhusare829.github.io" target="_blank">🌐 Portfolio</a>
    </div>
  </section>

  <!-- ── FOOTER ── -->
  <div class="footer">
    <div class="footer-motto">⚡ AUTOMATE EVERYTHING. BREAK NOTHING. SHIP FAST. ⚡</div>
    <div>rbhusare829 &nbsp;◈&nbsp; DevOps Engineer &nbsp;◈&nbsp; Maharashtra, India 🇮🇳</div>
    <br/>
    <div>Built with ⚡ passion for cloud engineering & automation</div>
  </div>

</div>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const dot = document.getElementById('cursorDot');
  document.addEventListener('mousemove', e => {
    cursor.style.left = e.clientX + 'px';
    cursor.style.top = e.clientY + 'px';
    dot.style.left = e.clientX + 'px';
    dot.style.top = e.clientY + 'px';
  });

  // Floating particles
  const colors = ['#00fff2','#7b2fff','#ff00c8','#ffffff'];
  const container = document.getElementById('particles');
  for (let i = 0; i < 50; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    const size = Math.random() * 4 + 1;
    p.style.cssText = `
      width:${size}px; height:${size}px;
      left:${Math.random()*100}%;
      background:${colors[Math.floor(Math.random()*colors.length)]};
      animation-duration:${Math.random()*15+8}s;
      animation-delay:${Math.random()*10}s;
      box-shadow: 0 0 ${size*3}px currentColor;
    `;
    container.appendChild(p);
  }

  // Counter animation
  function animateCounter(id, target, suffix='') {
    let start = 0;
    const el = document.getElementById(id);
    const dur = 2000;
    const step = target / (dur / 16);
    const timer = setInterval(() => {
      start = Math.min(start + step, target);
      el.textContent = Math.floor(start) + suffix;
      if (start >= target) clearInterval(timer);
    }, 16);
  }
  setTimeout(() => {
    animateCounter('c1', 847, '+');
    animateCounter('c2', 32, '');
    animateCounter('c3', 156, '+');
    animateCounter('c4', 94, '+');
    animateCounter('c5', 1200, '+');
    animateCounter('c6', 48, '');
  }, 500);
</script>
</body>
</html>
