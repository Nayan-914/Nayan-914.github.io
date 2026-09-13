<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Neon Sensei | Daily Anime Updates</title>
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Orbitron:wght@400;700;900&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    
    <!-- Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        :root {
            --bg-color: #050505;
            --surface-color: #111111;
            --primary-red: #ff003c;
            --text-main: #f0f0f0;
            --text-muted: #a0a0a0;
            --neon-glow: 0 0 5px #ff003c, 0 0 10px #ff003c, 0 0 20px #ff003c, 0 0 40px rgba(255, 0, 60, 0.5);
            --neon-glow-hover: 0 0 10px #ff003c, 0 0 20px #ff003c, 0 0 40px #ff003c, 0 0 80px rgba(255, 0, 60, 0.8);
            --font-display: 'Orbitron', sans-serif;
            --font-heading: 'Rajdhani', sans-serif;
            --font-body: 'Inter', sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            font-family: var(--font-body);
            overflow-x: hidden;
            line-height: 1.6;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: all 0.3s ease;
        }

        ul {
            list-style: none;
        }

        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(5, 5, 5, 0.8);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 0, 60, 0.2);
        }

        .logo {
            font-family: var(--font-display);
            font-size: 1.8rem;
            font-weight: 900;
            color: var(--primary-red);
            text-shadow: var(--neon-glow);
            letter-spacing: 2px;
            cursor: pointer;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            font-family: var(--font-heading);
            font-size: 1.1rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0%;
            height: 2px;
            background-color: var(--primary-red);
            box-shadow: var(--neon-glow);
            transition: width 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--primary-red);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Mobile Menu Toggle */
        .menu-toggle {
            display: none;
            color: var(--primary-red);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 5%;
            position: relative;
            background: linear-gradient(to bottom, rgba(5,5,5,0.3) 0%, rgba(5,5,5,1) 100%), 
                        url('https://images.unsplash.com/photo-1601042879364-f3947d3f9c16?q=80&w=2070&auto=format&fit=crop') center/cover no-repeat;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle, rgba(255,0,60,0.1) 0%, rgba(5,5,5,0.8) 80%);
            pointer-events: none;
        }

        .hero-content {
            z-index: 1;
            max-width: 800px;
        }

        .glitch-title {
            font-family: var(--font-display);
            font-size: 4.5rem;
            font-weight: 900;
            color: #fff;
            text-shadow: 2px 2px var(--primary-red), -2px -2px #0ff;
            margin-bottom: 1rem;
            position: relative;
            animation: glitch 3s infinite;
        }

        @keyframes glitch {
            0% { text-shadow: 2px 2px var(--primary-red), -2px -2px #0ff; transform: translate(0); }
            20% { text-shadow: -2px 2px var(--primary-red), 2px -2px #0ff; transform: translate(-2px, 2px); }
            40% { text-shadow: 2px -2px var(--primary-red), -2px 2px #0ff; transform: translate(2px, -2px); }
            60% { text-shadow: -2px -2px var(--primary-red), 2px 2px #0ff; transform: translate(-2px, -2px); }
            80% { text-shadow: 2px 2px var(--primary-red), -2px -2px #0ff; transform: translate(2px, 2px); }
            100% { text-shadow: 2px 2px var(--primary-red), -2px -2px #0ff; transform: translate(0); }
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 2.5rem;
            height: 30px; /* fixed height to prevent layout shift during typing */
        }

        .btn-neon {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: transparent;
            color: var(--primary-red);
            font-family: var(--font-heading);
            font-size: 1.2rem;
            font-weight: 700;
            text-transform: uppercase;
            border: 2px solid var(--primary-red);
            border-radius: 4px;
            box-shadow: inset 0 0 10px rgba(255,0,60,0.2), 0 0 10px rgba(255,0,60,0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .btn-neon::before {
            content: '';
            position: absolute;
            top: 0; left: -100%;
            width: 100%; height: 100%;
            background: var(--primary-red);
            transition: all 0.4s ease;
            z-index: -1;
        }

        .btn-neon:hover {
            color: #fff;
            box-shadow: var(--neon-glow-hover);
        }

        .btn-neon:hover::before {
            left: 0;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-title {
            font-family: var(--font-display);
            font-size: 2.5rem;
            color: var(--text-main);
            display: inline-block;
            position: relative;
        }

        .section-title span {
            color: var(--primary-red);
            text-shadow: 0 0 10px rgba(255,0,60,0.6);
        }

        section {
            padding: 6rem 5%;
        }

        .updates-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
        }

        .card {
            background-color: var(--surface-color);
            border: 1px solid #222;
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
            position: relative;
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: var(--primary-red);
            box-shadow: 0 10px 30px rgba(255, 0, 60, 0.15), 0 0 15px rgba(255, 0, 60, 0.2);
        }

        .card-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-bottom: 1px solid #222;
            transition: filter 0.3s ease;
            filter: grayscale(80%) contrast(120%);
        }

        .card:hover .card-img {
            filter: grayscale(0%) contrast(110%);
        }

        .card-content {
            padding: 1.5rem;
        }

        .card-tag {
            font-size: 0.8rem;
            color: var(--primary-red);
            text-transform: uppercase;
            font-weight: 700;
            letter-spacing: 1px;
            margin-bottom: 0.5rem;
            display: block;
        }

        .card-title {
            font-family: var(--font-heading);
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .card-text {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 1.5rem;
        }

        .card-link {
            font-family: var(--font-heading);
            color: var(--primary-red);
            font-weight: 700;
            text-transform: uppercase;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .card-link i {
            transition: transform 0.3s ease;
        }

        .card-link:hover i {
            transform: translateX(5px);
        }

        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
        }

        .gallery-item {
            position: relative;
            border-radius: 8px;
            overflow: hidden;
            aspect-ratio: 1 / 1;
            cursor: pointer;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease, filter 0.5s ease;
            filter: brightness(0.7) sepia(0.3) hue-rotate(300deg);
        }

        .gallery-item:hover img {
            transform: scale(1.1);
            filter: brightness(1) sepia(0) hue-rotate(0deg);
        }

        .gallery-overlay {
            position: absolute;
            bottom: -100%;
            left: 0;
            width: 100%;
            padding: 1.5rem;
            background: linear-gradient(to top, rgba(0,0,0,0.9), transparent);
            transition: bottom 0.3s ease;
        }

        .gallery-item:hover .gallery-overlay {
            bottom: 0;
        }

        .gallery-overlay h3 {
            font-family: var(--font-heading);
            color: var(--primary-red);
            font-size: 1.2rem;
            margin-bottom: 0.2rem;
        }

        .gallery-overlay p {
            font-size: 0.85rem;
            color: #ddd;
        }

        footer {
            background-color: #000;
            padding: 4rem 5% 2rem;
            text-align: center;
            border-top: 1px solid rgba(255,0,60,0.3);
        }

        .footer-logo {
            font-family: var(--font-display);
            font-size: 2rem;
            color: var(--primary-red);
            text-shadow: var(--neon-glow);
            margin-bottom: 1rem;
        }

        .footer-quote {
            font-style: italic;
            color: var(--text-muted);
            margin-bottom: 2rem;
            font-family: var(--font-heading);
            font-size: 1.2rem;
        }

        .social-icons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--surface-color);
            color: var(--text-main);
            font-size: 1.2rem;
            border: 1px solid #333;
            transition: all 0.3s ease;
        }

        .social-icons a:hover {
            border-color: var(--primary-red);
            color: var(--primary-red);
            box-shadow: 0 0 15px rgba(255,0,60,0.5);
            transform: translateY(-3px);
        }

        .copyright {
            color: #555;
            font-size: 0.9rem;
        }

        /* Scroll Animations */
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease-out;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Media Queries for Responsiveness */
        @media (max-width: 768px) {
            .glitch-title { font-size: 3rem; }
            .nav-links {
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                flex-direction: column;
                background: rgba(5,5,5,0.95);
                padding: 2rem 0;
                align-items: center;
                border-bottom: 1px solid rgba(255,0,60,0.2);
                clip-path: polygon(0 0, 100% 0, 100% 0, 0 0);
                transition: clip-path 0.4s ease-in-out;
            }
            .nav-links.active {
                clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
            }
            .menu-toggle { display: block; }
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <div class="logo">NEON SENSEI</div>
        <div class="menu-toggle" id="mobile-menu"><i class="fas fa-bars"></i></div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#updates">Daily Updates</a></li>
            <li><a href="#artworks">Artworks</a></li>
            <li><a href="#connect">Connect</a></li>
        </ul>
    </nav>

    <header class="hero" id="home">
        <div class="hero-content">
            <h1 class="glitch-title">WELCOME TO NEON SENSEI</h1>
            <p class="hero-subtitle" id="typewriter"></p>
            <a href="#updates" class="btn-neon">Enter the Grid</a>
        </div>
    </header>

    <section id="updates">
        <div class="section-header reveal">
            <h2 class="section-title">DAILY <span>UPDATES</span></h2>
        </div>
        
        <div class="updates-grid">
            <!-- Card 1 -->
            <article class="card reveal">
                <img src="https://images.unsplash.com/photo-1578632767115-351597cf2477?q=80&w=1000&auto=format&fit=crop" alt="Anime Episode" class="card-img">
                <div class="card-content">
                    <span class="card-tag">Episode Review</span>
                    <h3 class="card-title">Jujutsu Kaisen: The Shibuya Incident Escalates</h3>
                    <p class="card-text">A deep dive into the animation quality, pacing, and emotional impact of the latest jaw-dropping episode.</p>
                    <a href="#" class="card-link">Read Log <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>

            <!-- Card 2 -->
            <article class="card reveal" style="transition-delay: 0.1s;">
                <img src="https://images.unsplash.com/photo-1618336753974-aae8e04506aa?q=80&w=1000&auto=format&fit=crop" alt="Manga Drops" class="card-img">
                <div class="card-content">
                    <span class="card-tag">Manga Drops</span>
                    <h3 class="card-title">Cyberpunk Chronicles: Issue #42 is Live</h3>
                    <p class="card-text">The neon-soaked streets get darker in the latest chapter. We analyze the newest lore drops and character arcs.</p>
                    <a href="#" class="card-link">Read Log <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>

            <!-- Card 3 -->
            <article class="card reveal" style="transition-delay: 0.2s;">
                <img src="https://images.unsplash.com/photo-1542831371-29b0f74f9713?q=80&w=1000&auto=format&fit=crop" alt="Aesthetic Wallpapers" class="card-img">
                <div class="card-content">
                    <span class="card-tag">Aesthetic Cache</span>
                    <h3 class="card-title">Neon Aesthetic Wallpapers Pack Vol. 5</h3>
                    <p class="card-text">Upgrade your interface. Download high-resolution, hand-picked anime and cyberpunk wallpapers for your devices.</p>
                    <a href="#" class="card-link">Access Files <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>
        </div>
    </section>

    <section id="artworks">
        <div class="section-header reveal">
            <h2 class="section-title">INSPIRATION <span>BOARD</span></h2>
        </div>

        <div class="gallery-container">
            <div class="gallery-item reveal">
                <img src="https://images.unsplash.com/photo-1510804445831-236b28dd46b2?q=80&w=800&auto=format&fit=crop" alt="Art 1">
                <div class="gallery-overlay">
                    <h3>Tokyo Nights</h3>
                    <p>Neon Reflections</p>
                </div>
            </div>
            <div class="gallery-item reveal" style="transition-delay: 0.1s;">
                <img src="https://images.unsplash.com/photo-1522204647313-2d2c1ecbc2b1?q=80&w=800&auto=format&fit=crop" alt="Art 2">
                <div class="gallery-overlay">
                    <h3>Grid Runner</h3>
                    <p>Cyber Cityscapes</p>
                </div>
            </div>
            <div class="gallery-item reveal" style="transition-delay: 0.2s;">
                <img src="https://images.unsplash.com/photo-1555680202-c86f0e12f086?q=80&w=800&auto=format&fit=crop" alt="Art 3">
                <div class="gallery-overlay">
                    <h3>Mecha Dreams</h3>
                    <p>Industrial Design</p>
                </div>
            </div>
            <div class="gallery-item reveal" style="transition-delay: 0.3s;">
                <img src="https://images.unsplash.com/photo-1605806616949-1e87b487cb2a?q=80&w=800&auto=format&fit=crop" alt="Art 4">
                <div class="gallery-overlay">
                    <h3>Digital Ronin</h3>
                    <p>Character Concepts</p>
                </div>
            </div>
        </div>
    </section>

    <footer id="connect">
        <div class="footer-logo">NEON SENSEI</div>
        <p class="footer-quote">"In the neon glow, we find our truth."</p>
        
        <div class="social-icons">
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-discord"></i></a>
            <a href="#"><i class="fab fa-github"></i></a>
        </div>
        
        <p class="copyright">&copy; 2026 Neon Sensei. System Online.</p>
    </footer>

    <script>
        // Mobile Menu Toggle
        const menuToggle = document.getElementById('mobile-menu');
        const navLinks = document.querySelector('.nav-links');

        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            const icon = menuToggle.querySelector('i');
            if (navLinks.classList.contains('active')) {
                icon.classList.remove('fa-bars');
                icon.classList.add('fa-times');
            } else {
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            }
        });

        // Typewriter Effect for Hero Subtitle
        const texts = ["Your daily hub for anime updates.", "Curated aesthetic art drops.", "Immerse yourself in neon vibes."];
        let count = 0;
        let index = 0;
        let currentText = '';
        let letter = '';
        let isDeleting = false;
        
        (function type() {
            if (count === texts.length) {
                count = 0;
            }
            currentText = texts[count];

            if (isDeleting) {
                letter = currentText.slice(0, --index);
            } else {
                letter = currentText.slice(0, ++index);
            }

            document.getElementById('typewriter').textContent = letter + '|';

            let typeSpeed = 100;

            if (isDeleting) {
                typeSpeed /= 2; // Delete faster
            }

            if (!isDeleting && letter.length === currentText.length) {
                typeSpeed = 2000; // Pause at end of sentence
                isDeleting = true;
            } else if (isDeleting && letter.length === 0) {
                isDeleting = false;
                count++;
                typeSpeed = 500; // Pause before typing next sentence
            }

            setTimeout(type, typeSpeed);
        }());

        // Scroll Reveal Animation via IntersectionObserver
        const reveals = document.querySelectorAll('.reveal');

        const revealOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -50px 0px"
        };

        const revealOnScroll = new IntersectionObserver(function(entries, observer) {
            entries.forEach(entry => {
                if (!entry.isIntersecting) {
                    return;
                } else {
                    entry.target.classList.add('active');
                    observer.unobserve(entry.target);
                }
            });
        }, revealOptions);

        reveals.forEach(reveal => {
            revealOnScroll.observe(reveal);
        });
    </script>
</body>
</html>
