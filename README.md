<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile - Joseph Romero</title>
    <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        :root {
            --bg: #0a0a0f;
            --surface: #111118;
            --border: #1e1e2e;
            --accent: #00f5c4;
            --accent2: #7c6aff;
            --text: #e2e2f0;
            --muted: #6b6b8a;
            --card-bg: #13131d;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            font-family: 'Syne', sans-serif;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Grid background */
        body::before {
            content: '';
            position: fixed;
            inset: 0;
            background-image:
                linear-gradient(rgba(0, 245, 196, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 245, 196, 0.03) 1px, transparent 1px);
            background-size: 40px 40px;
            pointer-events: none;
            z-index: 0;
        }

        .wrapper {
            position: relative;
            z-index: 1;
            max-width: 780px;
            margin: 0 auto;
            padding: 60px 24px 80px;
        }

        /* ── HEADER ── */
        header {
            margin-bottom: 64px;
            animation: fadeUp 0.7s ease both;
        }

        .greeting {
            font-family: 'Space Mono', monospace;
            font-size: 0.8rem;
            color: var(--accent);
            letter-spacing: 0.2em;
            text-transform: uppercase;
            margin-bottom: 16px;
        }

        .greeting::before {
            content: '> ';
            opacity: 0.5;
        }

        header h1 {
            font-size: clamp(2.4rem, 6vw, 4rem);
            font-weight: 800;
            line-height: 1.05;
            margin-bottom: 12px;
        }

        header h1 span {
            color: var(--accent);
        }

        header p {
            font-size: 1rem;
            color: var(--muted);
            font-family: 'Space Mono', monospace;
        }

        .location-tag {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            margin-top: 16px;
            background: var(--border);
            border: 1px solid var(--border);
            border-radius: 100px;
            padding: 6px 14px;
            font-size: 0.78rem;
            color: var(--muted);
            font-family: 'Space Mono', monospace;
        }

        .location-tag::before {
            content: '📍';
            font-size: 0.85rem;
        }

        /* ── DIVIDER ── */
        .divider {
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, var(--accent) 0%, var(--accent2) 50%, transparent 100%);
            margin: 48px 0;
            opacity: 0.3;
        }

        /* ── SECTIONS ── */
        section {
            margin-bottom: 48px;
            animation: fadeUp 0.7s ease both;
        }

        section:nth-child(2) { animation-delay: 0.1s; }
        section:nth-child(3) { animation-delay: 0.2s; }
        section:nth-child(4) { animation-delay: 0.3s; }

        .section-label {
            font-family: 'Space Mono', monospace;
            font-size: 0.7rem;
            color: var(--accent2);
            letter-spacing: 0.2em;
            text-transform: uppercase;
            margin-bottom: 12px;
            opacity: 0.8;
        }

        section h2 {
            font-size: 1.5rem;
            font-weight: 800;
            margin-bottom: 16px;
            position: relative;
            display: inline-block;
        }

        section h2::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, var(--accent), transparent);
        }

        section p {
            color: #a0a0bc;
            line-height: 1.8;
            font-size: 0.95rem;
            margin-bottom: 12px;
        }

        /* ── ABOUT CARD ── */
        .about-card {
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-left: 3px solid var(--accent);
            border-radius: 12px;
            padding: 24px 28px;
        }

        /* ── TECH STACK ── */
        .tech-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 16px;
        }

        .tech-badge {
            font-family: 'Space Mono', monospace;
            font-size: 0.72rem;
            padding: 6px 14px;
            border-radius: 6px;
            background: #0d0d18;
            border: 1px solid var(--border);
            color: var(--accent);
            letter-spacing: 0.05em;
            transition: all 0.2s ease;
            cursor: default;
        }

        .tech-badge:hover {
            border-color: var(--accent);
            background: rgba(0, 245, 196, 0.07);
            transform: translateY(-2px);
        }

        /* ── CURRENTLY CARD ── */
        .currently-block {
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 24px 28px;
        }

        .cert-tag {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            margin-top: 12px;
            background: rgba(124, 106, 255, 0.08);
            border: 1px solid rgba(124, 106, 255, 0.25);
            border-radius: 8px;
            padding: 8px 16px;
            font-size: 0.8rem;
            font-family: 'Space Mono', monospace;
            color: var(--accent2);
        }

        .cert-tag::before {
            content: '🎓';
        }

        /* ── INTERESTS ── */
        .interests-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 12px;
            margin-top: 8px;
        }

        .interest-item {
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 10px;
            padding: 16px 18px;
            font-size: 0.85rem;
            color: #b0b0cc;
            transition: all 0.2s ease;
        }

        .interest-item:hover {
            border-color: var(--accent2);
            transform: translateY(-2px);
        }

        .interest-icon {
            font-size: 1.3rem;
            display: block;
            margin-bottom: 8px;
        }

        /* ── FOOTER ── */
        footer {
            margin-top: 80px;
            padding-top: 24px;
            border-top: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: gap;
            animation: fadeUp 0.7s 0.4s ease both;
        }

        footer p {
            font-family: 'Space Mono', monospace;
            font-size: 0.75rem;
            color: var(--muted);
        }

        .status-dot {
            display: flex;
            align-items: center;
            gap: 8px;
            font-family: 'Space Mono', monospace;
            font-size: 0.72rem;
            color: var(--accent);
        }

        .dot {
            width: 7px;
            height: 7px;
            background: var(--accent);
            border-radius: 50%;
            animation: pulse 2s ease-in-out infinite;
        }

        /* ── ANIMATIONS ── */
        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(24px); }
            to   { opacity: 1; transform: translateY(0); }
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; box-shadow: 0 0 0 0 rgba(0,245,196,0.4); }
            50%       { opacity: 0.7; box-shadow: 0 0 0 6px rgba(0,245,196,0); }
        }

        /* ── RESPONSIVE ── */
        @media (max-width: 520px) {
            .interests-list { grid-template-columns: 1fr 1fr; }
            footer { flex-direction: column; gap: 12px; text-align: center; }
        }
    </style>
</head>
<body>

<div class="wrapper">

    <!-- HEADER -->
    <header>
        <p class="greeting">Hello! Welcome.</p>
        <h1>Joseph <span>Romero</span></h1>
        <p>Systems Engineering student & Software Developer in training.</p>
        <div class="location-tag">Colombia</div>
    </header>

    <div class="divider"></div>

    <!-- ABOUT -->
    <section>
    
        <h2>About Me</h2>
        <div class="about-card">
            <p>
                I am a Systems Engineering student and a software developer in training at Riwi.
                I'm passionate about building practical solutions and constantly sharpening my technical skills.
            </p>
        </div>
    </section>

    <!-- CURRENTLY -->
    <section>

        <h2>Currently</h2>
        <div class="currently-block">
            <p>
                Working on software development and data projects while strengthening my programming skills day by day.
            </p>
            <p>Tech stack I work with:</p>
            <div class="tech-grid">
                <span class="tech-badge">C++</span>
                <span class="tech-badge">Python</span>
                <span class="tech-badge">SQL · MySQL</span>
                <span class="tech-badge">HTML</span>
                <span class="tech-badge">CSS</span>
                <span class="tech-badge">Kotlin</span>
                <span class="tech-badge">.NET WinForms</span>
                <span class="tech-badge">ASP.NET</span>
                <span class="tech-badge">WordPress</span>
                <span class="tech-badge">GitHub</span>
            </div>
            <div class="cert-tag">
                Introduction to Cybersecurity — Cisco (Virtual)
            </div>
        </div>
    </section>

    <!-- INTERESTS -->
    <section>
        <h2>Interests</h2>
        <div class="interests-list">
            <div class="interest-item">
                <span class="interest-icon">💻</span>
                Software Development
            </div>
            <div class="interest-item">
                <span class="interest-icon">🔐</span>
                Cybersecurity
            </div>
            <div class="interest-item">
                <span class="interest-icon">🧩</span>
                Problem Solving
            </div>
            <div class="interest-item">
                <span class="interest-icon">📚</span>
                Continuous Learning
            </div>
        </div>
    </section>

    <div class="divider"></div>

    <!-- FOOTER -->
    <footer>
        <p>© 2026 Joseph Romero</p>
        <div class="status-dot">
            <span class="dot"></span>
            Open to opportunities
        </div>
    </footer>

</div>

</body>
</html>
