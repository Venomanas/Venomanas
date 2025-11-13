<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anas-Peeds | GitHub Profile</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        :root {
            --primary: #6e44ff;
            --secondary: #b892ff;
            --accent: #ff6b6b;
            --dark: #1a1a2e;
            --darker: #0f0f1a;
            --light: #f8f9fa;
            --gray: #8a8fa3;
        }

        body {
            background: linear-gradient(135deg, var(--darker), var(--dark));
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Header with animated background */
        .header {
            position: relative;
            height: 300px;
            border-radius: 20px;
            overflow: hidden;
            margin-bottom: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        .header-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, var(--primary), var(--secondary), var(--accent));
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            z-index: -2;
        }

        .header-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(10, 10, 20, 0.7);
            z-index: -1;
        }

        .header-content {
            position: relative;
            z-index: 1;
            padding: 2rem;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Profile Section */
        .profile {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
            animation: fadeIn 1s ease;
        }

        .avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 4px solid var(--primary);
            margin-right: 2rem;
            position: relative;
            overflow: hidden;
            box-shadow: 0 0 20px rgba(110, 68, 255, 0.5);
            animation: pulse 2s infinite;
        }

        .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .profile-info h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .profile-info h2 {
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 1rem;
            font-weight: 400;
        }

        .tagline {
            font-style: italic;
            margin-bottom: 1rem;
            color: var(--secondary);
            position: relative;
            padding-left: 1.5rem;
        }

        .tagline::before {
            content: """;
            position: absolute;
            left: 0;
            top: 0;
            font-size: 1.5rem;
            color: var(--accent);
        }

        /* Stats */
        .stats {
            display: flex;
            gap: 2rem;
            margin-bottom: 2rem;
            animation: slideUp 1s ease;
        }

        .stat {
            text-align: center;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            flex: 1;
            transition: transform 0.3s ease, background 0.3s ease;
        }

        .stat:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.1);
        }

        .stat-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--gray);
        }

        /* Sections */
        .section {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 2rem;
            margin-bottom: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            animation: fadeIn 1s ease;
        }

        .section-title {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: var(--secondary);
            display: flex;
            align-items: center;
        }

        .section-title i {
            margin-right: 0.75rem;
            font-size: 1.2rem;
        }

        /* Skills */
        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .skill {
            background: rgba(110, 68, 255, 0.2);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            display: flex;
            align-items: center;
            transition: all 0.3s ease;
        }

        .skill:hover {
            background: rgba(110, 68, 255, 0.4);
            transform: scale(1.05);
        }

        .skill i {
            margin-right: 0.5rem;
            color: var(--secondary);
        }

        /* Contribution Graph */
        .contribution-graph {
            display: grid;
            grid-template-columns: repeat(53, 1fr);
            grid-gap: 4px;
            margin-top: 1rem;
        }

        .contribution-cell {
            width: 12px;
            height: 12px;
            border-radius: 2px;
            background: rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .contribution-cell:hover {
            transform: scale(1.5);
        }

        .contribution-cell.low {
            background: rgba(110, 68, 255, 0.4);
        }

        .contribution-cell.medium {
            background: rgba(110, 68, 255, 0.6);
        }

        .contribution-cell.high {
            background: rgba(110, 68, 255, 0.8);
        }

        .contribution-cell.very-high {
            background: rgba(110, 68, 255, 1);
        }

        /* Projects */
        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .project {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 1.5rem;
            transition: all 0.3s ease;
            border-left: 4px solid var(--primary);
        }

        .project:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }

        .project h3 {
            margin-bottom: 0.5rem;
            color: var(--secondary);
        }

        .project p {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .project-lang {
            display: inline-block;
            padding: 0.25rem 0.75rem;
            background: rgba(184, 146, 255, 0.2);
            border-radius: 15px;
            font-size: 0.8rem;
            color: var(--secondary);
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from { transform: translateY(20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(110, 68, 255, 0.7); }
            70% { box-shadow: 0 0 0 10px rgba(110, 68, 255, 0); }
            100% { box-shadow: 0 0 0 0 rgba(110, 68, 255, 0); }
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 2rem 0;
            color: var(--gray);
            font-size: 0.9rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 1rem;
        }

        .social-link {
            color: var(--light);
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            color: var(--secondary);
            transform: translateY(-5px);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .profile {
                flex-direction: column;
                text-align: center;
            }
            
            .avatar {
                margin-right: 0;
                margin-bottom: 1rem;
            }
            
            .stats {
                flex-direction: column;
                gap: 1rem;
            }
            
            .projects {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header with animated background -->
        <div class="header">
            <div class="header-bg"></div>
            <div class="header-overlay"></div>
            <div class="header-content">
                <h1>Turning Ideas into Digital Reality</h1>
                <p>Full-Stack Developer & Open Source Enthusiast</p>
            </div>
        </div>

        <!-- Profile Section -->
        <div class="profile">
            <div class="avatar">
                <!-- Placeholder for avatar image -->
                <div style="width:100%;height:100%;background:linear-gradient(45deg, var(--primary), var(--accent));display:flex;align-items:center;justify-content:center;color:white;font-size:3rem;">A</div>
            </div>
            <div class="profile-info">
                <h1>Anas (3FTW)</h1>
                <h2>Venomans: he/nm</h2>
                <p class="tagline">Peace comes from building firms, not from painting crowds.</p>
                <button style="background:var(--primary);color:white;border:none;padding:0.5rem 1.5rem;border-radius:5px;cursor:pointer;transition:all 0.3s ease;">
                    <i class="fas fa-edit"></i> Edit Profile
                </button>
            </div>
        </div>

        <!-- Stats -->
        <div class="stats">
            <div class="stat">
                <div class="stat-value">204</div>
                <div class="stat-label">Contributions</div>
            </div>
            <div class="stat">
                <div class="stat-value">28</div>
                <div class="stat-label">Repositories</div>
            </div>
            <div class="stat">
                <div class="stat-value">6</div>
                <div class="stat-label">Projects</div>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="section">
            <h2 class="section-title"><i class="fas fa-code"></i> Skills & Technologies</h2>
            <div class="skills">
                <div class="skill"><i class="fab fa-python"></i> Python</div>
                <div class="skill"><i class="fab fa-js-square"></i> JavaScript</div>
                <div class="skill"><i class="fab fa-react"></i> React</div>
                <div class="skill"><i class="fab fa-node-js"></i> Node.js</div>
                <div class="skill"><i class="fas fa-database"></i> MongoDB</div>
                <div class="skill"><i class="fab fa-git-alt"></i> Git</div>
                <div class="skill"><i class="fas fa-cloud"></i> AWS</div>
                <div class="skill"><i class="fas fa-mobile-alt"></i> Responsive Design</div>
            </div>
        </div>

        <!-- Contribution Activity -->
        <div class="section">
            <h2 class="section-title"><i class="fas fa-chart-line"></i> Contribution Activity</h2>
            <p>204 contributions in the last year</p>
            <div class="contribution-graph" id="contributionGraph">
                <!-- Contribution cells will be generated by JavaScript -->
            </div>
        </div>

        <!-- Projects Section -->
        <div class="section">
            <h2 class="section-title"><i class="fas fa-project-diagram"></i> Featured Projects</h2>
            <div class="projects">
                <div class="project">
                    <h3>Python Compiler</h3>
                    <p>A simple Python compiler with dynamic typing and display scripts.</p>
                    <span class="project-lang">Python</span>
                </div>
                <div class="project">
                    <h3>Anas-Peeds Website</h3>
                    <p>Important new panels created with friends, libraries, TypeScript.</p>
                    <span class="project-lang">TypeScript</span>
                </div>
                <div class="project">
                    <h3>Document Converter</h3>
                    <p>Converting documents, handling missing images, and existing signatures.</p>
                    <span class="project-lang">JavaScript</span>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <div class="social-links">
                <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                <a href="#" class="social-link"><i class="fab fa-linkedin"></i></a>
                <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-link"><i class="fas fa-envelope"></i></a>
            </div>
            <p>© 2023 Anas (3FTW) | Crafting digital experiences with code</p>
        </div>
    </div>

    <script>
        // Generate contribution graph
        const graph = document.getElementById('contributionGraph');
        const contributions = [0, 1, 2, 3]; // Contribution levels
        
        for (let i = 0; i < 365; i++) {
            const cell = document.createElement('div');
            const level = contributions[Math.floor(Math.random() * contributions.length)];
            
            cell.className = 'contribution-cell';
            if (level === 1) cell.classList.add('low');
            else if (level === 2) cell.classList.add('medium');
            else if (level === 3) cell.classList.add('high');
            else if (level === 4) cell.classList.add('very-high');
            
            graph.appendChild(cell);
        }

        // Add hover effect to skills
        document.querySelectorAll('.skill').forEach(skill => {
            skill.addEventListener('mouseover', function() {
                this.style.transform = 'scale(1.1)';
            });
            
            skill.addEventListener('mouseout', function() {
                this.style.transform = 'scale(1)';
            });
        });

        // Animate stats on scroll
        const observerOptions = {
            threshold: 0.5
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'slideUp 1s ease forwards';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.stat').forEach(stat => {
            observer.observe(stat);
        });
    </script>
</body>
</html>
