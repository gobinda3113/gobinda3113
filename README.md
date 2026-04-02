<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gobinda Adhikari – GitHub README Preview</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --neon-blue: #00d4ff;
            --neon-purple: #a855f7;
            --neon-green: #22c55e;
            --dark-bg: #0d1117;
            --card-bg: #161b22;
            --border-color: #30363d;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--dark-bg);
            color: #e6edf3;
            overflow-x: hidden;
        }

        /* Animated background */
        .bg-grid {
            position: fixed;
            inset: 0;
            background-image:
                linear-gradient(rgba(0, 212, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 212, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            z-index: 0;
            animation: gridMove 20s linear infinite;
        }

        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .floating-orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.15;
            z-index: 0;
            animation: float 8s ease-in-out infinite;
        }

        .orb-1 { width: 400px; height: 400px; background: var(--neon-blue); top: -100px; right: -100px; animation-delay: 0s; }
        .orb-2 { width: 350px; height: 350px; background: var(--neon-purple); bottom: -50px; left: -100px; animation-delay: 3s; }
        .orb-3 { width: 300px; height: 300px; background: var(--neon-green); top: 50%; left: 50%; animation-delay: 5s; }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.05); }
            66% { transform: translate(-20px, 20px) scale(0.95); }
        }

        .main-container {
            position: relative;
            z-index: 1;
            max-width: 980px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Tab system */
        .tab-bar {
            display: flex;
            gap: 0;
            margin-bottom: 0;
            background: var(--card-bg);
            border-radius: 12px 12px 0 0;
            border: 1px solid var(--border-color);
            border-bottom: none;
            overflow: hidden;
        }

        .tab-btn {
            flex: 1;
            padding: 16px 24px;
            background: transparent;
            border: none;
            color: #8b949e;
            font-family: 'JetBrains Mono', monospace;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
        }

        .tab-btn:hover { color: #e6edf3; background: rgba(0, 212, 255, 0.05); }

        .tab-btn.active {
            color: var(--neon-blue);
            background: rgba(0, 212, 255, 0.08);
        }

        .tab-btn.active::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-purple));
        }

        .tab-content {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 0 0 12px 12px;
            min-height: 600px;
        }

        .tab-panel { display: none; padding: 0; }
        .tab-panel.active { display: block; }

        /* README Preview Styles */
        .readme-preview {
            padding: 40px;
            line-height: 1.7;
        }

        .readme-preview img {
            max-width: 100%;
            height: auto;
        }

        .readme-preview h1, .readme-preview h2, .readme-preview h3 {
            margin-top: 24px;
            margin-bottom: 16px;
            font-weight: 700;
            line-height: 1.25;
        }

        .readme-preview h1 { font-size: 2em; border-bottom: 1px solid var(--border-color); padding-bottom: 0.3em; }
        .readme-preview h2 { font-size: 1.5em; border-bottom: 1px solid var(--border-color); padding-bottom: 0.3em; }
        .readme-preview h3 { font-size: 1.25em; }

        .readme-preview p { margin-bottom: 16px; }
        .readme-preview a { color: var(--neon-blue); text-decoration: none; }
        .readme-preview a:hover { text-decoration: underline; }
        .readme-preview hr { border: none; height: 1px; background: var(--border-color); margin: 24px 0; }

        .readme-preview .center { text-align: center; }

        .readme-preview table {
            border-collapse: collapse;
            width: 100%;
            margin: 16px 0;
        }

        .readme-preview table th, .readme-preview table td {
            border: 1px solid var(--border-color);
            padding: 10px 16px;
            text-align: left;
        }

        .readme-preview table th {
            background: rgba(0, 212, 255, 0.08);
            font-weight: 600;
        }

        .badge-row {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            justify-content: center;
            margin: 8px 0;
        }

        .badge-row img {
            height: 28px;
            transition: transform 0.2s;
        }

        .badge-row img:hover {
            transform: translateY(-3px);
        }

        .stats-row {
            display: flex;
            flex-wrap: wrap;
            gap: 16px;
            justify-content: center;
            margin: 16px 0;
        }

        .stats-row img {
            border-radius: 8px;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .stats-row img:hover {
            transform: scale(1.02);
            box-shadow: 0 0 20px rgba(0, 212, 255, 0.3);
        }

        .project-card {
            background: rgba(13, 17, 23, 0.8);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 20px;
            margin: 12px 0;
            transition: all 0.3s;
        }

        .project-card:hover {
            border-color: var(--neon-blue);
            box-shadow: 0 0 15px rgba(0, 212, 255, 0.1);
            transform: translateY(-2px);
        }

        .project-title {
            font-size: 1.1em;
            font-weight: 700;
            color: var(--neon-blue);
            margin-bottom: 8px;
        }

        .project-desc {
            color: #8b949e;
            font-size: 0.95em;
            margin-bottom: 12px;
        }

        .tech-tag {
            display: inline-block;
            background: rgba(0, 212, 255, 0.1);
            color: var(--neon-blue);
            padding: 2px 10px;
            border-radius: 20px;
            font-size: 0.8em;
            margin: 2px;
            border: 1px solid rgba(0, 212, 255, 0.2);
        }

        /* Code panel */
        .code-panel {
            position: relative;
        }

        .code-panel pre {
            background: #0d1117;
            color: #e6edf3;
            padding: 30px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 12.5px;
            line-height: 1.6;
            overflow-x: auto;
            white-space: pre;
            margin: 0;
            border-radius: 0 0 12px 12px;
            max-height: 80vh;
        }

        .copy-btn {
            position: sticky;
            top: 0;
            z-index: 10;
            display: flex;
            justify-content: flex-end;
            padding: 12px 16px;
            background: linear-gradient(180deg, #0d1117 0%, #0d1117 70%, transparent 100%);
        }

        .copy-btn button {
            background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple));
            color: white;
            border: none;
            padding: 10px 24px;
            border-radius: 8px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .copy-btn button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(0, 212, 255, 0.4);
        }

        .copy-btn button.copied {
            background: linear-gradient(135deg, var(--neon-green), #16a34a);
        }

        /* Typing animation for preview */
        .typing-cursor {
            display: inline-block;
            width: 3px;
            height: 1.1em;
            background: var(--neon-blue);
            margin-left: 4px;
            animation: blink 1s step-end infinite;
            vertical-align: text-bottom;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .section-header {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.4em;
            font-weight: 700;
            margin: 32px 0 16px 0;
            padding-bottom: 8px;
            border-bottom: 1px solid var(--border-color);
        }

        .section-header .emoji { font-size: 1.2em; }

        .connect-btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 10px 20px;
            border-radius: 8px;
            text-decoration: none !important;
            font-weight: 600;
            font-size: 0.95em;
            transition: all 0.3s;
            margin: 4px;
        }

        .connect-btn:hover { transform: translateY(-3px); }
        .connect-github { background: #333; color: white !important; }
        .connect-linkedin { background: #0077b5; color: white !important; }
        .connect-portfolio { background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple)); color: white !important; }

        .vision-box {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.08), rgba(168, 85, 247, 0.08));
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 12px;
            padding: 24px;
            margin: 16px 0;
            text-align: center;
            font-style: italic;
            font-size: 1.05em;
            line-height: 1.8;
        }

        .snake-img {
            width: 100%;
            margin: 16px 0;
            border-radius: 8px;
        }

        .wave { animation: wave 2.5s infinite; display: inline-block; transform-origin: 70% 70%; }
        @keyframes wave {
            0% { transform: rotate(0deg); }
            10% { transform: rotate(14deg); }
            20% { transform: rotate(-8deg); }
            30% { transform: rotate(14deg); }
            40% { transform: rotate(-4deg); }
            50% { transform: rotate(10deg); }
            60% { transform: rotate(0deg); }
            100% { transform: rotate(0deg); }
        }

        .glow-text {
            background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple), var(--neon-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .profile-views {
            display: inline-block;
            margin: 8px 0;
        }

        .separator-wave {
            text-align: center;
            margin: 24px 0;
            opacity: 0.5;
        }

        .about-list {
            list-style: none;
            padding: 0;
        }

        .about-list li {
            padding: 6px 0;
            font-size: 1.02em;
        }

        .footer-line {
            text-align: center;
            margin: 32px 0 16px 0;
            font-size: 0.95em;
            color: #8b949e;
        }

        .activity-graph {
            width: 100%;
            border-radius: 8px;
            margin: 16px 0;
        }

        @media (max-width: 768px) {
            .readme-preview { padding: 20px; }
            .stats-row { flex-direction: column; align-items: center; }
            .tab-btn { font-size: 12px; padding: 12px 8px; }
            .code-panel pre { font-size: 11px; padding: 16px; }
        }
    </style>
</head>
<body>

    <div class="bg-grid"></div>
    <div class="floating-orb orb-1"></div>
    <div class="floating-orb orb-2"></div>
    <div class="floating-orb orb-3"></div>

    <div class="main-container">

        <!-- Header -->
        <div style="text-align: center; padding: 48px 20px 32px;">
            <h1 style="font-size: 2.5em; font-weight: 900; margin-bottom: 8px;">
                <span class="glow-text">GitHub README Generator</span>
            </h1>
            <p style="color: #8b949e; font-size: 1.1em; font-family: 'JetBrains Mono', monospace;">
                Preview & Copy — Ready to paste into your profile
            </p>
        </div>

        <!-- Tabs -->
        <div class="tab-bar">
            <button class="tab-btn active" onclick="switchTab('preview')">
                👁️ Preview
            </button>
            <button class="tab-btn" onclick="switchTab('code')">
                📋 Markdown Code
            </button>
        </div>

        <div class="tab-content">

            <!-- PREVIEW TAB -->
            <div class="tab-panel active" id="preview-panel">
                <div class="readme-preview" id="readme-render">

                    <!-- BANNER / HEADER -->
                    <div class="center">
                        <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00d4ff,100:a855f7&height=220&section=header&text=Gobinda%20Adhikari&fontSize=50&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Full%20Stack%20Developer%20%7C%20Building%20the%20Future%20with%20Code&descSize=18&descAlignY=55&descAlign=50" width="100%"/>
                    </div>

                    <div class="center" style="margin: 16px 0;">
                        <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=28&duration=3000&pause=1000&color=00D4FF&center=true&vCenter=true&multiline=true&repeat=true&width=700&height=80&lines=%F0%9F%9A%80+Full+Stack+Developer+%7C+Problem+Solver;%F0%9F%92%A1+Turning+Ideas+into+Scalable+Applications;%F0%9F%94%90+Cybersecurity+Enthusiast+%7C+Lifelong+Learner" alt="Typing SVG" />
                    </div>

                    <div class="center">
                        <img src="https://komarev.com/ghpvc/?username=gobinda-adhikari&label=Profile%20Views&color=00d4ff&style=for-the-badge" alt="Profile Views" />
                        <span style="margin: 0 4px;"></span>
                        <img src="https://img.shields.io/github/followers/gobinda-adhikari?label=Followers&style=for-the-badge&color=a855f7&labelColor=0d1117" alt="Followers" />
                    </div>

                    <br>
                    <div class="separator-wave">
                        <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">
                    </div>

                    <!-- ABOUT ME -->
                    <div class="section-header">
                        <span class="emoji">🧑‍💻</span> About Me
                    </div>

                    <div style="display: flex; gap: 24px; align-items: flex-start; flex-wrap: wrap;">
                        <div style="flex: 1; min-width: 280px;">
                            <p style="font-size: 1.05em; margin-bottom: 16px;">
                                <span class="wave">👋</span> Hey there! I'm <strong style="color: var(--neon-blue);">Gobinda Adhikari</strong>, a passionate
                                <strong>Full Stack Developer</strong> who loves crafting elegant solutions to complex problems.
                            </p>
                            <ul class="about-list">
                                <li>🔭 Currently working on <strong>scalable web applications & open-source projects</strong></li>
                                <li>🌱 Exploring <strong>Cloud Architecture, DevOps & AI/ML</strong></li>
                                <li>🛡️ Passionate about <strong>Cybersecurity & Ethical Hacking</strong></li>
                                <li>💬 Ask me about <strong>React, Node.js, Python, System Design</strong></li>
                                <li>⚡ Fun fact: <strong>I debug with coffee and build with passion ☕</strong></li>
                                <li>🎯 Goal: <strong>Contribute to projects that make a difference</strong></li>
                                <li>📫 Reach me at <strong>gobinda.adhikari@email.com</strong></li>
                            </ul>
                        </div>
                        <div style="flex-shrink: 0;">
                            <img src="https://raw.githubusercontent.com/abhisheknaiidu/abhisheknaiidu/master/code.gif" width="320" style="border-radius: 12px; border: 1px solid var(--border-color);" alt="Coding gif"/>
                        </div>
                    </div>

                    <div class="separator-wave">
                        <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">
                    </div>

                    <!-- TECH STACK -->
                    <div class="section-header">
                        <span class="emoji">🛠️</span> Tech Stack & Tools
                    </div>

                    <table>
                        <tr>
                            <th>🎨 Frontend</th>
                            <td>
                                <div class="badge-row" style="justify-content: flex-start;">
                                    <img src="https://skillicons.dev/icons?i=html,css,js,ts,react,nextjs,tailwind,bootstrap" alt="Frontend"/>
                                </div>
                            </td>
                        </tr>
                        <tr>
                            <th>⚙️ Backend</th>
                            <td>
                                <div class="badge-row" style="justify-content: flex-start;">
                                    <img src="https://skillicons.dev/icons?i=nodejs,express,python,java,php" alt="Backend"/>
                                </div>
                            </td>
                        </tr>
                        <tr>
                            <th>🗄️ Database</th>
                            <td>
                                <div class="badge-row" style="justify-content: flex-start;">
                                    <img src="https://skillicons.dev/icons?i=mongodb,mysql,postgresql,firebase" alt="Database"/>
                                </div>
                            </td>
                        </tr>
                        <tr>
                            <th>🔧 Tools & DevOps</th>
                            <td>
                                <div class="badge-row" style="justify-content: flex-start;">
                                    <img src="https://skillicons.dev/icons?i=git,github,docker,linux,vscode,postman" alt="Tools"/>
                                </div>
                            </td>
                        </tr>
                        <tr>
                            <th>💻 Other Languages</th>
                            <td>
                                <div class="badge-row" style="justify-content: flex-start;">
                                    <img src="https://skillicons.dev/icons?i=c,cpp,cs,go,ruby,bash" alt="Languages"/>
                                </div>
                            </td>
                        </tr>
                    </table>

                    <div class="separator-wave">
                        <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">
                    </div>

                    <!-- GITHUB STATS -->
                    <div class="section-header">
                        <span class="emoji">📊</span> GitHub Analytics
                    </div>

                    <div class="stats-row">
                        <img src="https://github-readme-stats.vercel.app/api?username=gobinda-adhikari&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00d4ff&icon_color=a855f7&text_color=e6edf3&ring_color=00d4ff" width="48%" alt="GitHub Stats"/>
                        <img src="https://github-readme-streak-stats.herokuapp.com/?user=gobinda-adhikari&theme=tokyonight&hide_border=true&background=0d1117&ring=00d4ff&fire=a855f7&currStreakLabel=00d4ff&sideLabels=e6edf3&dates=8b949e" width="48%" alt="Streak Stats"/>
                    </div>

                    <div class="stats-row">
                        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=gobinda-adhikari&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00d4ff&text_color=e6edf3&langs_count=10" width="48%" alt="Top Languages"/>
                        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=gobinda-adhikari&layout=donut&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00d4ff&text_color=e6edf3&langs_count=6" width="48%" alt="Language Donut"/>
                    </div>

                    <div class="center" style="margin: 16px 0;">
                        <img src="https://github-readme-activity-graph.vercel.app/graph?username=gobinda-adhikari&theme=tokyo-night&bg_color=0d1117&color=00d4ff&line=a855f7&point=00d4ff&area=true&hide_border=true" width="98%" class="activity-graph" alt="Activity Graph"/>
                    </div>

                    <div class="separator-wave">
                        <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">
                    </div>

                    <!-- FEATURED PROJECTS -->
                    <div class="section-header">
                        <span class="emoji">🚀</span> Featured Projects
                    </div>

                    <div class="project-card">
                        <div class="project-title">🛡️ Third Eye – Ethical Hacking & Cyber Security Learning Platform</div>
                        <div class="project-desc">
                            A comprehensive platform for learning ethical hacking and cybersecurity concepts. Features interactive labs, real-world vulnerability simulations, CTF challenges, and structured learning paths from beginner to advanced levels.
                        </div>
                        <div>
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">MongoDB</span>
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Docker</span>
                            <span class="tech-tag">WebSockets</span>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-title">🛒 ShopStream – Modern E-Commerce Platform</div>
                        <div class="project-desc">
                            A full-featured e-commerce application with real-time inventory management, Stripe payment integration, admin dashboard, and AI-powered product recommendations. Built for scalability and performance.
                        </div>
                        <div>
                            <span class="tech-tag">Next.js</span>
                            <span class="tech-tag">TypeScript</span>
                            <span class="tech-tag">PostgreSQL</span>
                            <span class="tech-tag">Stripe</span>
                            <span class="tech-tag">Redis</span>
                            <span class="tech-tag">Tailwind CSS</span>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-title">💬 DevConnect – Real-Time Developer Collaboration Hub</div>
                        <div class="project-desc">
                            A real-time collaboration platform for developers featuring live code sharing, video conferencing, project management boards, and integrated CI/CD pipeline monitoring. Think Slack meets GitHub.
                        </div>
                        <div>
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Express.js</span>
                            <span class="tech-tag">Socket.io</span>
                            <span class="tech-tag">MongoDB</span>
                            <span class="tech-tag">WebRTC</span>
                            <span class="tech-tag">Docker</span>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-title">📊 InsightBoard – Analytics & Monitoring Dashboard</div>
                        <div class="project-desc">
                            A powerful analytics dashboard for monitoring application performance, user behavior, and system health. Features real-time charts, custom alerts, and exportable reports with role-based access control.
                        </div>
                        <div>
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">FastAPI</span>
                            <span class="tech-tag">PostgreSQL</span>
                            <span class="tech-tag">D3.js</span>
                            <span class="tech-tag">Firebase</span>
                        </div>
                    </div>

                    <div class="separator-wave">
                        <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">
                    </div>

                    <!-- CONNECT -->
                    <div class="section-header">
                        <span class="emoji">🤝</span> Let's Connect
                    </div>

                    <div class="center" style="margin: 16px 0;">
                        <a href="#" class="connect-btn connect-github">
                            <img src="https://skillicons.dev/icons?i=github" width="24" /> GitHub
                        </a>
                        <a href="#" class="connect-btn connect-linkedin">
                            <img src="https://skillicons.dev/icons?i=linkedin" width="24" /> LinkedIn
                        </a>
                        <a href="#" class="connect-btn connect-portfolio">
                            🌐 Portfolio
                        </a>
                    </div>

                    <div class="center" style="margin: 12px 0;">
                        <img src="https://img.shields.io/badge/Gmail-gobinda.adhikari%40email.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
                    </div>

                    <div class="separator-wave">
                        <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">
                    </div>

                    <!-- GOALS / VISION -->
                    <div class="section-header">
                        <span class="emoji">🎯</span> Goals & Vision
                    </div>

                    <div class="vision-box">
                        <p>🌟 "Code is not just syntax — it's the blueprint of innovation."</p>
                        <br>
                        <p>
                            🚀 Building scalable, impactful software that solves real-world problems.<br>
                            🤝 Contributing to open-source and giving back to the developer community.<br>
                            📚 Never stop learning — currently diving deep into Cloud Native & AI/ML.<br>
                            🌍 Dream: To build technology that empowers millions across the globe.
                        </p>
                    </div>

                    <div class="separator-wave">
                        <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">
                    </div>

                    <!-- TROPHY -->
                    <div class="center">
                        <img src="https://github-profile-trophy.vercel.app/?username=gobinda-adhikari&theme=tokyonight&no-frame=true&no-bg=true&margin-w=10&column=7" width="98%" alt="Trophies"/>
                    </div>

                    <div class="separator-wave">
                        <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">
                    </div>

                    <!-- SNAKE -->
                    <div class="center">
                        <picture>
                            <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" />
                            <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg" />
                            <img alt="github-snake" src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" width="100%" />
                        </picture>
                    </div>

                    <br>

                    <!-- FOOTER -->
                    <div class="center">
                        <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00d4ff,100:a855f7&height=120&section=footer" width="100%"/>
                    </div>

                    <div class="footer-line">
                        <p>⭐ <strong>If you find my work helpful, consider giving a star!</strong> ⭐</p>
                        <p style="margin-top: 8px; font-family: 'JetBrains Mono', monospace; font-size: 0.85em;">
                            <span class="glow-text">Built with 💜 by Gobinda Adhikari</span>
                        </p>
                        <p style="margin-top: 4px; font-size: 0.8em; color: #6e7681;">
                            "The only way to do great work is to love what you do." — Steve Jobs
                        </p>
                    </div>

                </div>
            </div>

            <!-- CODE TAB -->
            <div class="tab-panel" id="code-panel">
                <div class="code-panel">
                    <div class="copy-btn">
                        <button onclick="copyCode()" id="copyBtn">
                            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="9" y="9" width="13" height="13" rx="2" ry="2"/><path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"/></svg>
                            Copy to Clipboard
                        </button>
                    </div>
                    <pre id="markdown-code"></pre>
                </div>
            </div>
        </div>

        <div style="text-align: center; padding: 24px; color: #6e7681; font-size: 0.85em; font-family: 'JetBrains Mono', monospace;">
            Replace <strong style="color: var(--neon-blue);">gobinda-adhikari</strong> with your actual GitHub username &bull; Update links & email
        </div>

    </div>

    <script>
        const markdownCode = `<!-- ═══════════════════════════════════════════════════════════════════════════
     🚀 GOBINDA ADHIKARI — Full Stack Developer | GitHub Profile README
     ═══════════════════════════════════════════════════════════════════════════ -->

<div align="center">

  <!-- ANIMATED BANNER -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00d4ff,100:a855f7&height=220&section=header&text=Gobinda%20Adhikari&fontSize=50&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Full%20Stack%20Developer%20%7C%20Building%20the%20Future%20with%20Code&descSize=18&descAlignY=55&descAlign=50" width="100%" />

  <!-- TYPING ANIMATION -->
  <br>
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=28&duration=3000&pause=1000&color=00D4FF&center=true&vCenter=true&multiline=true&repeat=true&width=700&height=80&lines=%F0%9F%9A%80+Full+Stack+Developer+%7C+Problem+Solver;%F0%9F%92%A1+Turning+Ideas+into+Scalable+Applications;%F0%9F%94%90+Cybersecurity+Enthusiast+%7C+Lifelong+Learner" alt="Typing SVG" />
  </a>
  <br>

  <!-- PROFILE BADGES -->
  <img src="https://komarev.com/ghpvc/?username=gobinda-adhikari&label=Profile%20Views&color=00d4ff&style=for-the-badge" alt="Profile Views" />
  &nbsp;
  <img src="https://img.shields.io/github/followers/gobinda-adhikari?label=Followers&style=for-the-badge&color=a855f7&labelColor=0d1117" alt="Followers" />

</div>

<br>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ═══════════════════════════════════════════════════════════════ -->
## 🧑‍💻 About Me
<!-- ═══════════════════════════════════════════════════════════════ -->

<img align="right" src="https://raw.githubusercontent.com/abhisheknaiidu/abhisheknaiidu/master/code.gif" width="320" />

👋 Hey there! I'm **Gobinda Adhikari**, a passionate **Full Stack Developer** who loves crafting elegant solutions to complex problems.

- 🔭 Currently working on **scalable web applications & open-source projects**
- 🌱 Exploring **Cloud Architecture, DevOps & AI/ML**
- 🛡️ Passionate about **Cybersecurity & Ethical Hacking**
- 💬 Ask me about **React, Node.js, Python, System Design**
- ⚡ Fun fact: **I debug with coffee and build with passion ☕**
- 🎯 Goal: **Contribute to projects that make a difference**
- 📫 Reach me at **gobinda.adhikari@email.com**

<br clear="both">

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ═══════════════════════════════════════════════════════════════ -->
## 🛠️ Tech Stack & Tools
<!-- ═══════════════════════════════════════════════════════════════ -->

| Category | Technologies |
|----------|-------------|
| **🎨 Frontend** | ![Frontend](https://skillicons.dev/icons?i=html,css,js,ts,react,nextjs,tailwind,bootstrap) |
| **⚙️ Backend** | ![Backend](https://skillicons.dev/icons?i=nodejs,express,python,java,php) |
| **🗄️ Database** | ![Database](https://skillicons.dev/icons?i=mongodb,mysql,postgresql,firebase) |
| **🔧 Tools & DevOps** | ![Tools](https://skillicons.dev/icons?i=git,github,docker,linux,vscode,postman) |
| **💻 Other Languages** | ![Languages](https://skillicons.dev/icons?i=c,cpp,cs,go,ruby,bash) |

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ═══════════════════════════════════════════════════════════════ -->
## 📊 GitHub Analytics
<!-- ═══════════════════════════════════════════════════════════════ -->

<div align="center">

  <img width="48%" src="https://github-readme-stats.vercel.app/api?username=gobinda-adhikari&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00d4ff&icon_color=a855f7&text_color=e6edf3&ring_color=00d4ff" alt="GitHub Stats" />
  &nbsp;
  <img width="48%" src="https://github-readme-streak-stats.herokuapp.com/?user=gobinda-adhikari&theme=tokyonight&hide_border=true&background=0d1117&ring=00d4ff&fire=a855f7&currStreakLabel=00d4ff&sideLabels=e6edf3&dates=8b949e" alt="Streak Stats" />

  <br><br>

  <img width="48%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=gobinda-adhikari&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00d4ff&text_color=e6edf3&langs_count=10" alt="Top Languages" />
  &nbsp;
  <img width="48%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=gobinda-adhikari&layout=donut&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00d4ff&text_color=e6edf3&langs_count=6" alt="Language Donut" />

  <br><br>

  <!-- ACTIVITY GRAPH -->
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=gobinda-adhikari&theme=tokyo-night&bg_color=0d1117&color=00d4ff&line=a855f7&point=00d4ff&area=true&hide_border=true" width="98%" alt="Activity Graph" />

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ═══════════════════════════════════════════════════════════════ -->
## 🚀 Featured Projects
<!-- ═══════════════════════════════════════════════════════════════ -->

### 🛡️ [Third Eye – Ethical Hacking & Cyber Security Learning Platform](https://github.com/gobinda-adhikari/third-eye)
> A comprehensive platform for learning ethical hacking and cybersecurity concepts. Features interactive labs, real-world vulnerability simulations, CTF challenges, and structured learning paths from beginner to advanced levels.
>
> \`React\` \`Node.js\` \`MongoDB\` \`Python\` \`Docker\` \`WebSockets\`

---

### 🛒 [ShopStream – Modern E-Commerce Platform](https://github.com/gobinda-adhikari/shopstream)
> A full-featured e-commerce application with real-time inventory management, Stripe payment integration, admin dashboard, and AI-powered product recommendations. Built for scalability and performance.
>
> \`Next.js\` \`TypeScript\` \`PostgreSQL\` \`Stripe\` \`Redis\` \`Tailwind CSS\`

---

### 💬 [DevConnect – Real-Time Developer Collaboration Hub](https://github.com/gobinda-adhikari/devconnect)
> A real-time collaboration platform for developers featuring live code sharing, video conferencing, project management boards, and integrated CI/CD pipeline monitoring.
>
> \`React\` \`Express.js\` \`Socket.io\` \`MongoDB\` \`WebRTC\` \`Docker\`

---

### 📊 [InsightBoard – Analytics & Monitoring Dashboard](https://github.com/gobinda-adhikari/insightboard)
> A powerful analytics dashboard for monitoring application performance, user behavior, and system health. Features real-time charts, custom alerts, and exportable reports with role-based access control.
>
> \`React\` \`Python\` \`FastAPI\` \`PostgreSQL\` \`D3.js\` \`Firebase\`

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ═══════════════════════════════════════════════════════════════ -->
## 🤝 Let's Connect
<!-- ═══════════════════════════════════════════════════════════════ -->

<div align="center">

  [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gobinda-adhikari)
  [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/gobinda-adhikari)
  [![Portfolio](https://img.shields.io/badge/Portfolio-a855f7?style=for-the-badge&logo=google-chrome&logoColor=white)](https://gobinda-adhikari.dev)
  [![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:gobinda.adhikari@email.com)

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ═══════════════════════════════════════════════════════════════ -->
## 🎯 Goals & Vision
<!-- ═══════════════════════════════════════════════════════════════ -->

<div align="center">

  > 🌟 *"Code is not just syntax — it's the blueprint of innovation."*

  🚀 Building scalable, impactful software that solves real-world problems.
  <br>
  🤝 Contributing to open-source and giving back to the developer community.
  <br>
  📚 Never stop learning — currently diving deep into Cloud Native & AI/ML.
  <br>
  🌍 Dream: To build technology that empowers millions across the globe.

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- ═══════════════════════════════════════════════════════════════ -->
## 🏆 GitHub Trophies
<!-- ═══════════════════════════════════════════════════════════════ -->

<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=gobinda-adhikari&theme=tokyonight&no-frame=true&no-bg=true&margin-w=10&column=7" width="98%" alt="Trophies" />
</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%">

<!-- CONTRIBUTION SNAKE -->
<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg" />
    <img alt="github-snake" src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" width="100%" />
  </picture>
</div>

<br>

<!-- FOOTER WAVE -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00d4ff,100:a855f7&height=120&section=footer" width="100%" />

<div align="center">

  ⭐ **If you find my work helpful, consider giving a star!** ⭐

  <br>

  **Built with 💜 by Gobinda Adhikari**

  <br>

  *"The only way to do great work is to love what you do." — Steve Jobs*

</div>`;

        // Populate code block
        document.getElementById('markdown-code').textContent = markdownCode;

        // Tab switching
        function switchTab(tab) {
            document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
            document.querySelectorAll('.tab-panel').forEach(panel => panel.classList.remove('active'));

            if (tab === 'preview') {
                document.querySelectorAll('.tab-btn')[0].classList.add('active');
                document.getElementById('preview-panel').classList.add('active');
            } else {
                document.querySelectorAll('.tab-btn')[1].classList.add('active');
                document.getElementById('code-panel').classList.add('active');
            }
        }

        // Copy to clipboard
        function copyCode() {
            navigator.clipboard.writeText(markdownCode).then(() => {
                const btn = document.getElementById('copyBtn');
                btn.classList.add('copied');
                btn.innerHTML = `
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg>
                    Copied!
                `;
                setTimeout(() => {
                    btn.classList.remove('copied');
                    btn.innerHTML = `
                        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="9" y="9" width="13" height="13" rx="2" ry="2"/><path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"/></svg>
                        Copy to Clipboard
                    `;
                }, 2500);
            });
        }

        // Intersection Observer for fade-in animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.project-card, .section-header, .stats-row, .vision-box').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });
    </script>

</body>
</html>
