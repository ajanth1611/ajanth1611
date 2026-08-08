<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ajanth Rao | Data Analyst & Engineer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #00C9FF;
            --secondary: #92FE9D;
            --dark: #0a0e27;
            --darker: #050810;
            --text: #e0e0e0;
            --text-light: #a0a0a0;
            --accent: #ff006e;
            --success: #39ff14;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, var(--dark) 0%, var(--darker) 100%);
            color: var(--text);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* ===== SCROLLBAR ===== */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: var(--darker);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: 5px;
        }

        /* ===== NAVBAR ===== */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            backdrop-filter: blur(10px);
            background: rgba(10, 14, 39, 0.8);
            border-bottom: 1px solid rgba(0, 201, 255, 0.2);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            animation: slideDown 0.6s ease-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        nav ul {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        nav a {
            color: var(--text);
            text-decoration: none;
            font-size: 0.9rem;
            transition: color 0.3s;
            position: relative;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        /* ===== HERO SECTION ===== */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
            padding-top: 60px;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0, 201, 255, 0.2) 0%, transparent 70%);
            top: -100px;
            left: -100px;
            animation: float 8s ease-in-out infinite;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(146, 254, 157, 0.15) 0%, transparent 70%);
            bottom: -100px;
            right: -100px;
            animation: float 8s ease-in-out infinite 2s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(30px, 30px); }
        }

        .hero-content {
            z-index: 10;
            max-width: 800px;
            animation: fadeInUp 1s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 1rem;
            letter-spacing: -2px;
            line-height: 1.1;
        }

        .hero h1 .highlight {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .typing {
            min-height: 2.5rem;
            display: inline-block;
        }

        .typing::after {
            content: '|';
            animation: blink 1s infinite;
            color: var(--primary);
        }

        @keyframes blink {
            0%, 49% { opacity: 1; }
            50%, 100% { opacity: 0; }
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-light);
            margin-bottom: 2rem;
            line-height: 1.8;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 3rem;
        }

        .btn {
            padding: 0.9rem 2rem;
            border: 2px solid var(--primary);
            border-radius: 50px;
            background: transparent;
            color: var(--primary);
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
            position: relative;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--primary);
            border-radius: 50px;
            transition: width 0.3s;
            z-index: -1;
        }

        .btn:hover::before {
            width: 100%;
        }

        .btn:hover {
            color: var(--dark);
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 201, 255, 0.3);
        }

        .btn-secondary {
            border-color: var(--secondary);
            color: var(--secondary);
        }

        .btn-secondary::before {
            background: var(--secondary);
        }

        .btn-secondary:hover {
            color: var(--dark);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(10px); }
        }

        .scroll-indicator svg {
            width: 30px;
            height: 30px;
            stroke: var(--primary);
            stroke-width: 2;
            fill: none;
        }

        /* ===== STATS SECTION ===== */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
            padding: 2rem;
            background: rgba(0, 201, 255, 0.05);
            border-radius: 15px;
            border: 1px solid rgba(0, 201, 255, 0.1);
        }

        .stat {
            text-align: center;
        }

        .stat-value {
            font-size: 2.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: var(--text-light);
            font-size: 0.9rem;
        }

        /* ===== ABOUT SECTION ===== */
        .section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section h2 {
            font-size: 3rem;
            margin-bottom: 2rem;
            display: inline-block;
            position: relative;
            padding-bottom: 1rem;
        }

        .section h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 2px;
        }

        /* ===== PROJECTS SECTION ===== */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .project-card {
            background: rgba(0, 201, 255, 0.05);
            border: 1px solid rgba(0, 201, 255, 0.1);
            border-radius: 15px;
            padding: 2rem;
            transition: all 0.3s;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 201, 255, 0.1), transparent);
            transition: left 0.5s;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            border-color: var(--primary);
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 201, 255, 0.2);
            background: rgba(0, 201, 255, 0.08);
        }

        .project-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .project-card h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: var(--primary);
        }

        .project-meta {
            display: flex;
            gap: 0.5rem;
            margin: 1rem 0;
            flex-wrap: wrap;
        }

        .badge {
            background: rgba(0, 201, 255, 0.1);
            color: var(--primary);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            border: 1px solid rgba(0, 201, 255, 0.3);
        }

        .project-card p {
            color: var(--text-light);
            margin-bottom: 1rem;
            line-height: 1.6;
        }

        .project-stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(0, 201, 255, 0.1);
        }

        .stat-item {
            text-align: center;
        }

        .stat-item-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--success);
        }

        .stat-item-label {
            font-size: 0.8rem;
            color: var(--text-light);
        }

        /* ===== SKILLS SECTION ===== */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-category {
            background: rgba(0, 201, 255, 0.03);
            border: 1px solid rgba(0, 201, 255, 0.1);
            border-radius: 15px;
            padding: 2rem;
            transition: all 0.3s;
        }

        .skill-category:hover {
            border-color: var(--primary);
            background: rgba(0, 201, 255, 0.06);
        }

        .skill-category h3 {
            color: var(--primary);
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }

        .skill-item {
            margin-bottom: 1.5rem;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
        }

        .skill-level {
            color: var(--text-light);
            font-size: 0.8rem;
        }

        .skill-bar {
            height: 6px;
            background: rgba(0, 201, 255, 0.2);
            border-radius: 3px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 3px;
            transition: width 0.6s ease-out;
            width: 0%;
        }

        /* ===== CONTACT SECTION ===== */
        .contact {
            background: linear-gradient(135deg, rgba(0, 201, 255, 0.1) 0%, rgba(146, 254, 157, 0.05) 100%);
            border: 1px solid rgba(0, 201, 255, 0.2);
            border-radius: 20px;
            padding: 3rem;
            text-align: center;
            margin-top: 4rem;
        }

        .contact h2 {
            margin-bottom: 2rem;
        }

        .contact-links {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 2rem;
        }

        .contact-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.8rem 1.5rem;
            background: rgba(0, 201, 255, 0.1);
            border: 1px solid rgba(0, 201, 255, 0.3);
            border-radius: 50px;
            color: var(--primary);
            text-decoration: none;
            transition: all 0.3s;
        }

        .contact-link:hover {
            background: var(--primary);
            color: var(--dark);
            transform: translateY(-3px);
        }

        /* ===== FOOTER ===== */
        footer {
            text-align: center;
            padding: 2rem;
            color: var(--text-light);
            border-top: 1px solid rgba(0, 201, 255, 0.1);
            margin-top: 4rem;
        }

        /* ===== SCROLL ANIMATIONS ===== */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.6s ease-out forwards;
        }

        .stagger-1 { animation-delay: 0.1s; }
        .stagger-2 { animation-delay: 0.2s; }
        .stagger-3 { animation-delay: 0.3s; }
        .stagger-4 { animation-delay: 0.4s; }
        .stagger-5 { animation-delay: 0.5s; }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                flex-wrap: wrap;
                gap: 1rem;
                justify-content: center;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .section h2 {
                font-size: 2rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .contact {
                padding: 2rem;
            }
        }

        /* ===== GLITCH EFFECT (optional) ===== */
        .glitch {
            position: relative;
            display: inline-block;
        }

        .glitch::before,
        .glitch::after {
            content: attr(data-text);
            position: absolute;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
        }

        .glitch::before {
            color: var(--primary);
            z-index: -1;
            text-shadow: -2px 0 #FF006E;
            animation: glitch 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94) infinite;
        }

        .glitch::after {
            color: var(--secondary);
            z-index: -2;
            text-shadow: 2px 0 #00C9FF;
            animation: glitch 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94) reverse infinite;
        }

        @keyframes glitch {
            0% { clip-path: rect(0 0 0 0); }
            5% { clip-path: rect(10px, 9999px, 30px, 0); }
            10% { clip-path: rect(5px, 9999px, 10px, 0); }
            15% { clip-path: rect(5px, 9999px, 20px, 0); }
            20% { clip-path: rect(10px, 9999px, 10px, 0); }
            25% { clip-path: rect(5px, 9999px, 20px, 0); }
            30% { clip-path: rect(10px, 9999px, 10px, 0); }
            35% { clip-path: rect(0 0 0 0); }
        }

        .no-glitch {
            text-shadow: none !important;
        }
    </style>
</head>
<body>
    <!-- NAVBAR -->
    <nav>
        <div class="logo">Ajanth.</div>
        <ul>
            <li><a href="#about">About</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- HERO SECTION -->
    <section class="hero">
        <div class="hero-content">
            <h1>
                <span class="glitch no-glitch">Turning Raw Data Into</span><br>
                <span class="highlight">Decisions That Matter</span>
            </h1>
            
            <div class="typing">
                <span id="typed-text">Data Analyst & Engineer</span>
            </div>

            <p>
                I build dashboards, pipelines, and ML models that teams actually use.<br>
                <strong>Currently Open to Data Analytics & Engineering Internships</strong>
            </p>

            <div class="stats">
                <div class="stat fade-in stagger-1">
                    <div class="stat-value" data-value="19">0</div>
                    <div class="stat-label">GitHub Repos</div>
                </div>
                <div class="stat fade-in stagger-2">
                    <div class="stat-value" data-value="4">0</div>
                    <div class="stat-label">Projects Shipped</div>
                </div>
                <div class="stat fade-in stagger-3">
                    <div class="stat-value" data-value="94">0</div>
                    <div class="stat-label">ML Accuracy %</div>
                </div>
                <div class="stat fade-in stagger-4">
                    <div class="stat-value" data-value="50">0</div>
                    <div class="stat-label">Products in Catalog</div>
                </div>
            </div>

            <div class="cta-buttons">
                <a href="#projects" class="btn">View My Work</a>
                <a href="#contact" class="btn btn-secondary">Get In Touch</a>
            </div>
        </div>

        <div class="scroll-indicator">
            <svg viewBox="0 0 24 24">
                <polyline points="12 5 12 19 5 12 19 12"></polyline>
            </svg>
        </div>
    </section>

    <!-- PROJECTS SECTION -->
    <section class="section" id="projects">
        <h2>Featured Projects</h2>
        <p style="color: var(--text-light); margin-bottom: 2rem;">4 end-to-end projects that solve real problems</p>
        
        <div class="projects-grid">
            <!-- Project 1 -->
            <div class="project-card fade-in">
                <div class="project-icon">📊</div>
                <h3>Netflix Analytics</h3>
                <div class="project-meta">
                    <span class="badge">Power BI</span>
                    <span class="badge">SQL</span>
                    <span class="badge">Data Analysis</span>
                </div>
                <p>Interactive dashboard analyzing 8,800+ Netflix titles. Uncovers content and viewership trends across genres, countries, and time.</p>
                <div class="project-stats">
                    <div class="stat-item">
                        <div class="stat-item-value">8.8K</div>
                        <div class="stat-item-label">Titles</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-item-value">200+</div>
                        <div class="stat-item-label">Countries</div>
                    </div>
                </div>
            </div>

            <!-- Project 2 -->
            <div class="project-card fade-in stagger-1">
                <div class="project-icon">❤️</div>
                <h3>Heart Disease Predictor</h3>
                <div class="project-meta">
                    <span class="badge">ML</span>
                    <span class="badge">XGBoost</span>
                    <span class="badge">Streamlit</span>
                </div>
                <p>ML model predicting cardiac risk from patient metrics. Deployed web app with real-time predictions and explainability.</p>
                <div class="project-stats">
                    <div class="stat-item">
                        <div class="stat-item-value">94%</div>
                        <div class="stat-item-label">Accuracy</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-item-value">0.91</div>
                        <div class="stat-item-label">ROC-AUC</div>
                    </div>
                </div>
            </div>

            <!-- Project 3 -->
            <div class="project-card fade-in stagger-2">
                <div class="project-icon">🌱</div>
                <h3>AgroDetect AI</h3>
                <div class="project-meta">
                    <span class="badge">Deep Learning</span>
                    <span class="badge">CNN</span>
                    <span class="badge">TensorFlow</span>
                </div>
                <p>Plant disease detection from leaf images using CNN. Helps farmers catch diseases early and reduce crop loss.</p>
                <div class="project-stats">
                    <div class="stat-item">
                        <div class="stat-item-value">88%</div>
                        <div class="stat-item-label">Accuracy</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-item-value">15+</div>
                        <div class="stat-item-label">Diseases</div>
                    </div>
                </div>
            </div>

            <!-- Project 4 -->
            <div class="project-card fade-in stagger-3">
                <div class="project-icon">🛒</div>
                <h3>OrganNova E-Commerce</h3>
                <div class="project-meta">
                    <span class="badge">React</span>
                    <span class="badge">Firebase</span>
                    <span class="badge">Full-Stack</span>
                </div>
                <p>Full-stack organic vegetable e-commerce platform. Real-time inventory, secure checkout, responsive design.</p>
                <div class="project-stats">
                    <div class="stat-item">
                        <div class="stat-item-value">50+</div>
                        <div class="stat-item-label">Products</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-item-value">4</div>
                        <div class="stat-item-label">Checkout Steps</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SKILLS SECTION -->
    <section class="section" id="skills">
        <h2>Technical Skills</h2>
        <p style="color: var(--text-light); margin-bottom: 2rem;">Hands-on experience across the full stack</p>
        
        <div class="skills-grid">
            <!-- Data Analytics -->
            <div class="skill-category fade-in">
                <h3>📊 Data Analytics</h3>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>SQL</span>
                        <span class="skill-level">Expert</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 90%"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>Power BI</span>
                        <span class="skill-level">Advanced</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 85%"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>Excel</span>
                        <span class="skill-level">Advanced</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 80%"></div>
                    </div>
                </div>
            </div>

            <!-- Machine Learning -->
            <div class="skill-category fade-in stagger-1">
                <h3>🤖 Machine Learning</h3>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>Python</span>
                        <span class="skill-level">Advanced</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 85%"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>Scikit-Learn</span>
                        <span class="skill-level">Advanced</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 82%"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>TensorFlow/Keras</span>
                        <span class="skill-level">Intermediate</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 75%"></div>
                    </div>
                </div>
            </div>

            <!-- Web & Cloud -->
            <div class="skill-category fade-in stagger-2">
                <h3>☁️ Web & Cloud</h3>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>React</span>
                        <span class="skill-level">Intermediate</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 75%"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>Firebase</span>
                        <span class="skill-level">Intermediate</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 78%"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-name">
                        <span>AWS/GCP</span>
                        <span class="skill-level">Beginner</span>
                    </div>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 60%"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CONTACT SECTION -->
    <section class="section" id="contact">
        <div class="contact fade-in">
            <h2>Let's Work Together</h2>
            <p style="color: var(--text-light); margin-bottom: 2rem; font-size: 1.1rem;">
                I'm actively looking for Data Analyst & Engineering internships.<br>
                Let's build something great together.
            </p>
            
            <div class="contact-links">
                <a href="https://www.linkedin.com/in/kulkarni-ajanth-rao-b35243356" class="contact-link" target="_blank">
                    💼 LinkedIn
                </a>
                <a href="mailto:bhavanikulkarni24@gmail.com" class="contact-link">
                    📧 Email
                </a>
                <a href="https://github.com/ajanth1611" class="contact-link" target="_blank">
                    🐙 GitHub
                </a>
            </div>

            <p style="color: var(--text-light); font-size: 0.9rem; margin-top: 2rem;">
                📍 India | 🎓 B.Tech CSE | ✨ Open to Opportunities
            </p>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <p>© 2026 Ajanth Rao. Built with passion for data.</p>
    </footer>

    <script>
        // Typing Animation
        const textToType = "Data Analyst & Engineer";
        const typedElement = document.getElementById("typed-text");
        let charIndex = 0;

        function typeText() {
            if (charIndex < textToType.length) {
                typedElement.textContent += textToType.charAt(charIndex);
                charIndex++;
                setTimeout(typeText, 80);
            }
        }

        // Start typing after page loads
        window.addEventListener("load", typeText);

        // Animate stats counting
        function animateStats() {
            const stats = document.querySelectorAll(".stat-value");
            
            stats.forEach(stat => {
                const target = parseInt(stat.getAttribute("data-value"));
                let current = 0;
                
                const increment = target / 30;
                
                const updateStat = () => {
                    current += increment;
                    if (current < target) {
                        stat.textContent = Math.floor(current);
                        setTimeout(updateStat, 50);
                    } else {
                        stat.textContent = target;
                    }
                };
                
                updateStat();
            });
        }

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -100px 0px"
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add("fade-in");
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        // Observe project cards and skill categories
        document.querySelectorAll(".project-card, .skill-category, .contact").forEach(el => {
            observer.observe(el);
        });

        // Animate skill bars on scroll
        const skillObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const skillBars = entry.target.querySelectorAll(".skill-progress");
                    skillBars.forEach(bar => {
                        const width = bar.style.width;
                        bar.style.width = "0%";
                        setTimeout(() => {
                            bar.style.width = width;
                        }, 100);
                    });
                    skillObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.3 });

        document.querySelectorAll(".skill-category").forEach(el => {
            skillObserver.observe(el);
        });

        // Animate stats when section comes into view
        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateStats();
                    statsObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.3 });

        const statsSection = document.querySelector(".stats");
        if (statsSection) statsObserver.observe(statsSection);

        // Smooth scroll for navigation
        document.querySelectorAll("a[href^='#']").forEach(anchor => {
            anchor.addEventListener("click", (e) => {
                e.preventDefault();
                const target = document.querySelector(anchor.getAttribute("href"));
                if (target) {
                    target.scrollIntoView({ behavior: "smooth" });
                }
            });
        });

        // Add stagger animation delay to project cards
        document.querySelectorAll(".project-card").forEach((card, index) => {
            card.style.animationDelay = `${index * 0.1}s`;
        });

        // Scroll indicator fade out
        const scrollIndicator = document.querySelector(".scroll-indicator");
        window.addEventListener("scroll", () => {
            if (window.scrollY > 100) {
                scrollIndicator.style.opacity = "0";
                scrollIndicator.style.pointerEvents = "none";
            } else {
                scrollIndicator.style.opacity = "1";
                scrollIndicator.style.pointerEvents = "auto";
            }
        });
    </script>
</body>
</html>
