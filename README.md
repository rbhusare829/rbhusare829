<!-- ============================================================
     ROHIT BHUSARE — ULTRA PREMIUM GITHUB PROFILE README
     ============================================================ -->

<!-- ANIMATED HEADER SVG — PREMIUM NAME + TITLE -->
<div align="center">

<svg width="900" height="280" viewBox="0 0 900 280" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <!-- Background gradient -->
    <linearGradient id="bgGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#020817;stop-opacity:1" />
      <stop offset="50%" style="stop-color:#0a0f1e;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#020817;stop-opacity:1" />
    </linearGradient>
    <!-- Cyan glow gradient for name -->
    <linearGradient id="nameGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#00f5ff" />
      <stop offset="40%" style="stop-color:#ffffff" />
      <stop offset="100%" style="stop-color:#00d4ff" />
    </linearGradient>
    <!-- Subtitle gradient -->
    <linearGradient id="subGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#00d4ff" />
      <stop offset="100%" style="stop-color:#7fb3ff" />
    </linearGradient>
    <!-- Glow filter for name -->
    <filter id="nameGlow" x="-20%" y="-50%" width="140%" height="200%">
      <feGaussianBlur stdDeviation="4" result="blur1"/>
      <feGaussianBlur stdDeviation="10" result="blur2"/>
      <feMerge>
        <feMergeNode in="blur2"/>
        <feMergeNode in="blur1"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
    <!-- Star glow filter -->
    <filter id="starGlow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
    <!-- Particle filter -->
    <filter id="particleGlow">
      <feGaussianBlur stdDeviation="2" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <!-- Background -->
  <rect width="900" height="280" fill="url(#bgGrad)" rx="16"/>

  <!-- Grid lines (subtle tech grid) -->
  <g opacity="0.06" stroke="#00d4ff" stroke-width="0.5">
    <line x1="0" y1="56" x2="900" y2="56"/>
    <line x1="0" y1="112" x2="900" y2="112"/>
    <line x1="0" y1="168" x2="900" y2="168"/>
    <line x1="0" y1="224" x2="900" y2="224"/>
    <line x1="150" y1="0" x2="150" y2="280"/>
    <line x1="300" y1="0" x2="300" y2="280"/>
    <line x1="450" y1="0" x2="450" y2="280"/>
    <line x1="600" y1="0" x2="600" y2="280"/>
    <line x1="750" y1="0" x2="750" y2="280"/>
  </g>

  <!-- Floating particles -->
  <g fill="#00d4ff" filter="url(#particleGlow)">
    <circle cx="80" cy="60" r="2" opacity="0.7">
      <animate attributeName="cy" values="60;40;60" dur="4s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.7;0.2;0.7" dur="4s" repeatCount="indefinite"/>
    </circle>
    <circle cx="820" cy="80" r="1.5" opacity="0.6">
      <animate attributeName="cy" values="80;55;80" dur="5s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.6;0.1;0.6" dur="5s" repeatCount="indefinite"/>
    </circle>
    <circle cx="160" cy="200" r="2.5" opacity="0.5">
      <animate attributeName="cy" values="200;180;200" dur="6s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.5;0.15;0.5" dur="6s" repeatCount="indefinite"/>
    </circle>
    <circle cx="740" cy="220" r="2" opacity="0.6">
      <animate attributeName="cy" values="220;200;220" dur="3.5s" repeatCount="indefinite"/>
    </circle>
    <circle cx="450" cy="30" r="1.5" opacity="0.8">
      <animate attributeName="cx" values="450;470;450" dur="7s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.8;0.3;0.8" dur="7s" repeatCount="indefinite"/>
    </circle>
    <circle cx="50" cy="150" r="1.8" opacity="0.5">
      <animate attributeName="cx" values="50;70;50" dur="5.5s" repeatCount="indefinite"/>
    </circle>
    <circle cx="860" cy="170" r="2" opacity="0.6">
      <animate attributeName="cy" values="170;145;170" dur="4.5s" repeatCount="indefinite"/>
    </circle>
  </g>

  <!-- Left decorative accent line -->
  <rect x="40" y="70" width="3" height="140" rx="2" fill="url(#nameGrad)" opacity="0.8">
    <animate attributeName="height" values="0;140;140" dur="1.2s" fill="freeze" begin="0.3s"/>
    <animate attributeName="y" values="140;70;70" dur="1.2s" fill="freeze" begin="0.3s"/>
  </rect>

  <!-- Right decorative accent line -->
  <rect x="857" y="70" width="3" height="140" rx="2" fill="url(#nameGrad)" opacity="0.8">
    <animate attributeName="height" values="0;140;140" dur="1.2s" fill="freeze" begin="0.5s"/>
    <animate attributeName="y" values="140;70;70" dur="1.2s" fill="freeze" begin="0.5s"/>
  </rect>

  <!-- Top horizontal accent -->
  <rect x="60" y="38" width="780" height="1.5" rx="1" fill="url(#nameGrad)" opacity="0.3">
    <animate attributeName="width" values="0;780" dur="1s" fill="freeze" begin="0.1s"/>
  </rect>

  <!-- Bottom horizontal accent -->
  <rect x="60" y="240" width="780" height="1.5" rx="1" fill="url(#nameGrad)" opacity="0.3">
    <animate attributeName="width" values="0;780" dur="1s" fill="freeze" begin="0.1s"/>
  </rect>

  <!-- Corner decorations -->
  <g stroke="#00d4ff" stroke-width="2" fill="none" opacity="0.6">
    <!-- Top left -->
    <polyline points="55,55 55,42 68,42">
      <animate attributeName="opacity" values="0;0.6" dur="0.8s" fill="freeze"/>
    </polyline>
    <!-- Top right -->
    <polyline points="845,55 845,42 832,42">
      <animate attributeName="opacity" values="0;0.6" dur="0.8s" fill="freeze"/>
    </polyline>
    <!-- Bottom left -->
    <polyline points="55,225 55,238 68,238">
      <animate attributeName="opacity" values="0;0.6" dur="0.8s" fill="freeze"/>
    </polyline>
    <!-- Bottom right -->
    <polyline points="845,225 845,238 832,238">
      <animate attributeName="opacity" values="0;0.6" dur="0.8s" fill="freeze"/>
    </polyline>
  </g>

  <!-- Small stars / sparkles -->
  <g filter="url(#starGlow)" fill="#00d4ff">
    <polygon points="100,90 103,100 113,100 105,106 108,116 100,110 92,116 95,106 87,100 97,100" opacity="0">
      <animate attributeName="opacity" values="0;0.5;0" dur="3s" begin="1s" repeatCount="indefinite"/>
    </polygon>
    <polygon points="800,90 802,96 808,96 803,100 805,106 800,102 795,106 797,100 792,96 798,96" opacity="0">
      <animate attributeName="opacity" values="0;0.5;0" dur="4s" begin="2s" repeatCount="indefinite"/>
    </polygon>
    <polygon points="200,210 202,216 208,216 203,220 205,226 200,222 195,226 197,220 192,216 198,216" opacity="0">
      <animate attributeName="opacity" values="0;0.4;0" dur="3.5s" begin="1.5s" repeatCount="indefinite"/>
    </polygon>
    <polygon points="700,210 702,216 708,216 703,220 705,226 700,222 695,226 697,220 692,216 698,216" opacity="0">
      <animate attributeName="opacity" values="0;0.4;0" dur="5s" begin="0.5s" repeatCount="indefinite"/>
    </polygon>
  </g>

  <!-- MAIN NAME — ROHIT BHUSARE (Premium large) -->
  <text
    x="450" y="150"
    text-anchor="middle"
    font-family="'Georgia', 'Times New Roman', serif"
    font-size="72"
    font-weight="bold"
    letter-spacing="8"
    fill="url(#nameGrad)"
    filter="url(#nameGlow)"
    opacity="0">
    ROHIT BHUSARE
    <animate attributeName="opacity" values="0;1" dur="1.5s" fill="freeze" begin="0.6s"/>
    <animateTransform attributeName="transform" type="translate" values="0,20;0,0" dur="1.5s" fill="freeze" begin="0.6s"/>
  </text>

  <!-- Subtle name shadow/echo -->
  <text
    x="452" y="152"
    text-anchor="middle"
    font-family="'Georgia', 'Times New Roman', serif"
    font-size="72"
    font-weight="bold"
    letter-spacing="8"
    fill="none"
    stroke="#00d4ff"
    stroke-width="0.5"
    opacity="0.15">
    ROHIT BHUSARE
  </text>

  <!-- Subtitle: DevOps Engineer -->
  <text
    x="450" y="192"
    text-anchor="middle"
    font-family="'Courier New', monospace"
    font-size="18"
    letter-spacing="6"
    fill="url(#subGrad)"
    opacity="0">
    ◆  D E V O P S   E N G I N E E R  ◆
    <animate attributeName="opacity" values="0;0.9" dur="1s" fill="freeze" begin="1.5s"/>
    <animateTransform attributeName="transform" type="translate" values="0,10;0,0" dur="1s" fill="freeze" begin="1.5s"/>
  </text>

  <!-- Tag line -->
  <text
    x="450" y="222"
    text-anchor="middle"
    font-family="'Courier New', monospace"
    font-size="13"
    letter-spacing="3"
    fill="#4a9eff"
    opacity="0">
    AWS  ·  Terraform  ·  Docker  ·  CI/CD  ·  Ansible
    <animate attributeName="opacity" values="0;0.7" dur="1s" fill="freeze" begin="2s"/>
  </text>

  <!-- Location badge -->
  <text
    x="450" y="256"
    text-anchor="middle"
    font-family="'Courier New', monospace"
    font-size="11"
    letter-spacing="2"
    fill="#3a7acc"
    opacity="0">
    📍 Pune, Maharashtra, India
    <animate attributeName="opacity" values="0;0.6" dur="1s" fill="freeze" begin="2.3s"/>
  </text>

  <!-- Scanning line animation (tech effect) -->
  <rect x="60" y="70" width="780" height="2" fill="#00d4ff" opacity="0">
    <animate attributeName="y" values="70;210;70" dur="4s" repeatCount="indefinite" begin="2.5s"/>
    <animate attributeName="opacity" values="0;0.15;0" dur="4s" repeatCount="indefinite" begin="2.5s"/>
  </rect>
</svg>

<!-- Animated Typing Roles -->
<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Courier+Prime&weight=700&size=22&duration=2800&pause=600&color=00D4FF&center=true&vCenter=true&width=700&lines=🚀+Building+Cloud+Infrastructure+at+Scale;☁️+AWS+%7C+EC2+%7C+VPC+%7C+IAM+%7C+S3;🔧+Infrastructure+as+Code+with+Terraform;🐳+Containerizing+Apps+with+Docker;⚙️+Automating+Everything+with+Ansible;🔁+CI%2FCD+Pipelines+with+Jenkins+%26+GitHub;📊+Monitoring+with+Prometheus+%26+Grafana" alt="Typing SVG" />
</a>

<br/>

<!-- Profile Views & Badges -->
<p>
  <img src="https://komarev.com/ghpvc/?username=rbhusare829&label=👁️+Profile+Views&color=00d4ff&style=for-the-badge&labelColor=0a0f1e" />
  <img src="https://img.shields.io/badge/Status-Open_to_Opportunities-00d4ff?style=for-the-badge&labelColor=0a0f1e&logo=checkmarx&logoColor=00d4ff" />
</p>

</div>

---

<div align="center">

## `< About Me />`

</div>

```yaml
╔══════════════════════════════════════════════════════════════╗
║                    ROHIT BHUSARE                             ║
║──────────────────────────────────────────────────────────────║
║  Role      →  DevOps Engineer (Fresher / Learner)           ║
║  Location  →  📍 Pune, Maharashtra, India                    ║
║  Focus     →  Cloud Automation & Infrastructure              ║
║  Learning  →  AWS Solutions Architect | Kubernetes | GitOps  ║
║  Passion   →  Automate everything. Scale everything.         ║
║  Goal      →  Break nothing in production 🔥                 ║
╚══════════════════════════════════════════════════════════════╝
```

> *"The best DevOps engineers make the complex look effortlessly simple."*

---

## ⚡ Tech Arsenal

<div align="center">

### ☁️ Cloud & AWS Services
![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![EC2](https://img.shields.io/badge/EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=black)
![S3](https://img.shields.io/badge/S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white)
![VPC](https://img.shields.io/badge/VPC-232F3E?style=for-the-badge&logo=amazonaws&logoColor=FF9900)
![IAM](https://img.shields.io/badge/IAM-DD344C?style=for-the-badge&logo=amazonaws&logoColor=white)
![CloudWatch](https://img.shields.io/badge/CloudWatch-FF4F8B?style=for-the-badge&logo=amazonaws&logoColor=white)

### 🏗️ Infrastructure as Code
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)

### 🐳 Containers & Orchestration
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)

### 🔁 CI/CD & Source Control
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

### 🖥️ OS & Scripting
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### 📊 Monitoring & Observability
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

</div>

---

## 📊 GitHub Analytics

<div align="center">

<img width="49%" src="https://github-readme-stats.vercel.app/api?username=rbhusare829&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0a0f1e&title_color=00d4ff&icon_color=00d4ff&text_color=c9d1d9&ring_color=00d4ff&border_radius=12" />
<img width="49%" src="https://github-readme-streak-stats.herokuapp.com/?user=rbhusare829&theme=tokyonight&hide_border=true&background=0a0f1e&ring=00d4ff&fire=ff6b6b&currStreakLabel=00d4ff&sideLabels=00d4ff&dates=7fb3ff&border_radius=12" />

<img width="49%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=rbhusare829&layout=compact&theme=tokyonight&hide_border=true&bg_color=0a0f1e&title_color=00d4ff&text_color=c9d1d9&border_radius=12" />

</div>

---

## 🏆 Achievements

<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=rbhusare829&theme=tokyonight&no-frame=true&no-bg=true&margin-w=8&column=7" />
</div>

---

## 📈 Contribution Graph

<div align="center">
  <img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=rbhusare829&bg_color=0a0f1e&color=00d4ff&line=00d4ff&point=ffffff&area=true&area_color=00d4ff&hide_border=true&radius=8" />
</div>

---

## 🤝 Let's Connect

<div align="center">

<a href="https://linkedin.com/in/rbhusare829">
  <img src="https://img.shields.io/badge/LinkedIn-Rohit_Bhusare-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0a0f1e"/>
</a>
&nbsp;
<a href="mailto:rbhusare829@gmail.com">
  <img src="https://img.shields.io/badge/Email-rbhusare829@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0a0f1e"/>
</a>
&nbsp;
<a href="https://github.com/rbhusare829">
  <img src="https://img.shields.io/badge/GitHub-rbhusare829-181717?style=for-the-badge&logo=github&logoColor=white&labelColor=0a0f1e"/>
</a>

</div>

---

<!-- FOOTER WAVE -->
<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0f1e,50:00d4ff,100:0a0f1e&height=100&section=footer&reversal=false&animation=fadeIn"/>

**`// Rohit Bhusare — Automating the future, one pipeline at a time 🚀`**

</div>