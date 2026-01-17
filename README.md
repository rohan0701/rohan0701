<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rohan Sutar - Full-Stack Developer & AI Engineer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Poppins:wght@600;700&display=swap');
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        :root {
            --primary: #2563eb;
            --primary-dark: #1e40af;
            --secondary: #8b5cf6;
            --accent: #06b6d4;
            --dark: #0f172a;
            --dark-light: #1e293b;
            --gray: #64748b;
            --light: #f1f5f9;
            --white: #ffffff;
        }
        body {
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
            color: var(--light);
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
        }
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
        }
        .particle {
            position: absolute;
            width: 3px;
            height: 3px;
            background: var(--accent);
            border-radius: 50%;
            opacity: 0.4;
            animation: float 15s infinite;
        }
        @keyframes float {
            0%, 100% {
                transform: translateY(0) translateX(0);
            }
            50% {
                transform: translateY(-100px) translateX(50px);
            }
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 1;
        }
        /* Header Section */
        .header {
            text-align: center;
            padding: 60px 0;
            margin-bottom: 60px;
        }
        .profile-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            margin: 0 auto 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            box-shadow: 0 20px 60px rgba(37, 99, 235, 0.3);
            animation: fadeInScale 1s ease-out;
        }
        @keyframes fadeInScale {
            from {
                opacity: 0;
                transform: scale(0.5);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }
        .name {
            font-family: 'Poppins', sans-serif;
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 700;
            background: linear-gradient(135deg, #2563eb, #8b5cf6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 15px;
            animation: fadeInUp 1s ease-out 0.2s both;
        }
        .title {
            font-size: clamp(1.2rem, 2.5vw, 1.5rem);
            color: var(--accent);
            font-weight: 500;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease-out 0.4s both;
        }
        .bio {
            max-width: 700px;
            margin: 0 auto;
            color: var(--gray);
            font-size: 1.1rem;
            animation: fadeInUp 1s ease-out 0.6s both;
        }
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        /* Quick Stats */
        .quick-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 25px;
            margin: 50px 0;
        }
        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s ease;
        }
        .stat-card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.08);
            box-shadow: 0 20px 40px rgba(37, 99, 235, 0.2);
        }
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
        }
        .stat-label {
            color: var(--gray);
            font-size: 0.95rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        /* Section Styling */
        .section {
            margin: 80px 0;
        }
        .section-header {
            margin-bottom: 40px;
        }
        .section-title {
            font-family: 'Poppins', sans-serif;
            font-size: 2.2rem;
            font-weight: 700;
            color: var(--white);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        .section-title::before {
            content: '';
            width: 5px;
            height: 40px;
            background: linear-gradient(180deg, var(--primary), var(--secondary));
            border-radius: 10px;
        }
        .section-subtitle {
            color: var(--gray);
            font-size: 1.1rem;
            margin-left: 20px;
        }
        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }
        .skill-category {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 30px;
            transition: all 0.3s ease;
        }
        .skill-category:hover {
            background: rgba(255, 255, 255, 0.08);
            border-color: var(--primary);
        }
        .category-title {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--white);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .category-icon {
            font-size: 1.5rem;
        }
        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .skill-tag {
            background: rgba(37, 99, 235, 0.1);
            color: var(--accent);
            padding: 8px 16px;
            border-radius: 8px;
            font-size: 0.9rem;
            font-weight: 500;
            border: 1px solid rgba(37, 99, 235, 0.2);
            transition: all 0.3s ease;
        }
        .skill-tag:hover {
            background: rgba(37, 99, 235, 0.2);
            transform: translateY(-2px);
            border-color: var(--primary);
        }
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }
        .project-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 35px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }
        .project-card:hover::before {
            transform: scaleX(1);
        }
        .project-card:hover {
            transform: translateY(-8px);
            background: rgba(255, 255, 255, 0.08);
            box-shadow: 0 20px 60px rgba(37, 99, 235, 0.3);
        }
        .project-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
        }
        .project-icon {
            font-size: 2rem;
        }
        .project-title {
            font-size: 1.4rem;
            font-weight: 600;
            color: var(--white);
        }
        .project-features {
            list-style: none;
            margin-top: 20px;
        }
        .project-features li {
            color: var(--gray);
            padding: 8px 0;
            padding-left: 25px;
            position: relative;
        }
        .project-features li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: bold;
        }
        /* Experience & Achievements */
        .timeline {
            position: relative;
            padding-left: 40px;
        }
        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(180deg, var(--primary), var(--secondary));
        }
        .timeline-item {
            margin-bottom: 40px;
            position: relative;
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            left: -45px;
            top: 5px;
            width: 12px;
            height: 12px;
            background: var(--primary);
            border-radius: 50%;
            border: 3px solid var(--dark);
            box-shadow: 0 0 0 4px rgba(37, 99, 235, 0.2);
        }
        .achievement-title {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--white);
            margin-bottom: 8px;
        }
        .achievement-desc {
            color: var(--gray);
        }
        /* Contact Links */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }
        .contact-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            padding: 18px 30px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 12px;
            color: var(--white);
            text-decoration: none;
            font-weight: 600;
            font-size: 1.05rem;
            transition: all 0.3s ease;
        }
        .contact-btn:hover {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(37, 99, 235, 0.4);
        }
        .contact-icon {
            font-size: 1.5rem;
        }
        /* Footer */
        .footer {
            text-align: center;
            padding: 60px 20px 40px;
            color: var(--gray);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            margin-top: 80px;
        }
        .footer-motto {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--white);
            margin-bottom: 15px;
        }
        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 20px 15px;
            }
            .header {
                padding: 40px 0;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .timeline {
                padding-left: 30px;
            }
        }
        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Particle Background -->
    <div class="particles" id="particles"></div>
    <div class="container">
        <!-- Header -->
        <header class="header">
            <div class="profile-image">👨‍💻</div>
            <h1 class="name">Rohan Sutar</h1>
            <p class="title">Full-Stack Developer & AI Engineer</p>
            <p class="bio">Passionate software engineer specializing in building scalable web applications and AI-powered solutions. Committed to writing clean code and delivering exceptional user experiences.</p>
        </header>
        <!-- Quick Stats -->
        <div class="quick-stats">
            <div class="stat-card">
                <div class="stat-number">4+</div>
                <div class="stat-label">Projects Deployed</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">10+</div>
                <div class="stat-label">Technologies</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">100%</div>
                <div class="stat-label">Commitment</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">∞</div>
                <div class="stat-label">Learning Mode</div>
            </div>
        </div>
        <!-- Skills Section -->
        <section class="section fade-in">
            <div class="section-header">
                <h2 class="section-title">Technical Skills</h2>
                <p class="section-subtitle">Technologies I work with on a daily basis</p>
            </div>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3 class="category-title"><span class="category-icon">💻</span> Languages</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">SQL</span>
                        <span class="skill-tag">HTML5</span>
                        <span class="skill-tag">CSS3</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3 class="category-title"><span class="category-icon">⚡</span> Frameworks</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">Node.js</span>
                        <span class="skill-tag">Express</span>
                        <span class="skill-tag">Django</span>
                        <span class="skill-tag">Tailwind CSS</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3 class="category-title"><span class="category-icon">🗄️</span> Databases</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">MySQL</span>
                        <span class="skill-tag">SQLite</span>
                        <span class="skill-tag">ORM</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3 class="category-title"><span class="category-icon">🛠️</span> Tools & Platforms</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Git</span>
                        <span class="skill-tag">GitHub</span>
                        <span class="skill-tag">VS Code</span>
                        <span class="skill-tag">REST APIs</span>
                        <span class="skill-tag">Netlify</span>
                        <span class="skill-tag">Vercel</span>
                    </div>
                </div>
            </div>
        </section>
        <!-- Projects Section -->
        <section class="section fade-in">
            <div class="section-header">
                <h2 class="section-title">Featured Projects</h2>
                <p class="section-subtitle">Production-ready applications I've built and deployed</p>
            </div>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-header">
                        <span class="project-icon">📜</span>
                        <h3 class="project-title">Certificate Generator Platform</h3>
                    </div>
                    <ul class="project-features">
                        <li>Dynamic form-based certificate generation</li>
                        <li>Automated PDF download functionality</li>
                        <li>Email delivery system integration</li>
                        <li>Social media sharing capabilities</li>
                        <li>Production-ready deployment</li>
                    </ul>
                </div>
                <div class="project-card">
                    <div class="project-header">
                        <span class="project-icon">💬</span>
                        <h3 class="project-title">Multi-User Communication App</h3>
                    </div>
                    <ul class="project-features">
                        <li>Real-time messaging capabilities</li>
                        <li>Media and document sharing</li>
                        <li>Online/offline presence indicators</li>
                        <li>Progressive Web App (PWA)</li>
                        <li>Mobile and desktop responsive</li>
                    </ul>
                </div>
                <div class="project-card">
                    <div class="project-header">
                        <span class="project-icon">🗃️</span>
                        <h3 class="project-title">SQL Manager Web Application</h3>
                    </div>
                    <ul class="project-features">
                        <li>Secure CRUD operations</li>
                        <li>User authentication & authorization</li>
                        <li>ORM-based backend architecture</li>
                        <li>Intuitive admin dashboard</li>
                        <li>No manual SQL required</li>
                    </ul>
                </div>
                <div class="project-card">
                    <div class="project-header">
                        <span class="project-icon">🌤️</span>
                        <h3 class="project-title">AI Weather Application</h3>
                    </div>
                    <ul class="project-features">
                        <li>Real-time weather updates</li>
                        <li>AI-powered chat assistant</li>
                        <li>Voice input support</li>
                        <li>Mobile-first responsive design</li>
                        <li>Location-based forecasting</li>
                    </ul>
                </div>
            </div>
        </section>
        <!-- Achievements -->
        <section class="section fade-in">
            <div class="section-header">
                <h2 class="section-title">Achievements & Certifications</h2>
                <p class="section-subtitle">Professional milestones and recognitions</p>
            </div>
            <div class="timeline">
                <div class="timeline-item">
                    <h3 class="achievement-title">TCS iON Career Edge – Young Professional</h3>
                    <p class="achievement-desc">Completed comprehensive certification program focused on industry-ready skills and professional development.</p>
                </div>
                <div class="timeline-item">
                    <h3 class="achievement-title">Web Development Internship</h3>
                    <p class="achievement-desc">Gained hands-on experience in full-stack web development, working on real-world projects and client deliverables.</p>
                </div>
                <div class="timeline-item">
                    <h3 class="achievement-title">Software Development Internship</h3>
                    <p class="achievement-desc">Developed software solutions using modern frameworks and best practices in collaborative team environments.</p>
                </div>
                <div class="timeline-item">
                    <h3 class="achievement-title">Multiple Production Deployments</h3>
                    <p class="achievement-desc">Successfully deployed and maintained multiple full-stack applications serving real users in production environments.</p>
                </div>
            </div>
        </section>
        <!-- Contact Section -->
        <section class="section fade-in">
            <div class="section-header">
                <h2 class="section-title">Let's Connect</h2>
                <p class="section-subtitle">Open to opportunities and collaborations</p>
            </div>
            <div class="contact-grid">
                <a href="https://www.linkedin.com/in/rohan-sutar/" target="_blank" class="contact-btn">
                    <span class="contact-icon">💼</span>
                    LinkedIn Profile
                </a>
                <a href="https://github.com/rohan0701" target="_blank" class="contact-btn">
                    <span class="contact-icon">🐙</span>
                    GitHub Portfolio
                </a>
            </div>
        </section>
        <!-- Footer -->
        <footer class="footer">
            <p class="footer-motto">"Consistency beats intensity. Clean code scales. Build first, explain later."</p>
            <p>© 2025 Rohan Sutar. Crafted with precision and passion.</p>
        </footer>
    </div>
    <script>
        // Generate particles
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.top = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            particlesContainer.appendChild(particle);
        }
        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);
        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>
