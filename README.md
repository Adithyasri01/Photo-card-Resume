
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adithya Kumar Sridhar - Visual CV</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0f172a;
            --secondary: #1e293b;
            --accent: #3b82f6;
            --accent-light: #60a5fa;
            --text: #334155;
            --text-light: #64748b;
            --bg: #f8fafc;
            --card: #ffffff;
            --border: #e2e8f0;
        }

        body {
            font-family: 'Inter', -apple-system, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 40px 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .resume-container {
            width: 100%;
            max-width: 1000px;
            background: var(--card);
            border-radius: 24px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
            overflow: hidden;
            display: grid;
            grid-template-columns: 320px 1fr;
        }

        /* Left Sidebar - Photo Card Style */
        .sidebar {
            background: linear-gradient(180deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 40px 30px;
            position: relative;
            overflow: hidden;
        }

        .sidebar::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(59, 130, 246, 0.1) 0%, transparent 70%);
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 0.8; }
        }

        .photo-card {
            position: relative;
            z-index: 1;
            text-align: center;
            margin-bottom: 30px;
        }

        .photo-wrapper {
            width: 180px;
            height: 180px;
            margin: 0 auto 20px;
            position: relative;
        }

        .photo-ring {
            position: absolute;
            inset: -8px;
            border: 3px solid var(--accent-light);
            border-radius: 50%;
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .photo-ring::before,
        .photo-ring::after {
            content: '';
            position: absolute;
            border-radius: 50%;
            border: 2px solid transparent;
            border-top-color: var(--accent);
        }

        .photo-ring::before {
            inset: -12px;
            animation: rotate 15s linear infinite reverse;
        }

        .photo-ring::after {
            inset: -16px;
            border-top-color: rgba(255,255,255,0.3);
            animation: rotate 20s linear infinite;
        }

        .profile-photo {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid white;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        .name-badge {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            padding: 15px 20px;
            border-radius: 12px;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .name-badge h1 {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            margin-bottom: 5px;
            font-weight: 700;
        }

        .name-badge p {
            font-size: 0.85rem;
            opacity: 0.9;
            font-weight: 300;
        }

        .contact-stack {
            position: relative;
            z-index: 1;
            space-y: 12px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 12px;
            background: rgba(255,255,255,0.05);
            border-radius: 10px;
            margin-bottom: 10px;
            transition: all 0.3s;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .contact-item:hover {
            background: rgba(255,255,255,0.1);
            transform: translateX(5px);
        }

        .contact-icon {
            width: 36px;
            height: 36px;
            background: var(--accent);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
            flex-shrink: 0;
        }

        .contact-text {
            font-size: 0.8rem;
            line-height: 1.4;
        }

        .contact-text strong {
            display: block;
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            opacity: 0.7;
            margin-bottom: 2px;
        }

        .skills-cloud {
            position: relative;
            z-index: 1;
            margin-top: 30px;
        }

        .skills-cloud h3 {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 15px;
            opacity: 0.8;
        }

        .skill-bubbles {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .skill-bubble {
            background: rgba(59, 130, 246, 0.3);
            border: 1px solid rgba(255,255,255,0.2);
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 500;
            transition: all 0.3s;
        }

        .skill-bubble:hover {
            background: var(--accent);
            transform: scale(1.05);
        }

        /* Main Content */
        .main-content {
            padding: 40px;
            background: var(--card);
        }

        .header-section {
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid var(--border);
        }

        .role-title {
            font-size: 1.75rem;
            color: var(--primary);
            font-weight: 700;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .role-title::after {
            content: '';
            flex: 1;
            height: 2px;
            background: linear-gradient(90deg, var(--accent), transparent);
        }

        .tagline {
            color: var(--text-light);
            font-size: 1rem;
            line-height: 1.6;
        }

        .section {
            margin-bottom: 28px;
        }

        .section-title {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: var(--accent);
            font-weight: 700;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section-title::before {
            content: '';
            width: 30px;
            height: 3px;
            background: var(--accent);
            border-radius: 2px;
        }

        .experience-card {
            background: var(--bg);
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 15px;
            border-left: 4px solid var(--accent);
            transition: all 0.3s;
        }

        .experience-card:hover {
            transform: translateX(5px);
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .exp-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 8px;
        }

        .exp-title {
            font-weight: 700;
            color: var(--primary);
            font-size: 1rem;
        }

        .exp-date {
            font-size: 0.8rem;
            color: var(--accent);
            font-weight: 600;
            background: rgba(59, 130, 246, 0.1);
            padding: 4px 10px;
            border-radius: 20px;
        }

        .exp-company {
            color: var(--text-light);
            font-size: 0.9rem;
            margin-bottom: 10px;
            font-weight: 500;
        }

        .exp-points {
            list-style: none;
            font-size: 0.9rem;
            color: var(--text);
        }

        .exp-points li {
            padding-left: 16px;
            position: relative;
            margin-bottom: 6px;
            line-height: 1.5;
        }

        .exp-points li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: 700;
        }

        .highlight-metric {
            display: inline-block;
            background: linear-gradient(135deg, var(--accent), var(--accent-light));
            color: white;
            padding: 2px 8px;
            border-radius: 4px;
            font-weight: 700;
            font-size: 0.9em;
        }

        .project-showcase {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .project-card {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 20px;
            border-radius: 12px;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
        }

        .project-tag {
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            opacity: 0.8;
            margin-bottom: 8px;
        }

        .project-name {
            font-weight: 700;
            font-size: 0.95rem;
            margin-bottom: 10px;
            line-height: 1.3;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
        }

        .tech-pill {
            background: rgba(255,255,255,0.2);
            padding: 3px 8px;
            border-radius: 10px;
            font-size: 0.7rem;
        }

        .education-timeline {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .edu-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 15px;
            background: var(--bg);
            border-radius: 10px;
            border-left: 3px solid var(--accent);
        }

        .edu-icon {
            width: 40px;
            height: 40px;
            background: var(--accent);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            flex-shrink: 0;
        }

        .edu-details h4 {
            color: var(--primary);
            font-size: 0.95rem;
            margin-bottom: 3px;
        }

        .edu-details p {
            color: var(--text-light);
            font-size: 0.85rem;
        }

        .edu-status {
            margin-left: auto;
            font-size: 0.75rem;
            padding: 4px 10px;
            border-radius: 15px;
            background: rgba(56, 161, 105, 0.1);
            color: #059669;
            font-weight: 600;
        }

        .edu-status.pursuing {
            background: rgba(59, 130, 246, 0.1);
            color: var(--accent);
        }

        /* Print Styles */
        @media print {
            body {
                background: white;
                padding: 0;
            }

            .resume-container {
                box-shadow: none;
                max-width: 100%;
            }

            .sidebar::before,
            .photo-ring {
                animation: none;
            }

            .experience-card:hover,
            .contact-item:hover,
            .skill-bubble:hover {
                transform: none;
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .resume-container {
                grid-template-columns: 1fr;
            }

            .sidebar {
                padding: 30px 20px;
            }

            .photo-wrapper {
                width: 150px;
                height: 150px;
            }

            .main-content {
                padding: 30px 20px;
            }

            .project-showcase {
                grid-template-columns: 1fr;
            }

            .exp-header {
                flex-direction: column;
                gap: 5px;
            }
        }
    </style>
</head>
<body>
    <div class="resume-container">
        <!-- Sidebar with Photo -->
        <aside class="sidebar">
            <div class="photo-card">
                <div class="photo-wrapper">
                    <div class="photo-ring"></div>
                    <img src="Adithya.jpeg" alt="Adithya Kumar Sridhar" class="profile-photo">
                </div>
                <div class="name-badge">
                    <h1>Adithya Kumar<br>Sridhar</h1>
                    <p>Data & AI Professional</p>
                </div>
            </div>

            <div class="contact-stack">
                <div class="contact-item">
                    <div class="contact-icon">📍</div>
                    <div class="contact-text">
                        <strong>Location</strong>
                        London, United Kingdom
                    </div>
                </div>

                <div class="contact-item">
                    <div class="contact-icon">📧</div>
                    <div class="contact-text">
                        <strong>Email</strong>
                        adithyak.sri01@outlook.com
                    </div>
                </div>

                <div class="contact-item">
                    <div class="contact-icon">📱</div>
                    <div class="contact-text">
                        <strong>Phone</strong>
                        +44 7799 275840
                    </div>
                </div>

                <div class="contact-item">
                    <div class="contact-icon">💼</div>
                    <div class="contact-text">
                        <strong>LinkedIn</strong>
                        linkedin.com/in/adithya-kumar-sridhar
                    </div>
                </div>
            </div>

            <div class="skills-cloud">
                <h3>Core Expertise</h3>
                <div class="skill-bubbles">
                    <span class="skill-bubble">Python</span>
                    <span class="skill-bubble">SQL</span>
                    <span class="skill-bubble">Power BI</span>
                    <span class="skill-bubble">Machine Learning</span>
                    <span class="skill-bubble">Deep Learning</span>
                    <span class="skill-bubble">XAI</span>
                    <span class="skill-bubble">Data Analytics</span>
                    <span class="skill-bubble">Business Intelligence</span>
                    <span class="skill-bubble">CNNs</span>
                    <span class="skill-bubble">Medical Imaging</span>
                    <span class="skill-bubble">Stakeholder Management</span>
                    <span class="skill-bubble">Strategic Planning</span>
                </div>
            </div>
        </aside>

        <!-- Main Content -->
        <main class="main-content">
            <header class="header-section">
                <h2 class="role-title">MSc Artificial Intelligence and Data Science| Data Analyst</h2>
                <p class="tagline">Results-driven Data Analyst with 4+ years of experience transforming complex datasets into actionable business insights. Currently pursuing MSc in AI and Data Science at University of East London. Specialist in Explainable AI, predictive analytics, and business intelligence solutions that drive strategic decision-making.</p>
            </header>

            <section class="section">
                <h3 class="section-title">Professional Experience</h3>

                <div class="experience-card">
                    <div class="exp-header">
                        <span class="exp-title">Data Analyst / Business Research Analyst</span>
                        <span class="exp-date">Dec 2024 – July 2025</span>
                    </div>
                    <div class="exp-company">Freelance Consultant | London, UK</div>
                    <ul class="exp-points">
                        <li>Analysed multi-source datasets to identify trends and growth opportunities, enabling <span class="highlight-metric">data-driven strategic decisions</span> for clients</li>
                        <li>Architected interactive Power BI and Excel dashboards, <span class="highlight-metric">reducing manual reporting by 40%</span> and improving stakeholder decision speed</li>
                        <li>Conducted comprehensive market and competitor analysis using structured datasets, enhancing forecasting accuracy and business intelligence capabilities</li>
                        <li>Collaborated with cross-functional stakeholders to define KPIs, data requirements, and reporting standards across multiple projects</li>
                        <li>Utilised SQL and Python (Pandas, NumPy) for data cleaning, transformation, and validation ensuring high-quality downstream analytics</li>
                    </ul>
                </div>

                <div class="experience-card">
                    <div class="exp-header">
                        <span class="exp-title">Deputy Vice President, Special Quality Assurance</span>
                        <span class="exp-date">Feb 2018 – Sep 2024</span>
                    </div>
                    <div class="exp-company">Kotak Life Insurance | India</div>
                    <ul class="exp-points">
                        <li>Led quality assurance initiatives ensuring compliance with regulatory standards and operational excellence</li>
                        <li>Developed data-driven quality metrics and automated reporting frameworks, improving team efficiency</li>
                        <li>Managed cross-functional collaboration between operations, compliance, and technology teams</li>
                    </ul>
                </div>

                <div class="experience-card">
                    <div class="exp-header">
                        <span class="exp-title">Team Leader</span>
                        <span class="exp-date">Sep 2016 – Jan 2018</span>
                    </div>
                    <div class="exp-company">Flemingo DFS | India</div>
                    <ul class="exp-points">
                        <li>Managed team operations and performance metrics using data-driven approaches</li>
                        <li>Implemented analytical frameworks to enhance operational workflows and customer satisfaction</li>
                    </ul>
                </div>
            </section>

            <section class="section">
                <h3 class="section-title">Featured Projects</h3>
                <div class="project-showcase">
                    <div class="project-card">
                        <div class="project-tag">Explainable AI / Healthcare</div>
                        <div class="project-name">Cancer Detection Using Big Data & XAI</div>
                        <div class="project-tech">
                            <span class="tech-pill">CNNs</span>
                            <span class="tech-pill">Grad-CAM</span>
                            <span class="tech-pill">SHAP</span>
                            <span class="tech-pill">LIME</span>
                            <span class="tech-pill">Python</span>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-tag">Business Analytics / ML</div>
                        <div class="project-name">Customer Purchase Behaviour Dashboard</div>
                        <div class="project-tech">
                            <span class="tech-pill">Python</span>
                            <span class="tech-pill">SQL</span>
                            <span class="tech-pill">Power BI</span>
                            <span class="tech-pill">ML</span>
                            <span class="tech-pill">Segmentation</span>
                        </div>
                    </div>
                </div>
            </section>

            <section class="section">
                <h3 class="section-title">Education & Qualifications</h3>
                <div class="education-timeline">
                    <div class="edu-item">
                        <div class="edu-icon">🎓</div>
                        <div class="edu-details">
                            <h4>MSc Artificial Intelligence and Data Science</h4>
                            <p>University of East London, UK</p>
                        </div>
                        <span class="edu-status pursuing">Pursuing</span>
                    </div>

                    <div class="edu-item">
                        <div class="edu-icon">⚡</div>
                        <div class="edu-details">
                            <h4>M.Tech – Power Electronics and Drives</h4>
                            <p>VIT University, India</p>
                        </div>
                        <span class="edu-status">2016</span>
                    </div>

                    <div class="edu-item">
                        <div class="edu-icon">🔌</div>
                        <div class="edu-details">
                            <h4>B.Tech – Electrical and Electronics Engineering</h4>
                            <p>Bharath University, India</p>
                        </div>
                        <span class="edu-status">2013</span>
                    </div>
                </div>
            </section>

            <section class="section" style="margin-bottom: 0;">
                <h3 class="section-title">Technical Proficiency</h3>
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9rem;">
                    <div>
                        <strong style="color: var(--primary); display: block; margin-bottom: 5px;">Programming & Data</strong>
                        <p style="color: var(--text-light);">Python, SQL, Pandas, NumPy, Data Cleaning, Feature Engineering, EDA</p>
                    </div>
                    <div>
                        <strong style="color: var(--primary); display: block; margin-bottom: 5px;">Analytics & BI</strong>
                        <p style="color: var(--text-light);">Power BI, Looker Studio, Excel (Advanced), Dashboard Design, KPI Development</p>
                    </div>
                    <div>
                        <strong style="color: var(--primary); display: block; margin-bottom: 5px;">Machine Learning</strong>
                        <p style="color: var(--text-light);">Regression, Classification, Model Evaluation, CNNs, XAI, Deep Learning</p>
                    </div>
                    <div>
                        <strong style="color: var(--primary); display: block; margin-bottom: 5px;">Web & Marketing Analytics</strong>
                        <p style="color: var(--text-light);">Google Analytics, Google Tag Manager, Market Analysis, Forecasting</p>
                    </div>
                </div>
            </section>
        </main>
    </div>
</body>
</html>
