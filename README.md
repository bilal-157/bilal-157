<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bilal Rafique — Full-Stack Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        :root {
            --bg-primary: #0a0a0f;
            --bg-secondary: #111118;
            --bg-card: #16161f;
            --bg-card-hover: #1c1c28;
            --accent-cyan: #00f0ff;
            --accent-magenta: #ff00e4;
            --accent-green: #00ff88;
            --accent-orange: #ff6b35;
            --accent-purple: #a855f7;
            --text-primary: #e2e8f0;
            --text-secondary: #94a3b8;
            --text-muted: #64748b;
            --border: rgba(255, 255, 255, 0.06);
            --border-hover: rgba(0, 240, 255, 0.2);
            --shadow-glow: rgba(0, 240, 255, 0.08);
            --gradient-1: linear-gradient(135deg, #00f0ff 0%, #a855f7 50%, #ff00e4 100%);
            --gradient-2: linear-gradient(90deg, #00f0ff, #ff00e4);
            --gradient-3: linear-gradient(135deg, #ff6b35, #ff00e4);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* Animated Background */
        .bg-grid {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            opacity: 0.03;
            background-image: 
                linear-gradient(rgba(0, 240, 255, 0.3) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 240, 255, 0.3) 1px, transparent 1px);
            background-size: 50px 50px;
        }

        .bg-orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(80px);
            pointer-events: none;
            z-index: 0;
            opacity: 0.15;
            animation: float 20s ease-in-out infinite;
        }

        .orb-1 {
            width: 400px;
            height: 400px;
            background: var(--accent-cyan);
            top: -10%;
            left: -5%;
            animation-delay: 0s;
        }

        .orb-2 {
            width: 300px;
            height: 300px;
            background: var(--accent-magenta);
            bottom: 10%;
            right: -5%;
            animation-delay: -5s;
        }

        .orb-3 {
            width: 250px;
            height: 250px;
            background: var(--accent-purple);
            top: 40%;
            left: 60%;
            animation-delay: -10s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
        }

        /* Cursor Effect */
        .cursor-glow {
            position: fixed;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(0, 240, 255, 0.06) 0%, transparent 70%);
            pointer-events: none;
            z-index: 1;
            transform: translate(-50%, -50%);
            transition: opacity 0.3s;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-primary);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--accent-cyan);
            border-radius: 3px;
        }

        /* Main Container */
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 24px;
            position: relative;
            z-index: 2;
        }

        /* Header / Hero */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            padding: 40px 0;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 8px 20px;
            border-radius: 50px;
            background: var(--bg-card);
            border: 1px solid var(--border);
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
            color: var(--accent-cyan);
            margin-bottom: 30px;
            animation: pulse-glow 3s ease-in-out infinite;
        }

        @keyframes pulse-glow {
            0%, 100% { box-shadow: 0 0 20px rgba(0, 240, 255, 0.1); }
            50% { box-shadow: 0 0 40px rgba(0, 240, 255, 0.2); }
        }

        .hero-badge .dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--accent-green);
            animation: blink 2s ease-in-out infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }

        .hero h1 {
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 700;
            margin-bottom: 10px;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -1px;
        }

        .hero .subtitle {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.1rem;
            color: var(--text-secondary);
            margin-bottom: 40px;
        }

        .typing-container {
            font-family: 'JetBrains Mono', monospace;
            font-size: clamp(1rem, 2.5vw, 1.4rem);
            color: var(--accent-cyan);
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 40px;
        }

        .typing-text::after {
            content: '|';
            animation: cursor-blink 1s step-end infinite;
            color: var(--accent-cyan);
        }

        @keyframes cursor-blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .hero-gif {
            width: 280px;
            height: 280px;
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid var(--border);
            box-shadow: 0 0 60px rgba(0, 240, 255, 0.1);
            margin-bottom: 40px;
            position: relative;
        }

        .hero-gif::before {
            content: '';
            position: absolute;
            inset: 0;
            border-radius: 20px;
            padding: 1px;
            background: var(--gradient-2);
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            pointer-events: none;
        }

        .hero-gif img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .scroll-indicator {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            color: var(--text-muted);
            font-size: 0.75rem;
            font-family: 'JetBrains Mono', monospace;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(-10px); }
        }

        /* Section Styles */
        section {
            padding: 80px 0;
            position: relative;
        }

        .section-header {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 40px;
        }

        .section-header .line {
            flex: 1;
            height: 1px;
            background: linear-gradient(90deg, var(--border), var(--accent-cyan), var(--border));
            opacity: 0.3;
        }

        .section-header h2 {
            font-size: 1.5rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 12px;
            white-space: nowrap;
            font-family: 'JetBrains Mono', monospace;
        }

        .section-header h2 .icon {
            font-size: 1.2rem;
        }

        /* About Section */
        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .about-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 24px;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .about-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--gradient-2);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.4s ease;
        }

        .about-card:hover {
            border-color: var(--border-hover);
            transform: translateY(-4px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3), 0 0 30px var(--shadow-glow);
        }

        .about-card:hover::before {
            transform: scaleX(1);
        }

        .about-card .emoji {
            font-size: 1.5rem;
            margin-bottom: 12px;
            display: block;
        }

        .about-card p {
            color: var(--text-secondary);
            font-size: 0.95rem;
            line-height: 1.7;
        }

        .about-card strong {
            color: var(--text-primary);
            font-weight: 600;
        }

        /* Social Links */
        .social-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px;
        }

        .social-link {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 24px;
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 12px;
            color: var(--text-secondary);
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            inset: 0;
            background: var(--gradient-2);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .social-link:hover {
            color: var(--bg-primary);
            border-color: transparent;
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0, 240, 255, 0.15);
        }

        .social-link:hover::before {
            opacity: 1;
        }

        .social-link span, .social-link i {
            position: relative;
            z-index: 1;
        }

        /* Tech Stack */
        .tech-category {
            margin-bottom: 50px;
        }

        .tech-category-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.1rem;
            color: var(--accent-cyan);
            margin-bottom: 24px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tech-category-title::before {
            content: '//';
            color: var(--text-muted);
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 12px;
        }

        .tech-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 14px 16px;
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 10px;
            transition: all 0.3s ease;
            cursor: default;
        }

        .tech-item:hover {
            border-color: var(--border-hover);
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
        }

        .tech-item .tech-icon {
            width: 28px;
            height: 28px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
        }

        .tech-item .tech-name {
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--text-primary);
        }

        /* Skills Table */
        .skills-table {
            width: 100%;
            border-collapse: separate;
            border-spacing: 0 8px;
        }

        .skills-table tr {
            background: var(--bg-card);
            transition: all 0.3s ease;
        }

        .skills-table td {
            padding: 16px 20px;
            border: 1px solid var(--border);
        }

        .skills-table td:first-child {
            border-radius: 10px 0 0 10px;
            border-right: none;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
            color: var(--accent-cyan);
            width: 140px;
            white-space: nowrap;
        }

        .skills-table td:last-child {
            border-radius: 0 10px 10px 0;
            border-left: none;
        }

        .skills-table tr:hover {
            background: var(--bg-card-hover);
            border-color: var(--border-hover);
        }

        .skill-badge {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            padding: 6px 14px;
            background: rgba(0, 240, 255, 0.06);
            border: 1px solid rgba(0, 240, 255, 0.1);
            border-radius: 6px;
            font-size: 0.8rem;
            color: var(--text-secondary);
            margin: 4px;
            transition: all 0.2s ease;
        }

        .skill-badge:hover {
            background: rgba(0, 240, 255, 0.12);
            color: var(--accent-cyan);
            transform: scale(1.05);
        }

        /* GitHub Stats */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .stats-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 20px;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .stats-card:hover {
            border-color: var(--border-hover);
            box-shadow: 0 0 40px var(--shadow-glow);
        }

        .stats-card img {
            width: 100%;
            border-radius: 10px;
        }

        .stats-full {
            grid-column: 1 / -1;
        }

        /* Quote Section */
        .quote-box {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .quote-box::before {
            content: '"';
            position: absolute;
            top: -20px;
            left: 20px;
            font-size: 8rem;
            color: rgba(0, 240, 255, 0.05);
            font-family: Georgia, serif;
            line-height: 1;
        }

        .quote-text {
            font-size: 1.2rem;
            font-style: italic;
            color: var(--text-secondary);
            margin-bottom: 16px;
            position: relative;
            z-index: 1;
        }

        .quote-author {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
            color: var(--accent-cyan);
        }

        /* Footer */
        .footer {
            padding: 60px 0 40px;
            text-align: center;
            border-top: 1px solid var(--border);
            margin-top: 40px;
        }

        .footer-wave {
            width: 100%;
            height: 100px;
            background: linear-gradient(180deg, transparent, var(--bg-secondary));
            margin-bottom: -1px;
        }

        .footer-content {
            background: var(--bg-secondary);
            padding: 40px 0;
        }

        .footer-text {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
            color: var(--text-muted);
        }

        .footer-heart {
            color: var(--accent-magenta);
            animation: heartbeat 1.5s ease-in-out infinite;
            display: inline-block;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.2rem; }
            .section-header h2 { font-size: 1.2rem; }
            .tech-grid { grid-template-columns: repeat(auto-fill, minmax(120px, 1fr)); }
            .social-link { padding: 10px 16px; font-size: 0.8rem; }
            .skills-table td:first-child { width: 100px; font-size: 0.75rem; }
        }

        /* Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
<base target="_blank">
</head>
<body>
    <!-- Background Effects -->
    <div class="bg-grid"></div>
    <div class="bg-orb orb-1"></div>
    <div class="bg-orb orb-2"></div>
    <div class="bg-orb orb-3"></div>
    <div class="cursor-glow" id="cursorGlow"></div>

    <div class="container">
        <!-- Hero Section -->
        <section class="hero" id="hero">
            <div class="hero-badge">
                <span class="dot"></span>
                <span>Available for collaboration</span>
            </div>

            <h1>Hi, I'm Bilal Rafique</h1>
            <p class="subtitle">Full-Stack Next.js Developer</p>

            <div class="typing-container">
                <span class="typing-text" id="typingText"></span>
            </div>

            <div class="hero-gif">
                <img src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" alt="Coding animation">
            </div>

            <div class="scroll-indicator">
                <span>scroll to explore</span>
                <i class="fas fa-chevron-down"></i>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="reveal">
            <div class="section-header">
                <div class="line"></div>
                <h2><span class="icon">🌟</span> About Me</h2>
                <div class="line"></div>
            </div>

            <div class="about-grid">
                <div class="about-card">
                    <span class="emoji">🔭</span>
                    <p>Currently working on <strong>AI-powered web applications</strong></p>
                </div>
                <div class="about-card">
                    <span class="emoji">🌱</span>
                    <p>Learning <strong>Deep Learning & Advanced System Design</strong></p>
                </div>
                <div class="about-card">
                    <span class="emoji">💡</span>
                    <p>Passionate about <strong>solving complex problems with elegant solutions</strong></p>
                </div>
                <div class="about-card">
                    <span class="emoji">👯</span>
                    <p>Looking to collaborate on <strong>open-source projects</strong></p>
                </div>
                <div class="about-card">
                    <span class="emoji">⚡</span>
                    <p>Fun fact: <strong>I can solve a Rubik's cube in under 2 minutes</strong></p>
                </div>
                <div class="about-card">
                    <span class="emoji">🧠</span>
                    <p>Curious – exploring modern API development beyond REST</p>
                </div>
            </div>
        </section>

        <!-- Connect Section -->
        <section id="connect" class="reveal">
            <div class="section-header">
                <div class="line"></div>
                <h2><span class="icon">🌐</span> Connect With Me</h2>
                <div class="line"></div>
            </div>

            <div class="social-grid">
                <a href="https://discord.gg/bugs119" class="social-link" target="_blank">
                    <i class="fab fa-discord"></i>
                    <span>Discord</span>
                </a>
                <a href="https://www.facebook.com/share/1B3TzGo6Wu/" class="social-link" target="_blank">
                    <i class="fab fa-facebook-f"></i>
                    <span>Facebook</span>
                </a>
                <a href="https://instagram.com/bilal_rafique_11" class="social-link" target="_blank">
                    <i class="fab fa-instagram"></i>
                    <span>Instagram</span>
                </a>
                <a href="https://www.linkedin.com/in/muhammadbilal711" class="social-link" target="_blank">
                    <i class="fab fa-linkedin-in"></i>
                    <span>LinkedIn</span>
                </a>
                <a href="mailto:rafiqueb087@gmail.com" class="social-link">
                    <i class="fas fa-envelope"></i>
                    <span>Email</span>
                </a>
                <a href="https://codeforces.com/profile/bilal_rafi" class="social-link" target="_blank">
                    <i class="fas fa-code"></i>
                    <span>Codeforces</span>
                </a>
                <a href="https://cses.fi/user/340387/" class="social-link" target="_blank">
                    <i class="fas fa-database"></i>
                    <span>CSES</span>
                </a>
                <a href="https://leetcode.com/u/Bilal157/" class="social-link" target="_blank">
                    <i class="fas fa-laptop-code"></i>
                    <span>LeetCode</span>
                </a>
            </div>
        </section>

        <!-- Tech Stack Section -->
        <section id="tech" class="reveal">
            <div class="section-header">
                <div class="line"></div>
                <h2><span class="icon">💻</span> Tech Stack & Skills</h2>
                <div class="line"></div>
            </div>

            <!-- Frontend -->
            <div class="tech-category">
                <div class="tech-category-title">Frontend Development</div>
                <div class="tech-grid">
                    <div class="tech-item"><span class="tech-icon" style="color:#E34F26">●</span><span class="tech-name">HTML5</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#1572B6">●</span><span class="tech-name">CSS3</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#F7DF1E">●</span><span class="tech-name">JavaScript</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#61DAFB">●</span><span class="tech-name">React</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#fff">●</span><span class="tech-name">Next.js</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#38B2AC">●</span><span class="tech-name">Tailwind</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#7952B3">●</span><span class="tech-name">Bootstrap</span></div>
                </div>
            </div>

            <!-- Backend & AI -->
            <div class="tech-category">
                <div class="tech-category-title">Backend & AI Development</div>
                <table class="skills-table">
                    <tr>
                        <td>Runtime</td>
                        <td>
                            <span class="skill-badge">Node.js</span>
                        </td>
                    </tr>
                    <tr>
                        <td>Frameworks</td>
                        <td>
                            <span class="skill-badge">Express.js</span>
                            <span class="skill-badge">FastAPI</span>
                            <span class="skill-badge">Flask</span>
                            <span class="skill-badge">Django</span>
                        </td>
                    </tr>
                    <tr>
                        <td>Databases</td>
                        <td>
                            <span class="skill-badge">MongoDB</span>
                            <span class="skill-badge">PostgreSQL</span>
                            <span class="skill-badge">Mongoose</span>
                            <span class="skill-badge">Sequelize</span>
                        </td>
                    </tr>
                    <tr>
                        <td>APIs</td>
                        <td>
                            <span class="skill-badge">GraphQL</span>
                            <span class="skill-badge">REST API</span>
                            <span class="skill-badge">JWT</span>
                        </td>
                    </tr>
                    <tr>
                        <td>Languages</td>
                        <td>
                            <span class="skill-badge">Python</span>
                            <span class="skill-badge">C++</span>
                            <span class="skill-badge">C#</span>
                            <span class="skill-badge">PHP</span>
                        </td>
                    </tr>
                    <tr>
                        <td>AI & ML</td>
                        <td>
                            <span class="skill-badge">NumPy</span>
                            <span class="skill-badge">Pandas</span>
                            <span class="skill-badge">Matplotlib</span>
                            <span class="skill-badge">TensorFlow</span>
                            <span class="skill-badge">Keras</span>
                        </td>
                    </tr>
                </table>
            </div>

            <!-- Tools -->
            <div class="tech-category">
                <div class="tech-category-title">Tools & Deployment</div>
                <div class="tech-grid">
                    <div class="tech-item"><span class="tech-icon" style="color:#F05032">●</span><span class="tech-name">Git</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#fff">●</span><span class="tech-name">GitHub</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#FF6C37">●</span><span class="tech-name">Postman</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#fff">●</span><span class="tech-name">Vercel</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#430098">●</span><span class="tech-name">Heroku</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#00C7B7">●</span><span class="tech-name">Netlify</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#007ACC">●</span><span class="tech-name">VS Code</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#2496ED">●</span><span class="tech-name">Docker</span></div>
                    <div class="tech-item"><span class="tech-icon" style="color:#009639">●</span><span class="tech-name">Nginx</span></div>
                </div>
            </div>
        </section>

        <!-- GitHub Stats -->
        <section id="stats" class="reveal">
            <div class="section-header">
                <div class="line"></div>
                <h2><span class="icon">📊</span> GitHub Stats</h2>
                <div class="line"></div>
            </div>

            <div class="stats-grid">
                <div class="stats-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=bilal-157&show_icons=true&theme=radical&include_all_commits=true&count_private=true&border_radius=10" alt="GitHub Stats">
                </div>
                <div class="stats-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=bilal-157&layout=compact&langs_count=8&theme=radical&border_radius=10" alt="Top Languages">
                </div>
                <div class="stats-card stats-full">
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=bilal-157&theme=radical&border_radius=10&fire=DD2727" alt="GitHub Streak">
                </div>
                <div class="stats-card stats-full">
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=bilal-157&theme=radical" alt="Profile Details" style="width:100%">
                </div>
            </div>
        </section>

        <!-- Quote Section -->
        <section id="quote" class="reveal">
            <div class="section-header">
                <div class="line"></div>
                <h2><span class="icon">💬</span> Dev Quote</h2>
                <div class="line"></div>
            </div>

            <div class="quote-box">
                <p class="quote-text" id="quoteText">"Code is like humor. When you have to explain it, it's bad."</p>
                <p class="quote-author">— Cory House</p>
            </div>
        </section>

        <!-- Footer -->
        <div class="footer">
            <div class="footer-wave"></div>
            <div class="footer-content">
                <p class="footer-text">
                    Built with <span class="footer-heart">❤</span> by Bilal Rafique
                </p>
            </div>
        </div>
    </div>

    <script>
        // Typing Effect
        const phrases = [
            "Full-Stack Next.js Developer",
            "AI & Data Science Explorer",
            "Open-Source Contributor",
            "Coding with passion every day"
        ];
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typingText');

        function type() {
            const currentPhrase = phrases[phraseIndex];

            if (isDeleting) {
                typingElement.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }

            let typeSpeed = isDeleting ? 50 : 100;

            if (!isDeleting && charIndex === currentPhrase.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
                typeSpeed = 500;
            }

            setTimeout(type, typeSpeed);
        }
        type();

        // Cursor Glow Effect
        const cursorGlow = document.getElementById('cursorGlow');
        document.addEventListener('mousemove', (e) => {
            cursorGlow.style.left = e.clientX + 'px';
            cursorGlow.style.top = e.clientY + 'px';
        });

        // Scroll Reveal
        const revealElements = document.querySelectorAll('.reveal');
        const revealObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, { threshold: 0.1 });

        revealElements.forEach(el => revealObserver.observe(el));

        // Random Quote
        const quotes = [
            { text: "Code is like humor. When you have to explain it, it's bad.", author: "Cory House" },
            { text: "First, solve the problem. Then, write the code.", author: "John Johnson" },
            { text: "Simplicity is the soul of efficiency.", author: "Austin Freeman" },
            { text: "Make it work, make it right, make it fast.", author: "Kent Beck" },
            { text: "The best code is no code at all.", author: "Jeff Atwood" }
        ];

        const randomQuote = quotes[Math.floor(Math.random() * quotes.length)];
        document.getElementById('quoteText').textContent = `"${randomQuote.text}"`;
        document.querySelector('.quote-author').textContent = `— ${randomQuote.author}`;
    </script>
</body>
</html>
