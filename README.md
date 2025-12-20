<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rohit Bhusare | DevOps Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* --- CSS Variables & Reset --- */
        :root {
            --bg-color: #0a0f1c; /* Dark Navy */
            --card-bg: #111a2e;
            --text-color: #e2e8f0;
            --accent-color: #38bdf8; /* Light Blue */
            --secondary-accent: #22c55e; /* Green for success/DevOps */
            --font-main: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: var(--font-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* --- Animations --- */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .reveal {
            opacity: 0;
            transition: all 1s ease;
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- Header --- */
        header {
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            background: rgba(10, 15, 28, 0.95);
            z-index: 1000;
            border-bottom: 1px solid #1e293b;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--accent-color);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 30px;
        }

        nav ul li a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        nav ul li a:hover {
            color: var(--accent-color);
        }

        /* --- Hero Section --- */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            background: radial-gradient(circle at center, #1e293b 0%, var(--bg-color) 70%);
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 10px;
            animation: fadeIn 1.5s ease;
        }

        .hero h1 span {
            color: var(--accent-color);
        }

        .hero p {
            font-size: 1.5rem;
            color: #94a3b8;
            margin-bottom: 30px;
            animation: fadeIn 2s ease;
        }

        .btn {
            padding: 12px 30px;
            background: transparent;
            border: 2px solid var(--accent-color);
            color: var(--accent-color);
            text-decoration: none;
            font-weight: bold;
            border-radius: 5px;
            transition: all 0.3s;
            cursor: pointer;
            margin: 5px;
        }

        .btn:hover {
            background: var(--accent-color);
            color: var(--bg-color);
            box-shadow: 0 0 15px var(--accent-color);
        }

        /* --- Sections Common --- */
        section {
            padding: 80px 10%;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            color: var(--text-color);
            position: relative;
        }

        .section-title::after {
            content: '';
            width: 60px;
            height: 4px;
            background: var(--accent-color);
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        /* --- Skills --- */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
        }

        .skill-card {
            background: var(--card-bg);
            padding: 20px;
            text-align: center;
            border-radius: 10px;
            border: 1px solid #1e293b;
            transition: transform 0.3s, border-color 0.3s;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-color);
            box-shadow: 0 0 20px rgba(56, 189, 248, 0.1);
        }

        .skill-card i {
            font-size: 3rem;
            margin-bottom: 15px;
            color: var(--secondary-accent);
        }

        /* --- Projects --- */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid #1e293b;
            transition: transform 0.3s;
        }

        .project-card:hover {
            transform: scale(1.02);
        }

        .project-info {
            padding: 20px;
        }

        .project-info h3 {
            color: var(--accent-color);
            margin-bottom: 10px;
        }

        .tech-stack span {
            display: inline-block;
            background: #1e293b;
            padding: 5px 10px;
            font-size: 0.8rem;
            border-radius: 15px;
            margin-right: 5px;
            margin-top: 5px;
            color: var(--secondary-accent);
        }

        /* --- Education --- */
        .education-card {
            background: var(--card-bg);
            padding: 30px;
            border-left: 5px solid var(--accent-color);
            margin-bottom: 20px;
        }

        /* --- Contact --- */
        .contact {
            text-align: center;
        }

        .social-links {
            margin-top: 30px;
        }

        .social-links a {
            font-size: 2rem;
            color: var(--text-color);
            margin: 0 15px;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: var(--accent-color);
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            header { padding: 15px 20px; }
            nav { display: none; } /* Simplified for demo */
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">RB.</div>
        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero">
        <h1>Hi, I'm <span>Rohit Bhusare</span></h1>
        <p>DevOps Learner | AWS | Terraform | Jenkins</p>
        <div>
            <a href="#projects" class="btn">View My Work</a>
            <a href="#contact" class="btn">Contact Me</a>
        </div>
    </section>

    <section id="skills">
        <h2 class="section-title">Technical Skills</h2>
        <div class="skills-container">
            <div class="skill-card reveal">
                <i class="fab fa-aws"></i>
                <h3>AWS</h3>
            </div>
            <div class="skill-card reveal">
                <i class="fas fa-code"></i>
                <h3>Terraform</h3>
            </div>
            <div class="skill-card reveal">
                <i class="fab fa-jenkins"></i>
                <h3>Jenkins</h3>
            </div>
            <div class="skill-card reveal">
                <i class="fab fa-docker"></i>
                <h3>Docker</h3>
            </div>
            <div class="skill-card reveal">
                <i class="fab fa-html5"></i>
                <h3>HTML</h3>
            </div>
            <div class="skill-card reveal">
                <i class="fab fa-git-alt"></i>
                <h3>Git & GitLab</h3>
            </div>
             <div class="skill-card reveal">
                <i class="fab fa-bitbucket"></i>
                <h3>Bitbucket</h3>
            </div>
        </div>
    </section>

    <section id="projects">
        <h2 class="section-title">My Projects</h2>
        <div class="projects-grid">
            
            <div class="project-card reveal">
                <div class="project-info">
                    <h3>Cloud Deployment Pipeline</h3>
                    <p>Automated CI/CD pipeline using Jenkins and GitLab to deploy applications on AWS EC2 instances securely.</p>
                    <div class="tech-stack">
                        <span>AWS</span>
                        <span>Jenkins</span>
                        <span>GitLab</span>
                        <span>Linux</span>
                    </div>
                </div>
            </div>

            <div class="project-card reveal">
                <div class="project-info">
                    <h3>Infrastructure as Code (IaC)</h3>
                    <p>Provisioned scalable infrastructure on AWS using Terraform modules, reducing manual setup time by 80%.</p>
                    <div class="tech-stack">
                        <span>Terraform</span>
                        <span>AWS VPC</span>
                        <span>S3</span>
                    </div>
                </div>
            </div>

            <div class="project-card reveal">
                <div class="project-info">
                    <h3>Static Website Hosting</h3>
                    <p>Deployed a high-performance portfolio website using AWS S3 and CloudFront with custom domain mapping.</p>
                    <div class="tech-stack">
                        <span>AWS S3</span>
                        <span>CloudFront</span>
                        <span>HTML/CSS</span>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <section id="education">
        <h2 class="section-title">Education</h2>
        <div class="education-card reveal">
            <h3>Bachelor of Commerce (B.Com)</h3>
            <p><strong>B. P. Sulakhe Commerce College, Barshi</strong></p>
            <p>Dist: Solapur, Maharashtra</p>
            <p><em>2022 - 2025</em></p>
        </div>
    </section>

    <section id="contact" class="contact">
        <h2 class="section-title">Get In Touch</h2>
        <p>Currently based in Pune, Maharashtra. Open for DevOps opportunities.</p>
        
        <div class="social-links">
            <a href="mailto:rbhusare829@gmail.com" title="Email"><i class="fas fa-envelope"></i></a>
            <a href="https://www.linkedin.com/in/rohitbhusare-84b94b368" target="_blank" title="LinkedIn"><i class="fab fa-linkedin"></i></a>
            <a href="https://github.com/rbhusare829" target="_blank" title="GitHub"><i class="fab fa-github"></i></a>
            <a href="#" title="Instagram"><i class="fab fa-instagram"></i></a>
        </div>
        
        <p style="margin-top: 50px; color: #64748b; font-size: 0.9rem;">
            &copy; 2025 Rohit Bhusare. Built with code & passion.
        </p>
    </section>

    <script>
        window.addEventListener('scroll', reveal);

        function reveal(){
            var reveals = document.querySelectorAll('.reveal');

            for(var i = 0; i < reveals.length; i++){
                var windowheight = window.innerHeight;
                var revealtop = reveals[i].getBoundingClientRect().top;
                var revealpoint = 150;

                if(revealtop < windowheight - revealpoint){
                    reveals[i].classList.add('active');
                }
                else{
                    reveals[i].classList.remove('active');
                }
            }
        }
    </script>
</body>
</html>
