<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Neon Sensei | Daily Anime &amp; Neon-Tokyo Aesthetic Updates</title>
    <meta name="description" content="Neon Sensei — daily anime episode reviews, manga drops, character spotlights, and neon-Tokyo aesthetic wallpapers, wrapped in one cyberpunk-styled hub.">

    <!-- Fonts: Orbitron for the English display wordmark, Noto Sans JP for correct Japanese rendering,
         Dela Gothic One for bold Japanese display moments, Rajdhani for UI labels, Inter for body copy -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Dela+Gothic+One&family=Inter:wght@300;400;500;600&family=Noto+Sans+JP:wght@300;400;500;700;900&family=Orbitron:wght@400;700;900&family=Rajdhani:wght@500;600;700&display=swap" rel="stylesheet">

    <!-- Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- Favicon: inline SVG mark, no external file needed -->
    <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect width='100' height='100' fill='%23050505'/%3E%3Ctext x='50' y='70' font-size='58' font-family='Arial, sans-serif' font-weight='900' fill='%23ff003c' text-anchor='middle'%3EN%3C/text%3E%3C/svg%3E">

    <style>
        /* ============================= ROOT TOKENS ============================= */
        :root {
            --bg-color: #050505;
            --bg-alt: #0a0a0d;
            --surface-color: #111113;
            --surface-hover: #17171a;
            --border-color: #222225;

            --primary-red: #ff003c;
            --primary-red-dim: #b3002a;
            --accent-cyan: #00e5ff;

            --text-main: #f0f0f0;
            --text-muted: #a0a0a6;
            --text-dim: #5c5c62;

            --neon-glow: 0 0 6px rgba(255,0,60,0.8), 0 0 16px rgba(255,0,60,0.6), 0 0 40px rgba(255,0,60,0.35);
            --neon-glow-hover: 0 0 10px rgba(255,0,60,0.9), 0 0 24px rgba(255,0,60,0.8), 0 0 60px rgba(255,0,60,0.5);
            --neon-glow-cyan: 0 0 6px rgba(0,229,255,0.7), 0 0 18px rgba(0,229,255,0.4);

            --ease-out: cubic-bezier(0.16, 1, 0.3, 1);

            --font-display: 'Orbitron', sans-serif;
            --font-jp-display: 'Dela Gothic One', 'Noto Sans JP', sans-serif;
            --font-heading: 'Rajdhani', sans-serif;
            --font-body: 'Inter', 'Noto Sans JP', sans-serif;
            --font-jp: 'Noto Sans JP', sans-serif;
        }

        /* ============================= RESET / BASE ============================= */
        * { margin: 0; padding: 0; box-sizing: border-box; }

        html { scroll-behavior: smooth; }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            font-family: var(--font-body);
            overflow-x: hidden;
            line-height: 1.6;
        }

        a { text-decoration: none; color: inherit; transition: color 0.25s ease; }
        ul { list-style: none; }
        img { display: block; max-width: 100%; }
        button, input { font-family: inherit; }

        a:focus-visible, button:focus-visible, input:focus-visible {
            outline: 2px solid var(--accent-cyan);
            outline-offset: 3px;
        }

        section { padding: 6rem 5%; position: relative; }

        /* Shared section heading pattern: English title stays neutral white;
           the Japanese line carries the red neon accent instead of splitting the English words. */
        .section-header { text-align: center; margin-bottom: 3.5rem; }
        .section-title {
            font-family: var(--font-display);
            font-size: clamp(1.9rem, 4vw, 2.5rem);
            color: var(--text-main);
            letter-spacing: 1px;
        }
        .section-jp {
            display: block;
            margin-top: 0.6rem;
            font-family: var(--font-jp);
            font-size: 1.1rem;
            color: var(--primary-red);
            text-shadow: 0 0 12px rgba(255,0,60,0.5);
            letter-spacing: 0.15em;
        }

        /* ============================= VERTICAL JP RAIL (signature element) ============================= */
        .jp-rail {
            position: fixed;
            left: 0;
            top: 0;
            height: 100vh;
            width: 34px;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 400;
            pointer-events: none;
        }
        .jp-rail span {
            writing-mode: vertical-rl;
            text-orientation: upright;
            font-family: var(--font-jp);
            font-weight: 500;
            font-size: 0.8rem;
            letter-spacing: 0.7em;
            color: var(--primary-red);
            opacity: 0.4;
            white-space: nowrap;
            text-shadow: 0 0 10px rgba(255,0,60,0.4);
        }
        @media (max-width: 1000px) { .jp-rail { display: none; } }

        /* ============================= NAVBAR ============================= */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.35rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(5, 5, 5, 0.85);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 0, 60, 0.2);
        }

        .logo {
            font-family: var(--font-display);
            font-size: 1.6rem;
            font-weight: 900;
            color: #fff;
            letter-spacing: 2px;
            cursor: pointer;
        }
        .logo span { color: var(--primary-red); text-shadow: var(--neon-glow); }

        .nav-links { display: flex; gap: 2.25rem; }

        .nav-links a { display: flex; flex-direction: column; align-items: center; gap: 3px; position: relative; padding-bottom: 4px; }

        .nav-en {
            font-family: var(--font-heading);
            font-size: 1.02rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .nav-jp { font-family: var(--font-jp); font-size: 0.65rem; color: var(--primary-red); letter-spacing: 0.05em; }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -6px;
            left: 50%;
            width: 0%;
            height: 2px;
            background-color: var(--primary-red);
            box-shadow: var(--neon-glow);
            transition: width 0.3s ease, left 0.3s ease;
        }
        .nav-links a:hover::after, .nav-links a.active::after { width: 100%; left: 0; }
        .nav-links a:hover .nav-en, .nav-links a.active .nav-en { color: var(--primary-red); }

        .menu-toggle { display: none; color: var(--primary-red); font-size: 1.5rem; cursor: pointer; }

        /* ============================= HERO ============================= */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 7rem 5% 4rem;
            position: relative;
            background:
                linear-gradient(to bottom, rgba(5,5,5,0.35) 0%, rgba(5,5,5,0.75) 60%, rgba(5,5,5,1) 100%),
                url('https://images.unsplash.com/photo-1764418658791-771bb04efdcd?q=80&w=2000&auto=format&fit=crop') center/cover no-repeat;
        }
        .hero::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 30%, rgba(255,0,60,0.12) 0%, rgba(5,5,5,0.85) 75%);
            pointer-events: none;
        }

        .hanko {
            position: relative;
            z-index: 1;
            color: var(--primary-red);
            margin-bottom: 1.75rem;
            transform: rotate(-6deg);
            filter: drop-shadow(0 0 8px rgba(255,0,60,0.5));
        }
        .hanko svg { width: 72px; height: 72px; }
        .hanko rect { fill: none; stroke: currentColor; stroke-width: 5; }
        .hanko-kanji { font-family: var(--font-jp-display); font-size: 30px; fill: currentColor; text-anchor: middle; }
        .hanko-en { font-family: var(--font-display); font-size: 13px; fill: currentColor; text-anchor: middle; letter-spacing: 1px; }

        .hero-content { z-index: 1; max-width: 800px; }

        .glitch-title {
            font-family: var(--font-display);
            font-size: clamp(2.6rem, 8vw, 4.75rem);
            font-weight: 900;
            color: #fff;
            text-shadow: 2px 2px var(--primary-red), -2px -2px var(--accent-cyan);
            margin-bottom: 0.9rem;
            letter-spacing: 2px;
            animation: glitch 4s infinite;
        }
        @keyframes glitch {
            0%, 100% { text-shadow: 2px 2px var(--primary-red), -2px -2px var(--accent-cyan); transform: translate(0); }
            20% { text-shadow: -2px 2px var(--primary-red), 2px -2px var(--accent-cyan); transform: translate(-2px, 2px); }
            40% { text-shadow: 2px -2px var(--primary-red), -2px 2px var(--accent-cyan); transform: translate(2px, -2px); }
            60% { text-shadow: -2px -2px var(--primary-red), 2px 2px var(--accent-cyan); transform: translate(-2px, -2px); }
            80% { text-shadow: 2px 2px var(--primary-red), -2px -2px var(--accent-cyan); transform: translate(2px, 2px); }
        }

        .hero-jp {
            font-family: var(--font-jp);
            font-size: 1.05rem;
            color: var(--primary-red);
            text-shadow: 0 0 12px rgba(255,0,60,0.5);
            letter-spacing: 0.1em;
            margin-bottom: 1.4rem;
        }

        .hero-subtitle { font-size: 1.15rem; color: var(--text-muted); margin-bottom: 2.5rem; min-height: 30px; }

        .btn-neon {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: transparent;
            color: var(--primary-red);
            font-family: var(--font-heading);
            font-size: 1.15rem;
            font-weight: 700;
            text-transform: uppercase;
            border: 2px solid var(--primary-red);
            border-radius: 4px;
            box-shadow: inset 0 0 10px rgba(255,0,60,0.15), 0 0 10px rgba(255,0,60,0.15);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }
        .btn-neon::before {
            content: ''; position: absolute; top: 0; left: -100%; width: 100%; height: 100%;
            background: var(--primary-red); transition: left 0.4s ease; z-index: -1;
        }
        .btn-neon:hover { color: #fff; box-shadow: var(--neon-glow-hover); }
        .btn-neon:hover::before { left: 0; }

        .scroll-cue {
            position: absolute;
            bottom: 2.2rem; left: 50%;
            transform: translateX(-50%);
            width: 24px; height: 38px;
            border: 2px solid var(--text-muted);
            border-radius: 14px;
        }
        .scroll-cue span {
            position: absolute; top: 6px; left: 50%; transform: translateX(-50%);
            width: 4px; height: 8px; border-radius: 2px;
            background: var(--primary-red);
            box-shadow: var(--neon-glow);
            animation: scrollcue 1.8s infinite;
        }
        @keyframes scrollcue { 0% { opacity: 1; top: 6px; } 70% { opacity: 0; top: 18px; } 100% { opacity: 0; top: 6px; } }

        /* ============================= TICKER ============================= */
        .ticker-wrap {
            overflow: hidden;
            white-space: nowrap;
            background: var(--surface-color);
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
            padding: 0.85rem 0;
        }
        .ticker { display: inline-flex; animation: ticker-scroll 32s linear infinite; }
        .ticker-track { display: inline-flex; align-items: center; }
        .ticker-track span { padding: 0 1.25rem; font-family: var(--font-heading); font-size: 0.95rem; letter-spacing: 0.5px; color: var(--text-muted); }
        .ticker-track span[lang="ja"] { font-family: var(--font-jp); color: var(--text-main); }
        .ticker-track .dot { color: var(--primary-red); padding: 0; }
        @keyframes ticker-scroll { from { transform: translateX(0); } to { transform: translateX(-50%); } }

        /* ============================= CARDS / DAILY UPDATES ============================= */
        .updates-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
        }

        .card {
            background-color: var(--surface-color);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.35s var(--ease-out), box-shadow 0.35s var(--ease-out), border-color 0.35s var(--ease-out);
        }
        .card:hover {
            transform: translateY(-8px);
            border-color: var(--primary-red);
            box-shadow: 0 14px 34px rgba(0,0,0,0.4), 0 0 18px rgba(255, 0, 60, 0.18);
        }

        .card-img-wrap { aspect-ratio: 4 / 3; overflow: hidden; background: var(--bg-alt); }
        .card-img {
            width: 100%; height: 100%; object-fit: cover;
            filter: saturate(0.92) contrast(1.05);
            transition: filter 0.4s ease, transform 0.6s var(--ease-out);
        }
        .card:hover .card-img { filter: saturate(1.15) contrast(1.08); transform: scale(1.04); }

        .card-content { padding: 1.5rem; }

        .card-tag { display: flex; align-items: baseline; gap: 0.55rem; margin-bottom: 0.75rem; flex-wrap: wrap; }
        .tag-jp { font-family: var(--font-jp); font-weight: 700; font-size: 0.95rem; color: var(--primary-red); text-shadow: 0 0 8px rgba(255,0,60,0.45); }
        .tag-en { font-family: var(--font-heading); font-size: 0.72rem; text-transform: uppercase; letter-spacing: 1px; color: var(--text-muted); }

        .card-title { font-family: var(--font-heading); font-size: 1.4rem; font-weight: 700; margin-bottom: 0.85rem; }
        .card-text { color: var(--text-muted); font-size: 0.95rem; margin-bottom: 1.5rem; }

        .card-link { font-family: var(--font-heading); color: var(--primary-red); font-weight: 700; text-transform: uppercase; display: inline-flex; align-items: center; gap: 0.5rem; font-size: 0.95rem; }
        .card-link i { transition: transform 0.3s ease; }
        .card-link:hover i { transform: translateX(5px); }

        /* ============================= STATS ============================= */
        .stats-section { background: var(--bg-alt); }
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
            gap: 2rem;
            max-width: 1000px;
            margin: 0 auto;
        }
        .stat-block { text-align: center; padding: 1.5rem 1rem; border: 1px solid var(--border-color); border-radius: 8px; background: var(--surface-color); }
        .stat-num { display: block; font-family: var(--font-display); font-size: 2.4rem; font-weight: 900; color: var(--primary-red); text-shadow: var(--neon-glow); }
        .stat-label { display: block; font-family: var(--font-heading); font-size: 0.95rem; color: var(--text-main); margin-top: 0.5rem; }
        .stat-jp { display: block; font-family: var(--font-jp); font-size: 0.75rem; color: var(--text-dim); margin-top: 0.3rem; letter-spacing: 0.05em; }

        /* ============================= FEATURED SPOTLIGHT ============================= */
        .featured-card {
            display: grid;
            grid-template-columns: 1.1fr 1fr;
            gap: 0;
            max-width: 1100px;
            margin: 0 auto;
            background: var(--surface-color);
            border: 1px solid var(--border-color);
            border-radius: 10px;
            overflow: hidden;
        }
        .featured-img-wrap { aspect-ratio: 4 / 3; overflow: hidden; background: var(--bg-alt); }
        .featured-img-wrap img { width: 100%; height: 100%; object-fit: cover; }
        .featured-content { padding: 2.5rem; display: flex; flex-direction: column; justify-content: center; }
        .featured-content .card-title { font-size: 1.75rem; }
        .featured-content .card-text { font-size: 1rem; margin-bottom: 1rem; }
        .featured-content .card-link { margin-top: 0.5rem; }

        @media (max-width: 800px) {
            .featured-card { grid-template-columns: 1fr; }
            .featured-img-wrap { aspect-ratio: 16 / 9; }
        }

        /* ============================= GALLERY ============================= */
        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 1.25rem;
        }
        .gallery-item { position: relative; border-radius: 8px; overflow: hidden; aspect-ratio: 1 / 1; cursor: pointer; background: var(--bg-alt); }
        .gallery-item img {
            width: 100%; height: 100%; object-fit: cover;
            filter: brightness(0.82) saturate(1.05);
            transition: transform 0.6s var(--ease-out), filter 0.5s ease;
        }
        .gallery-item:hover img { transform: scale(1.08); filter: brightness(1) saturate(1.2); }

        .gallery-overlay {
            position: absolute; bottom: 0; left: 0; width: 100%;
            padding: 1.4rem;
            background: linear-gradient(to top, rgba(0,0,0,0.92), transparent);
            transform: translateY(15%);
            opacity: 0;
            transition: opacity 0.3s ease, transform 0.3s ease;
        }
        .gallery-item:hover .gallery-overlay { opacity: 1; transform: translateY(0); }
        .gallery-overlay h3 { font-family: var(--font-heading); color: var(--primary-red); font-size: 1.15rem; margin-bottom: 0.15rem; }
        .gallery-overlay p { font-size: 0.82rem; color: #ddd; }

        /* ============================= NEWSLETTER / CONNECT ============================= */
        .newsletter-section { background: var(--bg-alt); text-align: center; }
        .newsletter-inner { max-width: 560px; margin: 0 auto; }
        .newsletter-inner p { color: var(--text-muted); margin: 1.25rem 0 2rem; }
        .newsletter-form { display: flex; gap: 0.75rem; flex-wrap: wrap; justify-content: center; }
        .newsletter-form input {
            flex: 1 1 260px;
            padding: 0.9rem 1.1rem;
            background: var(--surface-color);
            border: 1px solid var(--border-color);
            border-radius: 4px;
            color: var(--text-main);
            font-size: 1rem;
        }
        .newsletter-form input::placeholder { color: var(--text-dim); }
        .newsletter-form button {
            padding: 0.9rem 1.75rem;
            background: var(--primary-red);
            color: #fff;
            border: none;
            border-radius: 4px;
            font-family: var(--font-heading);
            font-weight: 700;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            display: inline-flex; align-items: center; gap: 0.5rem;
            transition: box-shadow 0.3s ease, transform 0.2s ease;
        }
        .newsletter-form button:hover { box-shadow: var(--neon-glow-hover); }
        .newsletter-form button:disabled { opacity: 0.75; cursor: default; }

        /* ============================= FOOTER ============================= */
        footer { background-color: #000; padding: 4.5rem 5% 2rem; border-top: 1px solid rgba(255,0,60,0.3); }

        .footer-grid {
            display: grid;
            grid-template-columns: 1.4fr 1fr 1fr 1fr;
            gap: 2.5rem;
            max-width: 1100px;
            margin: 0 auto 3rem;
        }
        .footer-logo { font-family: var(--font-display); font-size: 1.6rem; color: #fff; margin-bottom: 1rem; }
        .footer-logo span { color: var(--primary-red); text-shadow: var(--neon-glow); }
        .footer-quote { font-family: var(--font-heading); font-style: italic; color: var(--text-muted); font-size: 1.05rem; margin-bottom: 1.5rem; line-height: 1.7; }
        .footer-quote-jp { display: block; font-family: var(--font-jp); font-style: normal; color: var(--primary-red); font-size: 0.85rem; margin-top: 0.35rem; letter-spacing: 0.05em; }

        .social-icons { display: flex; gap: 1rem; }
        .social-icons a {
            display: flex; align-items: center; justify-content: center;
            width: 42px; height: 42px; border-radius: 50%;
            background: var(--surface-color); color: var(--text-main);
            font-size: 1.1rem; border: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }
        .social-icons a:hover { border-color: var(--primary-red); color: var(--primary-red); box-shadow: var(--neon-glow); transform: translateY(-3px); }

        .footer-col h4 { font-family: var(--font-heading); font-size: 1.05rem; margin-bottom: 1.1rem; display: flex; flex-direction: column; gap: 2px; }
        .footer-col h4 span { font-family: var(--font-jp); font-size: 0.68rem; color: var(--primary-red); font-weight: 400; }
        .footer-col ul li { margin-bottom: 0.65rem; }
        .footer-col ul li a { color: var(--text-muted); font-size: 0.92rem; }
        .footer-col ul li a:hover { color: var(--primary-red); }

        .status-line { display: flex; align-items: center; gap: 0.5rem; color: var(--text-muted); font-size: 0.92rem; margin-bottom: 0.4rem; }
        .status-dot { width: 8px; height: 8px; border-radius: 50%; background: #2ee66b; box-shadow: 0 0 8px #2ee66b; flex-shrink: 0; }
        .status-line-jp { font-family: var(--font-jp); font-size: 0.75rem; color: var(--text-dim); }

        .footer-bottom { text-align: center; padding-top: 2rem; border-top: 1px solid var(--border-color); max-width: 1100px; margin: 0 auto; }
        .copyright { color: var(--text-dim); font-size: 0.88rem; }

        @media (max-width: 900px) {
            .footer-grid { grid-template-columns: 1fr 1fr; }
        }
        @media (max-width: 520px) {
            .footer-grid { grid-template-columns: 1fr; }
        }

        /* ============================= BACK TO TOP ============================= */
        .back-to-top {
            position: fixed; right: 1.75rem; bottom: 1.75rem;
            width: 46px; height: 46px; border-radius: 50%;
            background: var(--surface-color); color: var(--primary-red);
            border: 1px solid var(--primary-red);
            display: flex; align-items: center; justify-content: center;
            font-size: 1.05rem; cursor: pointer;
            opacity: 0; visibility: hidden; transform: translateY(10px);
            transition: all 0.3s ease;
            z-index: 900;
        }
        .back-to-top.visible { opacity: 1; visibility: visible; transform: translateY(0); }
        .back-to-top:hover { box-shadow: var(--neon-glow); }

        /* ============================= BOOT SCREEN ============================= */
        .boot-screen {
            position: fixed; inset: 0; z-index: 9999;
            background: var(--bg-color);
            display: flex; align-items: center; justify-content: center;
            animation: bootFadeOut 0.6s ease forwards;
            animation-delay: 1.7s;
            cursor: pointer;
        }
        .boot-inner { text-align: center; }
        .boot-mark { font-family: var(--font-jp-display); font-size: 1.4rem; color: var(--primary-red); text-shadow: var(--neon-glow); margin-bottom: 1.2rem; letter-spacing: 0.1em; }
        .boot-bar { width: 220px; height: 3px; background: var(--surface-color); border-radius: 2px; overflow: hidden; margin: 0 auto 1rem; }
        .boot-bar span { display: block; height: 100%; width: 0%; background: var(--primary-red); box-shadow: var(--neon-glow); animation: bootFill 1.5s var(--ease-out) forwards; }
        .boot-line { font-family: var(--font-heading); font-size: 0.85rem; color: var(--text-muted); letter-spacing: 1px; }
        @keyframes bootFill { to { width: 100%; } }
        @keyframes bootFadeOut { to { opacity: 0; visibility: hidden; pointer-events: none; } }

        /* ============================= SCROLL REVEAL ============================= */
        .reveal { opacity: 0; transform: translateY(40px); transition: opacity 0.7s var(--ease-out), transform 0.7s var(--ease-out); }
        .reveal.active { opacity: 1; transform: translateY(0); }
        .updates-grid .card:nth-child(1) { transition-delay: 0s; }
        .updates-grid .card:nth-child(2) { transition-delay: 0.08s; }
        .updates-grid .card:nth-child(3) { transition-delay: 0.16s; }
        .updates-grid .card:nth-child(4) { transition-delay: 0.24s; }
        .updates-grid .card:nth-child(5) { transition-delay: 0.32s; }
        .updates-grid .card:nth-child(6) { transition-delay: 0.4s; }
        .gallery-container .gallery-item:nth-child(1) { transition-delay: 0s; }
        .gallery-container .gallery-item:nth-child(2) { transition-delay: 0.08s; }
        .gallery-container .gallery-item:nth-child(3) { transition-delay: 0.16s; }
        .gallery-container .gallery-item:nth-child(4) { transition-delay: 0.24s; }

        /* ============================= MOBILE NAV ============================= */
        @media (max-width: 768px) {
            .nav-links {
                position: absolute; top: 100%; left: 0; width: 100%;
                flex-direction: column; background: rgba(5,5,5,0.97);
                padding: 2rem 0; align-items: center; gap: 1.5rem;
                border-bottom: 1px solid rgba(255,0,60,0.2);
                clip-path: polygon(0 0, 100% 0, 100% 0, 0 0);
                transition: clip-path 0.4s ease-in-out;
            }
            .nav-links.active { clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%); }
            .menu-toggle { display: block; }
            .featured-content { padding: 1.75rem; }
        }

        /* ============================= REDUCED MOTION ============================= */
        @media (prefers-reduced-motion: reduce) {
            html { scroll-behavior: auto; }
            .boot-screen { animation: none; opacity: 0; visibility: hidden; pointer-events: none; }
            .glitch-title { animation: none; }
            .ticker { animation: none; }
            .scroll-cue span { animation: none; opacity: 1; }
            .reveal { opacity: 1; transform: none; transition: none; }
            .card, .card-img, .gallery-item img, .btn-neon, .back-to-top { transition: none; }
            .boot-bar span { animation: none; width: 100%; }
        }
    </style>
</head>
<body>

    <!-- Boot screen: pure CSS auto-hide after ~1.7s, click anywhere to skip immediately -->
    <div class="boot-screen" id="bootScreen" aria-hidden="true">
        <div class="boot-inner">
            <div class="boot-mark" lang="ja">起動中 — BOOTING</div>
            <div class="boot-bar"><span></span></div>
            <p class="boot-line">SYSTEM ONLINE</p>
        </div>
    </div>

    <div class="jp-rail" aria-hidden="true">
        <span lang="ja">電脳都市 ・ 不夜城 ・ ネオン街 ・ 電脳都市 ・ 不夜城 ・ ネオン街</span>
    </div>

    <nav class="navbar">
        <a href="#home" class="logo">NEON<span>SENSEI</span></a>
        <div class="menu-toggle" id="mobile-menu" role="button" tabindex="0" aria-label="Toggle menu"><i class="fas fa-bars"></i></div>
        <ul class="nav-links">
            <li><a href="#home" class="nav-link active"><span class="nav-en">Home</span><span class="nav-jp" lang="ja">ホーム</span></a></li>
            <li><a href="#updates" class="nav-link"><span class="nav-en">Updates</span><span class="nav-jp" lang="ja">更新情報</span></a></li>
            <li><a href="#artworks" class="nav-link"><span class="nav-en">Gallery</span><span class="nav-jp" lang="ja">ギャラリー</span></a></li>
            <li><a href="#connect" class="nav-link"><span class="nav-en">Connect</span><span class="nav-jp" lang="ja">接続</span></a></li>
        </ul>
    </nav>

    <header class="hero" id="home">
        <div class="hanko" aria-hidden="true">
            <svg viewBox="0 0 120 120">
                <rect x="6" y="6" width="108" height="108" rx="8"></rect>
                <text x="60" y="56" class="hanko-kanji" lang="ja">先生</text>
                <text x="60" y="90" class="hanko-en">NEON</text>
            </svg>
        </div>
        <div class="hero-content">
            <h1 class="glitch-title">NEON SENSEI</h1>
            <p class="hero-jp" lang="ja">電脳都市より愛を込めて</p>
            <p class="hero-subtitle" id="typewriter"></p>
            <a href="#updates" class="btn-neon">Enter the Grid</a>
        </div>
        <div class="scroll-cue" aria-hidden="true"><span></span></div>
    </header>

    <div class="ticker-wrap" aria-hidden="true">
        <div class="ticker">
            <span class="ticker-track">
                <span>SYSTEM ONLINE</span><span class="dot">✦</span>
                <span lang="ja">更新は毎週金曜日</span><span class="dot">✦</span>
                <span>NEW WALLPAPERS EVERY FRIDAY</span><span class="dot">✦</span>
                <span lang="ja">電脳都市へようこそ</span><span class="dot">✦</span>
                <span>FOLLOW FOR DAILY DROPS</span><span class="dot">✦</span>
            </span>
            <span class="ticker-track">
                <span>SYSTEM ONLINE</span><span class="dot">✦</span>
                <span lang="ja">更新は毎週金曜日</span><span class="dot">✦</span>
                <span>NEW WALLPAPERS EVERY FRIDAY</span><span class="dot">✦</span>
                <span lang="ja">電脳都市へようこそ</span><span class="dot">✦</span>
                <span>FOLLOW FOR DAILY DROPS</span><span class="dot">✦</span>
            </span>
        </div>
    </div>

    <section id="updates">
        <div class="section-header reveal">
            <h2 class="section-title">DAILY UPDATES</h2>
            <span class="section-jp" lang="ja">更新情報</span>
        </div>

        <div class="updates-grid">
            <article class="card reveal">
                <div class="card-img-wrap">
                    <img src="https://images.unsplash.com/photo-1780631347040-0c5df6053c2f?q=80&amp;w=900&amp;auto=format&amp;fit=crop" alt="Neon-lit street near Akihabara Station at night" class="card-img" loading="lazy">
                </div>
                <div class="card-content">
                    <span class="card-tag"><span class="tag-jp" lang="ja">話数レビュー</span><span class="tag-en">Episode Review</span></span>
                    <h3 class="card-title">Crimson Requiem: Episode 14 Breaks the Timeline</h3>
                    <p class="card-text">The mid-season twist landed harder than anyone expected — new key animation staff, a reworked color script, and a fight sequence already being frame-by-framed across every forum.</p>
                    <a href="#" class="card-link">Read Log <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>

            <article class="card reveal">
                <div class="card-img-wrap">
                    <img src="https://images.unsplash.com/photo-1764069138714-bcc6783b8e48?q=80&amp;w=900&amp;auto=format&amp;fit=crop" alt="Paper lantern and neon signs in Dotonbori, Osaka" class="card-img" loading="lazy">
                </div>
                <div class="card-content">
                    <span class="card-tag"><span class="tag-jp" lang="ja">新刊情報</span><span class="tag-en">New Volume</span></span>
                    <h3 class="card-title">Static Dreams Vol. 7 Hits Shelves</h3>
                    <p class="card-text">The cyberpunk noir manga trades its rain-soaked alleyways for a full descent into the city's underground data markets — and finally answers a question it's circled since chapter one.</p>
                    <a href="#" class="card-link">Read Log <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>

            <article class="card reveal">
                <div class="card-img-wrap">
                    <img src="https://images.unsplash.com/photo-1677003714423-cf7f1ce0a27d?q=80&amp;w=900&amp;auto=format&amp;fit=crop" alt="Narrow neon-lit alley in Shinjuku's Golden Gai district" class="card-img" loading="lazy">
                </div>
                <div class="card-content">
                    <span class="card-tag"><span class="tag-jp" lang="ja">キャラクター特集</span><span class="tag-en">Character Spotlight</span></span>
                    <h3 class="card-title">Spotlight: Kaze of the Wandering Blade</h3>
                    <p class="card-text">Quiet, sardonic, and impossible to read — Kaze has spent three seasons as the fandom's most quoted character without saying much at all. Here's why the minimalist lead works.</p>
                    <a href="#" class="card-link">Read Log <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>

            <article class="card reveal">
                <div class="card-img-wrap">
                    <img src="https://images.unsplash.com/photo-1644919070369-c0d17244fd88?q=80&amp;w=900&amp;auto=format&amp;fit=crop" alt="Rain-slicked street reflecting neon signs at night" class="card-img" loading="lazy">
                </div>
                <div class="card-content">
                    <span class="card-tag"><span class="tag-jp" lang="ja">イベントレポート</span><span class="tag-en">Event Report</span></span>
                    <h3 class="card-title">Inside NeoCon Tokyo 2026</h3>
                    <p class="card-text">Six halls, four hundred exhibitors, and one very long line for limited acrylic stands. We walked the floor to bring back the announcements and the cosplay that stopped foot traffic.</p>
                    <a href="#" class="card-link">Read Log <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>

            <article class="card reveal">
                <div class="card-img-wrap">
                    <img src="https://images.unsplash.com/photo-1735796788543-f7c76beb16dd?q=80&amp;w=900&amp;auto=format&amp;fit=crop" alt="Illuminated vending machine on an Akihabara street at night" class="card-img" loading="lazy">
                </div>
                <div class="card-content">
                    <span class="card-tag"><span class="tag-jp" lang="ja">壁紙コレクション</span><span class="tag-en">Wallpaper Pack</span></span>
                    <h3 class="card-title">Neon Aesthetic Wallpaper Pack Vol. 6</h3>
                    <p class="card-text">Twelve new high-resolution wallpapers built around this month's color story: magenta undertones, wet asphalt, and just enough grain to feel like film.</p>
                    <a href="#" class="card-link">Access Files <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>

            <article class="card reveal">
                <div class="card-img-wrap">
                    <img src="https://images.unsplash.com/photo-1743055838777-92ede742118e?q=80&amp;w=900&amp;auto=format&amp;fit=crop" alt="Close-up of a glowing neon sign with Japanese characters" class="card-img" loading="lazy">
                </div>
                <div class="card-content">
                    <span class="card-tag"><span class="tag-jp" lang="ja">特集記事</span><span class="tag-en">Feature</span></span>
                    <h3 class="card-title">The Rise of Neo-Retro Animation Styles</h3>
                    <p class="card-text">More studios are reaching for VHS-era color grading and hand-drawn grain over clean digital linework. We trace the trend and ask if it's nostalgia or a real aesthetic shift.</p>
                    <a href="#" class="card-link">Read Log <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>
        </div>
    </section>

    <section class="stats-section reveal">
        <div class="section-header">
            <h2 class="section-title">SYSTEM STATUS</h2>
            <span class="section-jp" lang="ja">システム状況</span>
        </div>
        <div class="stats-grid">
            <div class="stat-block">
                <span class="stat-num">500+</span>
                <span class="stat-label">Series Tracked</span>
                <span class="stat-jp" lang="ja">シリーズ追跡中</span>
            </div>
            <div class="stat-block">
                <span class="stat-num">24/7</span>
                <span class="stat-label">Always Updating</span>
                <span class="stat-jp" lang="ja">更新体制</span>
            </div>
            <div class="stat-block">
                <span class="stat-num">50K+</span>
                <span class="stat-label">Community Members</span>
                <span class="stat-jp" lang="ja">コミュニティ会員</span>
            </div>
            <div class="stat-block">
                <span class="stat-num">1,200+</span>
                <span class="stat-label">Wallpapers Archived</span>
                <span class="stat-jp" lang="ja">壁紙アーカイブ</span>
            </div>
        </div>
    </section>

    <section class="featured-section">
        <div class="section-header reveal">
            <h2 class="section-title">PICK OF THE WEEK</h2>
            <span class="section-jp" lang="ja">今週の一押し</span>
        </div>
        <article class="featured-card reveal">
            <div class="featured-img-wrap">
                <img src="https://images.unsplash.com/photo-1741684650296-19f452c8814f?q=80&amp;w=1400&amp;auto=format&amp;fit=crop" alt="Shibuya Crossing lit up with neon signs at night" loading="lazy">
            </div>
            <div class="featured-content">
                <span class="card-tag"><span class="tag-jp" lang="ja">今週の一押し</span><span class="tag-en">Pick of the Week</span></span>
                <h3 class="card-title">Static Dreams: Why This Cyberpunk Manga Is Rewriting the Genre</h3>
                <p class="card-text">Most cyberpunk manga treat the city as a backdrop. Static Dreams treats it as the antagonist — building its tension around who controls the grid, and what happens when the signal goes quiet.</p>
                <p class="card-text">Volume 7 pushes that premise further than expected, and it's the reason this series keeps showing up on every "best kept secret" list in the community. Here's why it deserves a wider audience.</p>
                <a href="#" class="card-link">Read Full Feature <i class="fas fa-arrow-right"></i></a>
            </div>
        </article>
    </section>

    <section id="artworks">
        <div class="section-header reveal">
            <h2 class="section-title">INSPIRATION BOARD</h2>
            <span class="section-jp" lang="ja">夜景コレクション</span>
        </div>

        <div class="gallery-container">
            <div class="gallery-item reveal">
                <img src="https://images.unsplash.com/photo-1780631347040-0c5df6053c2f?q=80&amp;w=700&amp;auto=format&amp;fit=crop" alt="Neon-lit street near Akihabara Station at night" loading="lazy">
                <div class="gallery-overlay">
                    <h3>Electric Town</h3>
                    <p>Akihabara, Tokyo</p>
                </div>
            </div>
            <div class="gallery-item reveal">
                <img src="https://images.unsplash.com/photo-1677003714423-cf7f1ce0a27d?q=80&amp;w=700&amp;auto=format&amp;fit=crop" alt="Narrow neon-lit alley in Shinjuku's Golden Gai district" loading="lazy">
                <div class="gallery-overlay">
                    <h3>Six Alleys</h3>
                    <p>Golden Gai, Shinjuku</p>
                </div>
            </div>
            <div class="gallery-item reveal">
                <img src="https://images.unsplash.com/photo-1644919070369-c0d17244fd88?q=80&amp;w=700&amp;auto=format&amp;fit=crop" alt="Rain-slicked street reflecting neon signs at night" loading="lazy">
                <div class="gallery-overlay">
                    <h3>After the Rain</h3>
                    <p>Night streets, Japan</p>
                </div>
            </div>
            <div class="gallery-item reveal">
                <img src="https://images.unsplash.com/photo-1743055838777-92ede742118e?q=80&amp;w=700&amp;auto=format&amp;fit=crop" alt="Close-up of a glowing neon sign with Japanese characters" loading="lazy">
                <div class="gallery-overlay">
                    <h3>Character Study</h3>
                    <p>Neon signage detail</p>
                </div>
            </div>
        </div>
    </section>

    <section id="connect" class="newsletter-section reveal">
        <div class="newsletter-inner">
            <h2 class="section-title">JOIN THE GRID</h2>
            <span class="section-jp" lang="ja">グリッドに接続</span>
            <p>Get new episode logs, wallpaper drops, and event reports before anyone else. No spam, just signal.</p>
            <form class="newsletter-form" id="newsletterForm">
                <input type="email" id="newsletterEmail" placeholder="your@email.com" aria-label="Email address" required>
                <button type="submit" id="newsletterBtn">Connect <i class="fas fa-bolt"></i></button>
            </form>
        </div>
    </section>

    <footer>
        <div class="footer-grid">
            <div class="footer-brand">
                <div class="footer-logo">NEON<span>SENSEI</span></div>
                <p class="footer-quote">
                    &ldquo;In the neon glow, we find our truth.&rdquo;
                    <span class="footer-quote-jp" lang="ja">ネオンの輝きの中に、真実を見つける</span>
                </p>
                <div class="social-icons">
                    <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
                    <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                    <a href="#" aria-label="Discord"><i class="fab fa-discord"></i></a>
                    <a href="#" aria-label="GitHub"><i class="fab fa-github"></i></a>
                </div>
            </div>

            <div class="footer-col">
                <h4>Navigate <span lang="ja">ナビゲート</span></h4>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#updates">Daily Updates</a></li>
                    <li><a href="#artworks">Gallery</a></li>
                    <li><a href="#connect">Connect</a></li>
                </ul>
            </div>

            <div class="footer-col">
                <h4>Categories <span lang="ja">カテゴリー</span></h4>
                <ul>
                    <li><a href="#">Episode Reviews</a></li>
                    <li><a href="#">Manga Drops</a></li>
                    <li><a href="#">Wallpapers</a></li>
                    <li><a href="#">Character Spotlights</a></li>
                </ul>
            </div>

            <div class="footer-col">
                <h4>System <span lang="ja">システム</span></h4>
                <p class="status-line"><span class="status-dot" aria-hidden="true"></span> All systems operational</p>
                <p class="status-line-jp" lang="ja">システム稼働中</p>
            </div>
        </div>

        <div class="footer-bottom">
            <p class="copyright">&copy; 2026 Neon Sensei. All rights reserved.</p>
        </div>
    </footer>

    <button class="back-to-top" id="backToTop" aria-label="Back to top"><i class="fas fa-chevron-up"></i></button>

    <script>
        var prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

        // Boot screen: click anywhere to skip immediately (CSS animation already auto-hides it)
        var bootScreen = document.getElementById('bootScreen');
        if (bootScreen) {
            bootScreen.addEventListener('click', function () { bootScreen.style.display = 'none'; });
        }

        // Mobile menu toggle
        var menuToggle = document.getElementById('mobile-menu');
        var navLinks = document.querySelector('.nav-links');

        function toggleMenu() {
            navLinks.classList.toggle('active');
            var icon = menuToggle.querySelector('i');
            icon.classList.toggle('fa-bars');
            icon.classList.toggle('fa-times');
        }
        menuToggle.addEventListener('click', toggleMenu);
        menuToggle.addEventListener('keydown', function (e) {
            if (e.key === 'Enter' || e.key === ' ') { e.preventDefault(); toggleMenu(); }
        });
        document.querySelectorAll('.nav-links a').forEach(function (link) {
            link.addEventListener('click', function () {
                navLinks.classList.remove('active');
                var icon = menuToggle.querySelector('i');
                icon.classList.add('fa-bars');
                icon.classList.remove('fa-times');
            });
        });

        // Typewriter effect for hero subtitle
        var texts = ['Your daily hub for anime updates.', 'Curated neon-Tokyo aesthetic drops.', 'Immerse yourself in the grid.'];
        var typewriterEl = document.getElementById('typewriter');

        if (prefersReducedMotion) {
            typewriterEl.textContent = texts[0];
        } else {
            (function () {
                var count = 0, index = 0, currentText = '', letter = '', isDeleting = false;
                (function type() {
                    if (count === texts.length) count = 0;
                    currentText = texts[count];
                    letter = isDeleting ? currentText.slice(0, --index) : currentText.slice(0, ++index);
                    typewriterEl.textContent = letter + '|';
                    var typeSpeed = isDeleting ? 50 : 100;
                    if (!isDeleting && letter.length === currentText.length) {
                        typeSpeed = 2000; isDeleting = true;
                    } else if (isDeleting && letter.length === 0) {
                        isDeleting = false; count++; typeSpeed = 500;
                    }
                    setTimeout(type, typeSpeed);
                }());
            }());
        }

        // Scroll reveal
        var reveals = document.querySelectorAll('.reveal');
        var revealObserver = new IntersectionObserver(function (entries, observer) {
            entries.forEach(function (entry) {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
        reveals.forEach(function (el) { revealObserver.observe(el); });

        // Active nav link on scroll
        var sections = ['home', 'updates', 'artworks', 'connect'].map(function (id) { return document.getElementById(id); }).filter(Boolean);
        var navByHref = {};
        document.querySelectorAll('.nav-link').forEach(function (a) { navByHref[a.getAttribute('href')] = a; });
        var navObserver = new IntersectionObserver(function (entries) {
            entries.forEach(function (entry) {
                if (entry.isIntersecting) {
                    Object.values(navByHref).forEach(function (a) { a.classList.remove('active'); });
                    var link = navByHref['#' + entry.target.id];
                    if (link) link.classList.add('active');
                }
            });
        }, { rootMargin: '-45% 0px -45% 0px' });
        sections.forEach(function (s) { navObserver.observe(s); });

        // Back to top
        var backToTop = document.getElementById('backToTop');
        window.addEventListener('scroll', function () {
            if (window.scrollY > 600) backToTop.classList.add('visible');
            else backToTop.classList.remove('visible');
        });
        backToTop.addEventListener('click', function () {
            window.scrollTo({ top: 0, behavior: prefersReducedMotion ? 'auto' : 'smooth' });
        });

        // Newsletter form (front-end only demo)
        var newsletterForm = document.getElementById('newsletterForm');
        newsletterForm.addEventListener('submit', function (e) {
            e.preventDefault();
            var btn = document.getElementById('newsletterBtn');
            var input = document.getElementById('newsletterEmail');
            var original = btn.innerHTML;
            btn.innerHTML = 'Connected <i class="fas fa-check"></i>';
            btn.disabled = true;
            input.value = '';
            setTimeout(function () { btn.innerHTML = original; btn.disabled = false; }, 3000);
        });
    </script>
</body>
</html>
