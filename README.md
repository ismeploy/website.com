<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vuth Sovannara | Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Raleway:wght@800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary: #10b981;
            --dark: #1e293b;
            --light: #f8fafc;
            --gray: #94a3b8;
            --accent: #f97316;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #0f172a, #1e293b);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        section {
            padding: 80px 0;
        }

        h1, h2, h3, h4 {
            font-weight: 700;
            line-height: 1.2;
        }

        h1 {
            font-size: 4rem;
            margin-bottom: 20px;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 40px;
            text-align: center;
            position: relative;
        }

        h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: var(--primary);
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
        }

        p {
            margin-bottom: 15px;
            color: var(--gray);
        }

        a {
            text-decoration: none;
            color: var(--primary);
            transition: var(--transition);
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: var(--primary);
            color: white;
            border-radius: 30px;
            font-weight: 500;
            transition: var(--transition);
            border: 2px solid transparent;
            cursor: pointer;
        }

        .btn:hover {
            background: transparent;
            border-color: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .btn-secondary {
            background: var(--secondary);
        }

        .btn-secondary:hover {
            border-color: var(--secondary);
        }

        /* Navigation */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            padding: 20px 0;
            transition: var(--transition);
        }

        header.scrolled {
            background: rgba(30, 41, 59, 0.95);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            padding: 15px 0;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Raleway', sans-serif;
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--light);
        }

        .logo span {
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            color: var(--light);
            font-weight: 500;
            position: relative;
        }

        .nav-links a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--primary);
            bottom: -5px;
            left: 0;
            transition: var(--transition);
        }

        .nav-links a:hover:after,
        .nav-links a.active:after {
            width: 100%;
        }

        .mobile-menu {
            display: none;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--primary), transparent);
            top: -250px;
            right: -250px;
            opacity: 0.2;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--secondary), transparent);
            bottom: -150px;
            left: -150px;
            opacity: 0.2;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 600px;
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: var(--primary);
            margin-bottom: 10px;
            display: block;
        }

        .hero-title {
            font-size: 3.5rem;
            margin-bottom: 20px;
            color: var(--light);
            line-height: 1.2;
        }

        .hero-title span {
            color: var(--primary);
        }

        .hero-description {
            font-size: 1.1rem;
            margin-bottom: 30px;
            max-width: 500px;
        }

        .hero-btns {
            display: flex;
            gap: 15px;
        }

        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 30px;
        }

        .social-icons a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .social-icons a:hover {
            background: var(--primary);
            transform: translateY(-5px);
        }

        /* About Section */
        .about {
            background: var(--dark);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-image {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .about-image img {
            width: 100%;
            display: block;
            transition: var(--transition);
        }

        .about-image:hover img {
            transform: scale(1.05);
        }

        .about-text h3 {
            margin-bottom: 20px;
        }

        .about-text p {
            margin-bottom: 20px;
        }

        .info-list {
            margin: 30px 0;
        }

        .info-item {
            display: flex;
            margin-bottom: 15px;
        }

        .info-item strong {
            min-width: 120px;
            color: var(--light);
        }

        /* Skills Section */
        .skills {
            background: linear-gradient(to bottom, #0f172a, #1e293b);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 30px;
        }

        .skill-category h3 {
            margin-bottom: 20px;
            display: flex;
            align-items: center;
        }

        .skill-category h3 i {
            margin-right: 10px;
            color: var(--primary);
        }

        .skill-item {
            margin-bottom: 25px;
        }

        .skill-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
        }

        .skill-bar {
            height: 10px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: var(--primary);
            border-radius: 5px;
            position: relative;
            width: 0;
            transition: width 1.5s ease-in-out;
        }

        .skill-progress::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            animation: shine 2s infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        /* Portfolio Section */
        .portfolio {
            background: var(--dark);
        }

        .portfolio-filters {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 40px;
        }

        .filter-btn {
            padding: 8px 20px;
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--light);
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
        }

        .filter-btn.active,
        .filter-btn:hover {
            background: var(--primary);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .portfolio-item {
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transform: translateY(0);
            transition: var(--transition);
        }

        .portfolio-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        .portfolio-image {
            height: 250px;
            overflow: hidden;
        }

        .portfolio-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .portfolio-item:hover .portfolio-image img {
            transform: scale(1.1);
        }

        .portfolio-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(37, 99, 235, 0.9);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            opacity: 0;
            transition: var(--transition);
        }

        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }

        .portfolio-overlay h3 {
            color: white;
            margin-bottom: 10px;
            text-align: center;
        }

        .portfolio-overlay p {
            color: rgba(255, 255, 255, 0.8);
            text-align: center;
            margin-bottom: 20px;
        }

        .portfolio-overlay a {
            color: white;
            background: var(--secondary);
            padding: 8px 20px;
            border-radius: 30px;
            font-size: 0.9rem;
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(to bottom, #1e293b, #0f172a);
        }

        .contact-wrapper {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 50px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background: rgba(37, 99, 235, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: var(--primary);
        }

        .contact-text h3 {
            font-size: 1.2rem;
            margin-bottom: 5px;
        }

        .contact-form {
            background: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 10px;
            backdrop-filter: blur(10px);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: var(--light);
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            background: rgba(255, 255, 255, 0.08);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            color: var(--light);
            transition: var(--transition);
        }

        .form-control:focus {
            border-color: var(--primary);
            outline: none;
            background: rgba(37, 99, 235, 0.05);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background: #0f172a;
            padding: 30px 0;
            text-align: center;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .footer-logo {
            font-family: 'Raleway', sans-serif;
            font-size: 1.5rem;
            font-weight: 800;
            margin-bottom: 20px;
        }

        .footer-logo span {
            color: var(--primary);
        }

        .footer-social {
            display: flex;
            gap: 15px;
            margin-bottom: 20px;
        }

        .footer-social a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .footer-social a:hover {
            background: var(--primary);
            transform: translateY(-3px);
        }

        .copyright {
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .about-content,
            .contact-wrapper,
            .skills-grid {
                grid-template-columns: 1fr;
            }

            .hero-title {
                font-size: 3rem;
            }
        }

        @media (max-width: 768px) {
            .mobile-menu {
                display: block;
                font-size: 1.5rem;
            }

            .nav-links {
                position: fixed;
                top: 80px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 80px);
                background: var(--dark);
                flex-direction: column;
                align-items: center;
                padding-top: 50px;
                transition: var(--transition);
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links li {
                margin: 15px 0;
            }

            .hero-btns {
                flex-direction: column;
                gap: 10px;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            h1 {
                font-size: 3rem;
            }

            h2 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">Vuth<span>Dev</span></div>
                <ul class="nav-links">
                    <li><a href="#home" class="active">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#portfolio">Portfolio</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="mobile-menu">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <span class="hero-subtitle">Hello, I'm</span>
                <h1 class="hero-title">Vuth <span>Sovannara</span></h1>
                <p class="hero-description">A passionate web developer specializing in creating modern, responsive websites and applications with clean code and user-friendly interfaces.</p>
                <div class="hero-btns">
                    <a href="#portfolio" class="btn">View My Work</a>
                    <a href="#contact" class="btn btn-secondary">Contact Me</a>
                </div>
                <div class="social-icons">
                   <a href="https://t.me/ahhpl0yy_bot" target="_blank"><i class="fab fa-telegram"></i></a>
                   <a href="https://github.com/vuthsovannara" target="_blank"><i class="fab fa-github"></i></a>
                   <a href="https://www.tiktok.com/@ahhpl0yy?_t=ZS-8wv0FvhUoWe&_r=1" target="_blank"><i class="fab fa-tiktok"></i></a>
                   <a href="https://www.facebook.com/share/1UTC8SNFYB/?mibextid=wwXIfr" target="_blank"><i class="fab fa-facebook-f"></i></a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <h2>About Me</h2>
            <div class="about-content">
                <div class="about-image">
                    <img src="https://scontent.fpnh2-1.fna.fbcdn.net/v/t39.30808-6/500531076_729777589391786_68598103500527204_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=6ee11a&_nc_eui2=AeGKLev0FxSZCMt-9je6GdkdF6wEpzaIXBQXrASnNohcFIx4rOzz82g1H1bjOnyTOYbomb1UAr66Zyu9D9Lsne6Y&_nc_ohc=tKk5SbasUJ4Q7kNvwFtJwg1&_nc_oc=AdlZmzcskQw22Gakm3PfY_ZKOfrXnBVqiM3_QWyNBDc0zICbNIIsPlWwOAxniIIenuU&_nc_zt=23&_nc_ht=scontent.fpnh2-1.fna&_nc_gid=BT4LNbiMeMxjenztwmkAMA&oh=00_AfII6ZaQDgvIVfvy0OL2oPlocbYcmKopsilU11MFvEaAeQ&oe=6845C5BB" alt="Vuth Sovannara">
                </div>
                <div class="about-text">
                    <h3>Web Developer & UI/UX Designer</h3>
                    <p>Hello! I'm Vuth Sovannara, a passionate web developer with over 3 years of experience in building modern websites and web applications. I specialize in frontend development with a strong focus on creating intuitive user experiences.</p>
                    <p>My approach combines technical expertise with creative problem-solving to deliver solutions that meet both business requirements and user needs. I'm committed to writing clean, efficient code and staying up-to-date with the latest web technologies.</p>
                    
                    <div class="info-list">
                        <div class="info-item">
                            <strong>Name:</strong>
                            <span>Vuth Sovannara<span><
                            <strong>Email:</strong>
                            <span>vuthsovannara308@gmail.com</span>
                        </div>
                        <div class="info-item">
                            <strong>From:</strong>
                            <span>Kandal, Cambodia</span>
                        </div>
                        <div class="info-item">
                            <strong>Freelance:</strong>
                            <span>Available</span>
                        </div>
                    </div>
                    
                    <a href="#" class="btn">Download CV</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills">
        <div class="container">
            <h2>My Skills</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3><i class="fas fa-code"></i> Technical Skills</h3>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>HTML5 & CSS3</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>JavaScript</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>React.js</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Node.js</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3><i class="fas fa-paint-brush"></i> Design Skills</h3>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>UI/UX Design</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Figma</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Responsive Design</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Adobe Photoshop</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 75%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="portfolio">
        <div class="container">
            <h2>My Portfolio</h2>
            <div class="portfolio-filters">
                <button class="filter-btn active" data-filter="all">All</button>
                <button class="filter-btn" data-filter="web">Web Design</button>
                <button class="filter-btn" data-filter="app">App Development</button>
                <button class="filter-btn" data-filter="ui">UI/UX</button>
            </div>
            <div class="portfolio-grid">
                <!-- Project 1 -->
                <div class="portfolio-item" data-category="web">
                    <div class="portfolio-image">
                        <img src="https://images.unsplash.com/photo-1551434678-e076c223a692?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="Project 1">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>E-commerce Website</h3>
                        <p>Fully responsive e-commerce platform with payment integration</p>
                        <a href="#">View Project</a>
                    </div>
                </div>
                
                <!-- Project 2 -->
                <div class="portfolio-item" data-category="app">
                    <div class="portfolio-image">
                        <img src="https://images.unsplash.com/photo-1519225421980-715cb0215aed?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="Project 2">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>Fitness Mobile App</h3>
                        <p>Health tracking application with workout plans and progress analytics</p>
                        <a href="#">View Project</a>
                    </div>
                </div>
                
                <!-- Project 3 -->
                <div class="portfolio-item" data-category="ui">
                    <div class="portfolio-image">
                        <img src="https://images.unsplash.com/photo-1467232004584-a241de8bcf5d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1169&q=80" alt="Project 3">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>Travel App UI Design</h3>
                        <p>Modern UI design for a travel booking application</p>
                        <a href="#">View Project</a>
                    </div>
                </div>
                
                <!-- Project 4 -->
                <div class="portfolio-item" data-category="web">
                    <div class="portfolio-image">
                        <img src="https://images.unsplash.com/photo-1547658719-da2b51169166?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1160&q=80" alt="Project 4">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>Corporate Dashboard</h3>
                        <p>Analytics dashboard for business intelligence</p>
                        <a href="#">View Project</a>
                    </div>
                </div>
                
                <!-- Project 5 -->
                <div class="portfolio-item" data-category="app">
                    <div class="portfolio-image">
                        <img src="https://images.unsplash.com/photo-1558655146-d09347e92766?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1164&q=80" alt="Project 5">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>Food Delivery App</h3>
                        <p>Mobile application for restaurant food ordering</p>
                        <a href="#">View Project</a>
                    </div>
                </div>
                
                <!-- Project 6 -->
                <div class="portfolio-item" data-category="ui">
                    <div class="portfolio-image">
                        <img src="https://images.unsplash.com/photo-1551650975-87deedd944c3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1074&q=80" alt="Project 6">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>Banking App UI</h3>
                        <p>Modern banking interface with dark mode</p>
                        <a href="#">View Project</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2>Contact Me</h2>
            <div class="contact-wrapper">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div class="contact-text">
                            <h3>Location</h3>
                            <p>Kandal, Cambodia</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-text">
                            <h3>Email</h3>
                            <p>vuthsovannara308@gmail.com</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div class="contact-text">
                            <h3>Phone</h3>
                            <p>+855 96 977 1070</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-globe"></i>
                        </div>
                        <div class="contact-text">
                            <h3>Website</h3>
                            <p>Available</p>
                        </div>
                    </div>
                </div>
                
                <div class="contact-form">
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">Full Name</label>
                            <input type="text" id="name" class="form-control" placeholder="Your Name" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="email">Email Address</label>
                            <input type="email" id="email" class="form-control" placeholder="Your Email" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" class="form-control" placeholder="Subject">
                        </div>
                        
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" class="form-control" placeholder="Your Message" required></textarea>
                        </div>
                        
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">Vuth<span>Dev</span></div>
                <div class="footer-social">
                 <a href="https://t.me/ahhpl0yy_bot" target="_blank"><i class="fab fa-telegram"></i></a>
                 <a href="https://github.com/vuthsovannara" target="_blank"><i class="fab fa-github"></i></a>
                 <a href="https://www.tiktok.com/@ahhpl0yy?_t=ZS-8wv0FvhUoWe&_r=1" target="_blank"><i class="fab fa-tiktok"></i></a>
                 <a href="https://www.facebook.com/share/1UTC8SNFYB/?mibextid=wwXIfr" target="_blank"><i class="fab fa-facebook-f"></i></a>
                 <a href="https://www.instagram.com/ahh_pl0yy?igsh=MW5lOW5haXRmbGh4dw%3D%3D&utm_source=qr" target="_blank"><i class="fab fa-instagram"></i></a>
                </div>
                <p class="copyright">© 2023 Vuth Sovannara. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Mobile menu toggle
        const mobileMenu = document.querySelector('.mobile-menu');
        const navLinks = document.querySelector('.nav-links');

        mobileMenu.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetElement.offsetTop - 80,
                    behavior: 'smooth'
                });
            });
        });

        // Portfolio filtering
        const filterBtns = document.querySelectorAll('.filter-btn');
        const portfolioItems = document.querySelectorAll('.portfolio-item');

        filterBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                // Remove active class from all buttons
                filterBtns.forEach(b => b.classList.remove('active'));
                
                // Add active class to clicked button
                btn.classList.add('active');
                
                const filter = btn.getAttribute('data-filter');
                
                portfolioItems.forEach(item => {
                    if (filter === 'all' || item.getAttribute('data-category') === filter) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });

        // Animate skill bars when they come into view
        const skillBars = document.querySelectorAll('.skill-progress');
        
        const animateSkillBars = () => {
            skillBars.forEach(bar => {
                const barWidth = bar.parentElement.previousElementSibling.querySelector('span:last-child').textContent;
                bar.style.width = barWidth;
            });
        };

        // Use Intersection Observer to trigger animation
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateSkillBars();
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });

        observer.observe(document.querySelector('.skills'));
         // Form submission
        const contactForm = document.getElementById('contactForm');
        
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const subject = document.getElementById('subject').value;
            const message = document.getElementById('message').value;
            
            // In a real application, you would send this data to a server
            console.log({ name, email, subject, message });
            
            // Show success message
            alert('Thank you for your message! I will get back to you soon.');
            
            // Reset form
            contactForm.reset();
        });

        // Set current year in footer
        document.querySelector('.copyright').innerHTML = `&copy; ${new Date().getFullYear()} Vuth Sovannara. All Rights Reserved.`;
    </script>
</body>
</html>
