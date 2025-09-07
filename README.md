# Projet-
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio Personnel</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Variables CSS */
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
            --text-color: #333;
            --background-color: #f9f9f9;
        }
        
        /* Reset et styles de base */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--background-color);
            padding-top: 70px;
        }
        
        a {
            text-decoration: none;
            color: var(--secondary-color);
            transition: color 0.3s;
        }
        
        a:hover {
            color: var(--accent-color);
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Navigation */
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: white;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 1.5rem;
        }
        
        .nav-links a {
            color: white;
            font-weight: 500;
        }
        
        .burger {
            display: none;
            cursor: pointer;
        }
        
        .burger div {
            width: 25px;
            height: 3px;
            background-color: white;
            margin: 5px;
            transition: all 0.3s ease;
        }
        
        /* Sections générales */
        section {
            padding: 5rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2rem;
            color: var(--primary-color);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--secondary-color);
            margin: 10px auto;
            border-radius: 2px;
        }
        
        /* Hero Section */
        .hero {
            height: 90vh;
            display: flex;
            align-items: center;
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            color: white;
            text-align: center;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 0.8rem 1.8rem;
            border-radius: 5px;
            font-weight: bold;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }
        
        .btn:hover {
            background-color: #c0392b;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid white;
            margin-left: 15px;
        }
        
        .btn-outline:hover {
            background-color: white;
            color: var(--primary-color);
        }
        
        /* Timeline */
        .timeline {
            display: flex;
            justify-content: center;
            margin: 2rem 0 3rem;
            flex-wrap: wrap;
        }
        
        .timeline-item {
            padding: 0.5rem 1.5rem;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            margin: 0 0.5rem 1rem;
            font-size: 0.9rem;
        }
        
        /* About Section */
        .about-content {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 3rem;
        }
        
        .about-text {
            flex: 1;
            min-width: 300px;
        }
        
        .about-text p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }
        
        .about-image {
            flex: 1;
            min-width: 300px;
            text-align: center;
        }
        
        .about-image img {
            max-width: 100%;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .about-image img:hover {
            transform: scale(1.02);
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
            display: flex;
            flex-direction: column;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .project-image {
            height: 200px;
            background-color: #ddd;
            background-size: cover;
            background-position: center;
        }
        
        .project-info {
            padding: 1.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        .project-info h3 {
            margin-bottom: 0.8rem;
            color: var(--primary-color);
        }
        
        .project-info p {
            margin-bottom: 1.2rem;
            flex-grow: 1;
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            margin: 0.5rem 0 1.2rem;
        }
        
        .project-tag {
            background-color: var(--light-color);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-right: 0.5rem;
            margin-bottom: 0.5rem;
            color: var(--dark-color);
        }
        
        /* Skills Section */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 2rem;
        }
        
        .skill-category {
            flex: 1;
            min-width: 250px;
            background-color: white;
            padding: 1.8rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .skill-category h3 {
            margin-bottom: 1.5rem;
            color: var(--primary-color);
            text-align: center;
            font-size: 1.4rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid var(--light-color);
        }
        
        .skill-item {
            margin-bottom: 1.5rem;
        }
        
        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .skill-bar {
            height: 10px;
            background-color: var(--light-color);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, var(--secondary-color), var(--primary-color));
            border-radius: 5px;
            width: 0;
            transition: width 1s ease-in-out;
        }
        
        /* Contact Section */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background-color: white;
            padding: 2.5rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: var(--primary-color);
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
            font-size: 1rem;
            transition: border-color 0.3s;
        }
        
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--secondary-color);
            box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
        }
        
        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background-color: var(--primary-color);
            color: white;
            text-align: center;
            padding: 2.5rem 0;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .social-links {
            display: flex;
            margin: 1.5rem 0;
        }
        
        .social-links a {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.1);
            color: white;
            margin: 0 0.5rem;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background-color: var(--secondary-color);
            transform: translateY(-3px);
        }
        
        /* Responsive Design */
        @media screen and (max-width: 768px) {
            body {
                padding-top: 60px;
            }
            
            .nav-links {
                position: fixed;
                right: 0;
                top: 60px;
                background-color: var(--primary-color);
                display: flex;
                flex-direction: column;
                align-items: center;
                width: 100%;
                transform: translateX(100%);
                transition: transform 0.5s ease-in;
                z-index: 999;
                padding: 2rem 0;
                height: calc(100vh - 60px);
                justify-content: center;
            }
            
            .nav-links li {
                opacity: 0;
                margin: 1.5rem 0;
            }
            
            .nav-links a {
                font-size: 1.2rem;
            }
            
            .burger {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .btn-container {
                display: flex;
                flex-direction: column;
                gap: 1rem;
            }
            
            .btn-outline {
                margin-left: 0;
            }
            
            .about-content, .skills-container {
                flex-direction: column;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
        }
        
        .nav-active {
            transform: translateX(0%);
        }
        
        @keyframes navLinkFade {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        .toggle .line1 {
            transform: rotate(-45deg) translate(-5px, 6px);
        }
        
        .toggle .line2 {
            opacity: 0;
        }
        
        .toggle .line3 {
            transform: rotate(45deg) translate(-5px, -6px);
        }
        
        /* Animation des barres de compétences */
        .animate-skills .skill-progress {
            width: var(--skill-level) !important;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">MonPortfolio</div>
                <ul class="nav-links">
                    <li><a href="#accueil">Accueil</a></li>
                    <li><a href="#about">À propos</a></li>
                    <li><a href="#projects">Projets</a></li>
                    <li><a href="#skills">Compétences</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="burger">
                    <div class="line1"></div>
                    <div class="line2"></div>
                    <div class="line3"></div>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="accueil" class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="timeline">
                    <span class="timeline-item">Année 2</span>
                    <span class="timeline-item">Année 3</span>
                    <span class="timeline-item">Après Septembre</span>
                    <span class="timeline-item">Après Octobre</span>
                </div>
                
                <h1>Je suis Prosper, Développeur en devenir passionné par le web et le design !</h1>
                <p>Bienvenue sur mon portfolio où je partage mes projets et compétences en développement web.</p>
                
                <div class="btn-container">
                    <a href="#projects" class="btn">Voir mes projets</a>
                    <a href="#contact" class="btn btn-outline">Me contacter</a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="container">
            <h2 class="section-title">À propos</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Je m'appelle BESSAN Prosper, passionné par la création de sites web modernes et interactifs.</p>
                    <p>Je suis actuellement étudiant en développement web, et je cherche à améliorer mes compétences en JavaScript, HTML et CSS.</p>
                    <p>J'adore transformer mes idées en projets concrets et apprendre les nouvelles technologies.</p>
                    <a href="#" class="btn">Télécharger mon CV</a>
                </div>
                <div class="about-image">
                    <!-- IMG-20250624-WA0026.jpg -->
                    <img src="IMG-20250624-WA0026.jpg" alt="Photo de profil">
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <div class="container">
            <h2 class="section-title">Mes Projets</h2>
            <div class="projects-grid">
                <!-- Projet 1 -->
                <div class="project-card">
                    <div class="project-image" style="background: #3498db url('https://images.unsplash.com/photo-1581276879432-15e50529f34b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80') no-repeat center center; background-size: cover;"></div>
                    <div class="project-info">
                        <h3>Mini-jeu interactif</h3>
                        <p>Un mini-jeu interactif en JavaScript qui utilise des événements DOM pour une expérience utilisateur engageante.</p>
                        <div class="project-tags">
                            <span class="project-tag">#html</span>
                            <span class="project-tag">#css</span>
                            <span class="project-tag">#js</span>
                        </div>
                        <a href="#" class="btn">Voir le projet</a>
                    </div>
                </div>
                
                <!-- Projet 2 -->
                <div class="project-card">
                    <div class="project-image" style="background: #2ecc71 url('https://images.unsplash.com/photo-1551650975-87deedd944c3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80') no-repeat center center; background-size: cover;"></div>
                    <div class="project-info">
                        <h3>Application web responsive</h3>
                        <p>Une application web responsive avec des fonctionnalités avancées et une interface utilisateur intuitive.</p>
                        <div class="project-tags">
                            <span class="project-tag">#html</span>
                            <span class="project-tag">#css</span>
                            <span class="project-tag">#js</span>
                        </div>
                        <a href="#" class="btn">Voir le projet</a>
                    </div>
                </div>
                
                <!-- Projet 3 -->
                <div class="project-card">
                    <div class="project-image" style="background: #e74c3c url('https://images.unsplash.com/photo-1460925895917-afdab827c52f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80') no-repeat center center; background-size: cover;"></div>
                    <div class="project-info">
                        <h3>Portfolio design</h3>
                        <p>Conception et développement d'un portfolio personnel moderne avec des animations fluides.</p>
                        <div class="project-tags">
                            <span class="project-tag">#html</span>
                            <span class="project-tag">#css</span>
                            <span class="project-tag">#js</span>
                        </div>
                        <a href="#" class="btn">Voir le projet</a>
                    </div>
                </div>
            </div>
            
            <p style="text-align: center; margin-top: 2rem; font-style: italic;">
                On trouve un projet intéressant en production. Approfondir.
            </p>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="container">
            <h2 class="section-title">Mes Compétences</h2>
            <div class="skills-container">
             <div class="skill-category">
                    <h3>Compétences principales</h3>
                    <div class="skill-item">
           div class="skill-name">
                            <span>HTML</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="--skill-level: 85%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>CSS</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="--skill-level: 80%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>JavaScript</span>
                            <span>70%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="--skill-level: 70%;"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>Outils & Technologies</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>VS Code</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="--skill-level: 90%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Git</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="--skill-level: 75%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Figma</span>
                            <span>65%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="--skill-level: 65%;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <h2 class="section-title">Contactez-moi</h2>
            <div class="contact-form">
                <p style="text-align: center; margin-bottom: 1.5rem;">Vous avez un projet en tête ? N'hésitez pas à me contacter</p>
                <form id="contactForm">
                    <div class="form-group">
                        <label for="name">Nom</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" required></textarea>
                    </div>
                    <button type="submit" class="btn">Envoyer</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="social-links">
                    <a href="#"><i class="fab fa-github"></i></a>
                    <a href="#"><i class="fab fa-linkedin"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-codepen"></i></a>
                </div>
                <p>Designed by <a href="https://www.python.net" style="color: white; text-decoration: underline;">python.net</a></p>
                <p>&copy; 2025 Tous droits réservés</p>
            </div>
        </div>
    </footer>

    <script>
        // Navigation responsive
        const navSlide = () => {
            const burger = document.querySelector('.burger');
            const nav = document.querySelector('.nav-links');
            const navLinks = document.querySelectorAll('.nav-links li');
            
            burger.addEventListener('click', () => {
                // Toggle Nav
                nav.classList.toggle('nav-active');
                
                // Animate Links
                navLinks.forEach((link, index) => {
                    if (link.style.animation) {
                        link.style.animation = '';
                    } else {
                        link.style.animation = `navLinkFade 0.5s ease forwards ${index / 7 + 0.3}s`;
                    }
                });
                
                // Burger Animation
                burger.classList.toggle('toggle');
            });
        }
        
        navSlide();
        
        // Validation du formulaire de contact
        const contactForm = document.getElementById('contactForm');
        
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;
            
            if (name && email && message) {
                alert('Merci pour votre message ! Je vous répondrai dès que possible.');
                contactForm.reset();
            } else {
                alert('Veuillez remplir tous les champs du formulaire.');
            }
        });
        
        // Animation au défilement
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('.nav-links a');
            
            let current = '';
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                
                if (pageYOffset >= (sectionTop - 300)) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === current) {
                    link.classList.add('active');
                }
            });
            
            // Animation des compétences
            const skillsSection = document.getElementById('skills');
            const skillBars = document.querySelectorAll('.skill-progress');
            const skillsSectionTop = skillsSection.offsetTop;
            const skillsSectionHeight = skillsSection.clientHeight;
            
            if (pageYOffset > skillsSectionTop - 400) {
                skillsSection.classList.add('animate-skills');
            }
        });
        
        // Fermer le menu en cliquant sur un lien
        const navLinks = document.querySelectorAll('.nav-links a');
        const nav = document.querySelector('.nav-links');
        const burger = document.querySelector('.burger');
        
        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                nav.classList.remove('nav-active');
                burger.classList.remove('toggle');
                
                // Reset animations
                document.querySelectorAll('.nav-links li').forEach(item => {
                    item.style.animation = '';
                });
            });
        });
    </script>
</body>
</html>
```  
