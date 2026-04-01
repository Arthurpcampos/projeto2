
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TechPulse Events — O Futuro Começa Aqui</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@400;500;600;700&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,700;1,300&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  /* ============================================
     ROOT & VARIABLES
  ============================================ */
  :root {
    --bg-primary: #050810;
    --bg-secondary: #0a0f1e;
    --bg-card: #0d1428;
    --bg-glass: rgba(13, 20, 40, 0.7);
    --cyan: #00e5ff;
    --cyan-dim: rgba(0, 229, 255, 0.15);
    --purple: #b14fff;
    --purple-dim: rgba(177, 79, 255, 0.15);
    --orange: #ff6b35;
    --orange-dim: rgba(255, 107, 53, 0.15);
    --green: #00ff88;
    --text-primary: #eef2ff;
    --text-secondary: #8892b0;
    --text-muted: #4a5568;
    --border: rgba(255,255,255,0.07);
    --border-glow: rgba(0, 229, 255, 0.3);
    --shadow-cyan: 0 0 30px rgba(0, 229, 255, 0.2);
    --shadow-purple: 0 0 30px rgba(177, 79, 255, 0.2);
    --radius: 12px;
    --radius-lg: 20px;
    --font-display: 'Rajdhani', sans-serif;
    --font-body: 'DM Sans', sans-serif;
    --font-mono: 'Space Mono', monospace;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg-primary);
    color: var(--text-primary);
    font-family: var(--font-body);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ============================================
     SCROLLBAR
  ============================================ */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg-secondary); }
  ::-webkit-scrollbar-thumb { background: var(--purple); border-radius: 3px; }

  /* ============================================
     BACKGROUND GRID
  ============================================ */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* ============================================
     NAVBAR
  ============================================ */
  .navbar {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 1000;
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    background: rgba(5, 8, 16, 0.85);
    border-bottom: 1px solid var(--border);
    padding: 0 2rem;
    height: 70px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .nav-logo {
    font-family: var(--font-display);
    font-size: 1.6rem;
    font-weight: 700;
    letter-spacing: 2px;
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    cursor: pointer;
  }
  .nav-logo span { color: var(--orange); -webkit-text-fill-color: var(--orange); }

  .nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
    align-items: center;
  }

  .nav-links a {
    color: var(--text-secondary);
    text-decoration: none;
    font-size: 0.9rem;
    font-weight: 500;
    letter-spacing: 0.5px;
    transition: color 0.2s;
    cursor: pointer;
  }
  .nav-links a:hover { color: var(--cyan); }

  .nav-actions { display: flex; gap: 1rem; align-items: center; }

  .btn {
    padding: 0.55rem 1.4rem;
    border-radius: 8px;
    font-family: var(--font-body);
    font-size: 0.875rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.25s;
    border: none;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    letter-spacing: 0.3px;
  }

  .btn-ghost {
    background: transparent;
    color: var(--text-secondary);
    border: 1px solid var(--border);
  }
  .btn-ghost:hover {
    border-color: var(--cyan);
    color: var(--cyan);
    box-shadow: 0 0 15px rgba(0,229,255,0.15);
  }

  .btn-primary {
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    color: var(--bg-primary);
    font-weight: 700;
  }
  .btn-primary:hover {
    transform: translateY(-1px);
    box-shadow: 0 8px 25px rgba(0,229,255,0.3);
  }

  .btn-outline {
    background: transparent;
    color: var(--cyan);
    border: 1px solid var(--cyan);
  }
  .btn-outline:hover {
    background: var(--cyan-dim);
    box-shadow: var(--shadow-cyan);
  }

  .btn-danger {
    background: rgba(255, 60, 60, 0.15);
    color: #ff6060;
    border: 1px solid rgba(255, 60, 60, 0.3);
  }
  .btn-danger:hover { background: rgba(255, 60, 60, 0.25); }

  /* ============================================
     HERO
  ============================================ */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 100px 2rem 4rem;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 50% at 70% 50%, rgba(177,79,255,0.12) 0%, transparent 70%),
      radial-gradient(ellipse 40% 40% at 20% 60%, rgba(0,229,255,0.08) 0%, transparent 60%);
    pointer-events: none;
  }

  .hero-content {
    position: relative;
    z-index: 1;
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
    width: 100%;
  }

  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: var(--cyan-dim);
    border: 1px solid rgba(0,229,255,0.3);
    border-radius: 50px;
    padding: 0.4rem 1rem;
    font-family: var(--font-mono);
    font-size: 0.72rem;
    color: var(--cyan);
    letter-spacing: 1px;
    margin-bottom: 1.5rem;
    text-transform: uppercase;
  }

  .pulse-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--green);
    box-shadow: 0 0 10px var(--green);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0%,100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  .hero-title {
    font-family: var(--font-display);
    font-size: clamp(3rem, 6vw, 5.5rem);
    font-weight: 700;
    line-height: 1.05;
    letter-spacing: 1px;
    margin-bottom: 1.5rem;
  }

  .hero-title .grad {
    background: linear-gradient(135deg, var(--cyan) 0%, var(--purple) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-subtitle {
    color: var(--text-secondary);
    font-size: 1.1rem;
    line-height: 1.75;
    margin-bottom: 2.5rem;
    max-width: 480px;
  }

  .hero-cta { display: flex; gap: 1rem; flex-wrap: wrap; }

  .hero-stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }

  .stat-card {
    background: var(--bg-glass);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1.5rem;
    text-align: center;
    backdrop-filter: blur(10px);
    transition: border-color 0.3s, transform 0.3s;
    position: relative;
    overflow: hidden;
  }
  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--cyan), var(--purple));
    opacity: 0;
    transition: opacity 0.3s;
  }
  .stat-card:hover { border-color: var(--border-glow); transform: translateY(-3px); }
  .stat-card:hover::before { opacity: 1; }

  .stat-number {
    font-family: var(--font-display);
    font-size: 2.5rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .stat-label { color: var(--text-secondary); font-size: 0.8rem; margin-top: 0.3rem; }

  /* ============================================
     SECTIONS
  ============================================ */
  section { position: relative; z-index: 1; }

  .section-header {
    text-align: center;
    margin-bottom: 3rem;
  }

  .section-tag {
    font-family: var(--font-mono);
    font-size: 0.75rem;
    color: var(--cyan);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 0.75rem;
    display: block;
  }

  .section-title {
    font-family: var(--font-display);
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 700;
    letter-spacing: 1px;
    line-height: 1.1;
  }

  .section-sub {
    color: var(--text-secondary);
    margin-top: 0.75rem;
    font-size: 1rem;
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
    line-height: 1.7;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 5rem 2rem;
  }

  /* ============================================
     SEARCH & FILTER
  ============================================ */
  .search-section {
    background: var(--bg-secondary);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 3rem 2rem;
  }

  .search-wrapper {
    max-width: 1200px;
    margin: 0 auto;
  }

  .search-bar {
    display: flex;
    gap: 1rem;
    margin-bottom: 1.5rem;
    flex-wrap: wrap;
  }

  .search-input-wrap {
    flex: 1;
    position: relative;
    min-width: 280px;
  }

  .search-icon {
    position: absolute;
    left: 1.1rem;
    top: 50%;
    transform: translateY(-50%);
    color: var(--text-muted);
    font-size: 1.1rem;
    pointer-events: none;
  }

  .input {
    width: 100%;
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 0.85rem 1.2rem 0.85rem 2.8rem;
    color: var(--text-primary);
    font-family: var(--font-body);
    font-size: 0.95rem;
    transition: border-color 0.25s, box-shadow 0.25s;
    outline: none;
  }
  .input:focus {
    border-color: var(--cyan);
    box-shadow: 0 0 0 3px rgba(0,229,255,0.1);
  }
  .input::placeholder { color: var(--text-muted); }

  .date-input-wrap {
    position: relative;
    min-width: 200px;
  }
  .date-input-wrap .search-icon { left: 1rem; }
  .date-input-wrap .input { padding-left: 2.7rem; }

  .filter-chips {
    display: flex;
    gap: 0.6rem;
    flex-wrap: wrap;
    align-items: center;
  }

  .filter-label {
    font-family: var(--font-mono);
    font-size: 0.72rem;
    color: var(--text-muted);
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-right: 0.4rem;
  }

  .chip {
    padding: 0.4rem 1rem;
    border-radius: 50px;
    font-size: 0.8rem;
    font-weight: 500;
    cursor: pointer;
    border: 1px solid var(--border);
    background: var(--bg-card);
    color: var(--text-secondary);
    transition: all 0.2s;
  }
  .chip:hover { border-color: var(--cyan); color: var(--cyan); }
  .chip.active {
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    border-color: transparent;
    color: var(--bg-primary);
    font-weight: 700;
  }

  .results-count {
    font-family: var(--font-mono);
    font-size: 0.8rem;
    color: var(--text-muted);
    margin-top: 1rem;
  }
  .results-count span { color: var(--cyan); }

  /* ============================================
     EVENTS GRID
  ============================================ */
  .events-section { padding: 5rem 2rem; }

  .events-grid {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
    gap: 1.75rem;
  }

  .event-card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    overflow: hidden;
    transition: all 0.35s cubic-bezier(0.25, 0.8, 0.25, 1);
    cursor: pointer;
    position: relative;
    animation: fadeUp 0.5s ease both;
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .event-card:hover {
    transform: translateY(-6px);
    border-color: rgba(0,229,255,0.25);
    box-shadow: 0 20px 60px rgba(0,0,0,0.4), 0 0 30px rgba(0,229,255,0.08);
  }

  .event-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
    display: block;
    transition: transform 0.4s;
  }
  .event-card:hover .event-image { transform: scale(1.04); }

  .event-img-wrap {
    overflow: hidden;
    position: relative;
  }

  .event-category-badge {
    position: absolute;
    top: 1rem;
    left: 1rem;
    padding: 0.3rem 0.8rem;
    border-radius: 50px;
    font-size: 0.72rem;
    font-weight: 700;
    font-family: var(--font-mono);
    letter-spacing: 0.5px;
    text-transform: uppercase;
    backdrop-filter: blur(10px);
  }

  .badge-ai { background: rgba(0,229,255,0.2); color: var(--cyan); border: 1px solid rgba(0,229,255,0.4); }
  .badge-dev { background: rgba(177,79,255,0.2); color: var(--purple); border: 1px solid rgba(177,79,255,0.4); }
  .badge-security { background: rgba(255,107,53,0.2); color: var(--orange); border: 1px solid rgba(255,107,53,0.4); }
  .badge-cloud { background: rgba(0,255,136,0.15); color: var(--green); border: 1px solid rgba(0,255,136,0.3); }
  .badge-ux { background: rgba(255,80,140,0.2); color: #ff508c; border: 1px solid rgba(255,80,140,0.4); }
  .badge-web3 { background: rgba(255,200,0,0.15); color: #ffc800; border: 1px solid rgba(255,200,0,0.3); }

  .event-body { padding: 1.5rem; }

  .event-meta {
    display: flex;
    gap: 1rem;
    margin-bottom: 0.75rem;
    font-family: var(--font-mono);
    font-size: 0.72rem;
    color: var(--text-muted);
  }

  .event-meta-item { display: flex; align-items: center; gap: 0.35rem; }

  .event-title {
    font-family: var(--font-display);
    font-size: 1.35rem;
    font-weight: 700;
    letter-spacing: 0.5px;
    margin-bottom: 0.6rem;
    line-height: 1.2;
    color: var(--text-primary);
    transition: color 0.2s;
  }
  .event-card:hover .event-title { color: var(--cyan); }

  .event-desc {
    font-size: 0.875rem;
    color: var(--text-secondary);
    line-height: 1.65;
    margin-bottom: 1.25rem;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .event-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 1rem;
    border-top: 1px solid var(--border);
  }

  .event-price {
    font-family: var(--font-display);
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--green);
  }
  .event-price.paid { color: var(--cyan); }

  .event-spots {
    font-size: 0.78rem;
    color: var(--text-muted);
    margin-top: 0.1rem;
  }

  .spots-bar {
    width: 80px;
    height: 3px;
    background: var(--border);
    border-radius: 2px;
    margin-top: 0.3rem;
    overflow: hidden;
  }
  .spots-fill {
    height: 100%;
    border-radius: 2px;
    background: linear-gradient(90deg, var(--cyan), var(--purple));
  }

  .no-results {
    text-align: center;
    padding: 5rem 2rem;
    color: var(--text-muted);
    grid-column: 1 / -1;
  }
  .no-results .emoji { font-size: 3rem; margin-bottom: 1rem; }
  .no-results h3 { font-family: var(--font-display); font-size: 1.5rem; margin-bottom: 0.5rem; color: var(--text-secondary); }

  /* ============================================
     MODAL
  ============================================ */
  .modal-overlay {
    position: fixed;
    inset: 0;
    background: rgba(5, 8, 16, 0.92);
    backdrop-filter: blur(12px);
    z-index: 2000;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 2rem;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s;
  }
  .modal-overlay.open {
    opacity: 1;
    pointer-events: all;
  }

  .modal {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    width: 100%;
    max-width: 580px;
    max-height: 90vh;
    overflow-y: auto;
    transform: scale(0.95) translateY(20px);
    transition: transform 0.3s cubic-bezier(0.25,0.8,0.25,1);
    position: relative;
  }
  .modal-overlay.open .modal { transform: scale(1) translateY(0); }

  .modal-close {
    position: absolute;
    top: 1.2rem;
    right: 1.2rem;
    background: var(--border);
    border: none;
    width: 34px; height: 34px;
    border-radius: 50%;
    color: var(--text-secondary);
    cursor: pointer;
    font-size: 1.1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.2s;
    z-index: 10;
  }
  .modal-close:hover { background: rgba(255,255,255,0.1); color: white; }

  .modal-image {
    width: 100%;
    height: 220px;
    object-fit: cover;
    border-radius: var(--radius-lg) var(--radius-lg) 0 0;
  }

  .modal-body { padding: 2rem; }

  .modal-title {
    font-family: var(--font-display);
    font-size: 1.8rem;
    font-weight: 700;
    letter-spacing: 0.5px;
    margin-bottom: 0.5rem;
  }

  .modal-details {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
    margin: 1.5rem 0;
  }

  .modal-detail {
    background: var(--bg-secondary);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1rem;
  }
  .modal-detail-label {
    font-family: var(--font-mono);
    font-size: 0.68rem;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 0.35rem;
  }
  .modal-detail-value {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--text-primary);
  }

  .modal-desc {
    color: var(--text-secondary);
    line-height: 1.75;
    font-size: 0.9rem;
    margin-bottom: 1.5rem;
  }

  .countdown-wrap {
    background: linear-gradient(135deg, rgba(0,229,255,0.06), rgba(177,79,255,0.06));
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1.25rem;
    margin-bottom: 1.5rem;
    text-align: center;
  }
  .countdown-label {
    font-family: var(--font-mono);
    font-size: 0.7rem;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 0.75rem;
  }
  .countdown-digits {
    display: flex;
    justify-content: center;
    gap: 0.75rem;
    font-family: var(--font-display);
    font-size: 1.8rem;
    font-weight: 700;
  }
  .countdown-unit { text-align: center; }
  .countdown-unit span:first-child {
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: block;
  }
  .countdown-unit small {
    font-size: 0.6rem;
    color: var(--text-muted);
    font-family: var(--font-mono);
    display: block;
    margin-top: -2px;
    text-transform: uppercase;
    letter-spacing: 1px;
    -webkit-text-fill-color: var(--text-muted);
  }
  .countdown-sep { color: var(--purple); opacity: 0.5; }

  /* ============================================
     AUTH MODAL
  ============================================ */
  .auth-modal { max-width: 480px; }

  .auth-tabs {
    display: flex;
    border-bottom: 1px solid var(--border);
    margin-bottom: 2rem;
  }

  .auth-tab {
    flex: 1;
    padding: 1rem;
    text-align: center;
    cursor: pointer;
    font-family: var(--font-display);
    font-size: 1rem;
    font-weight: 600;
    letter-spacing: 0.5px;
    color: var(--text-muted);
    border-bottom: 2px solid transparent;
    margin-bottom: -1px;
    transition: all 0.2s;
  }
  .auth-tab.active { color: var(--cyan); border-bottom-color: var(--cyan); }

  .auth-form { display: flex; flex-direction: column; gap: 1.1rem; }

  .form-group { display: flex; flex-direction: column; gap: 0.5rem; }

  .form-label {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--text-secondary);
    letter-spacing: 0.3px;
  }

  .form-input {
    background: var(--bg-secondary);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 0.8rem 1.1rem;
    color: var(--text-primary);
    font-family: var(--font-body);
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.2s, box-shadow 0.2s;
  }
  .form-input:focus {
    border-color: var(--cyan);
    box-shadow: 0 0 0 3px rgba(0,229,255,0.1);
  }

  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

  .form-check {
    display: flex;
    align-items: flex-start;
    gap: 0.7rem;
    font-size: 0.82rem;
    color: var(--text-secondary);
    cursor: pointer;
  }
  .form-check input[type="checkbox"] {
    width: 16px; height: 16px;
    accent-color: var(--cyan);
    margin-top: 1px;
    flex-shrink: 0;
  }

  .form-divider {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin: 0.5rem 0;
    color: var(--text-muted);
    font-size: 0.8rem;
  }
  .form-divider::before, .form-divider::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .btn-full { width: 100%; justify-content: center; padding: 0.85rem; font-size: 0.95rem; }

  .auth-switch {
    text-align: center;
    font-size: 0.85rem;
    color: var(--text-muted);
  }
  .auth-switch a { color: var(--cyan); cursor: pointer; text-decoration: none; }
  .auth-switch a:hover { text-decoration: underline; }

  .toast {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1rem 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
    z-index: 3000;
    transform: translateY(100px);
    opacity: 0;
    transition: all 0.35s cubic-bezier(0.25,0.8,0.25,1);
    min-width: 280px;
    max-width: 380px;
    box-shadow: 0 10px 40px rgba(0,0,0,0.5);
  }
  .toast.show { transform: translateY(0); opacity: 1; }
  .toast-icon { font-size: 1.3rem; flex-shrink: 0; }
  .toast-text { flex: 1; }
  .toast-title { font-weight: 700; font-size: 0.9rem; margin-bottom: 0.1rem; }
  .toast-sub { font-size: 0.78rem; color: var(--text-muted); }
  .toast.success { border-color: rgba(0,255,136,0.3); }
  .toast.success .toast-icon { color: var(--green); }
  .toast.error { border-color: rgba(255,100,100,0.3); }
  .toast.error .toast-icon { color: #ff6060; }
  .toast.info { border-color: rgba(0,229,255,0.3); }
  .toast.info .toast-icon { color: var(--cyan); }

  /* ============================================
     USER PANEL
  ============================================ */
  .user-avatar {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-display);
    font-weight: 700;
    font-size: 0.9rem;
    color: var(--bg-primary);
    cursor: pointer;
    border: 2px solid transparent;
    transition: border-color 0.2s;
  }
  .user-avatar:hover { border-color: var(--cyan); }

  .user-menu {
    position: absolute;
    top: calc(100% + 10px);
    right: 0;
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    min-width: 220px;
    padding: 0.5rem;
    z-index: 100;
    display: none;
    box-shadow: 0 10px 40px rgba(0,0,0,0.5);
  }
  .user-menu.open { display: block; }

  .user-menu-header {
    padding: 0.75rem 0.75rem 0.6rem;
    border-bottom: 1px solid var(--border);
    margin-bottom: 0.4rem;
  }
  .user-menu-name { font-weight: 700; font-size: 0.9rem; }
  .user-menu-email { font-size: 0.75rem; color: var(--text-muted); }

  .menu-item {
    display: flex;
    align-items: center;
    gap: 0.7rem;
    padding: 0.65rem 0.75rem;
    border-radius: 8px;
    cursor: pointer;
    font-size: 0.875rem;
    color: var(--text-secondary);
    transition: all 0.15s;
  }
  .menu-item:hover { background: rgba(255,255,255,0.05); color: var(--text-primary); }
  .menu-item.danger { color: #ff6060; }
  .menu-item.danger:hover { background: rgba(255,96,96,0.1); }

  .nav-user-wrap { position: relative; }

  /* ============================================
     MY REGISTRATIONS
  ============================================ */
  .registrations-list { display: flex; flex-direction: column; gap: 1rem; }

  .reg-item {
    background: var(--bg-secondary);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1.25rem 1.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .reg-info { flex: 1; }
  .reg-title { font-family: var(--font-display); font-size: 1.1rem; font-weight: 700; margin-bottom: 0.3rem; }
  .reg-meta { font-size: 0.8rem; color: var(--text-muted); font-family: var(--font-mono); }

  .reg-status {
    padding: 0.3rem 0.8rem;
    border-radius: 50px;
    font-size: 0.75rem;
    font-weight: 700;
    font-family: var(--font-mono);
  }
  .reg-status.confirmed { background: rgba(0,255,136,0.15); color: var(--green); border: 1px solid rgba(0,255,136,0.3); }
  .reg-status.pending { background: rgba(255,200,0,0.12); color: #ffc800; border: 1px solid rgba(255,200,0,0.3); }

  /* ============================================
     FEATURES
  ============================================ */
  .features-section {
    background: var(--bg-secondary);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }

  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5rem;
    max-width: 1200px;
    margin: 0 auto;
  }

  .feature-card {
    padding: 2rem;
    border-radius: var(--radius);
    border: 1px solid var(--border);
    background: var(--bg-card);
    transition: all 0.3s;
  }
  .feature-card:hover { border-color: var(--border-glow); transform: translateY(-4px); }

  .feature-icon {
    font-size: 2rem;
    margin-bottom: 1rem;
    display: block;
    filter: drop-shadow(0 0 10px rgba(0,229,255,0.5));
  }

  .feature-title {
    font-family: var(--font-display);
    font-size: 1.15rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
    letter-spacing: 0.5px;
  }

  .feature-desc {
    font-size: 0.875rem;
    color: var(--text-secondary);
    line-height: 1.6;
  }

  /* ============================================
     NEWSLETTER
  ============================================ */
  .newsletter-section {
    background: linear-gradient(135deg, rgba(0,229,255,0.04) 0%, rgba(177,79,255,0.06) 100%);
    border-top: 1px solid var(--border);
  }

  .newsletter-wrap {
    max-width: 600px;
    margin: 0 auto;
    text-align: center;
  }

  .newsletter-form {
    display: flex;
    gap: 1rem;
    margin-top: 2rem;
    flex-wrap: wrap;
  }
  .newsletter-form .input { flex: 1; min-width: 240px; }

  /* ============================================
     FOOTER
  ============================================ */
  footer {
    background: var(--bg-secondary);
    border-top: 1px solid var(--border);
    padding: 3rem 2rem 2rem;
  }

  .footer-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 2rem;
  }

  .footer-brand {
    font-family: var(--font-display);
    font-size: 1.4rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .footer-copy {
    font-size: 0.82rem;
    color: var(--text-muted);
  }

  .footer-links {
    display: flex;
    gap: 1.5rem;
    list-style: none;
  }
  .footer-links a {
    font-size: 0.85rem;
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .footer-links a:hover { color: var(--cyan); }

  /* ============================================
     TICKET CONFIRMATION
  ============================================ */
  .ticket-card {
    background: linear-gradient(135deg, rgba(0,229,255,0.06), rgba(177,79,255,0.06));
    border: 1px solid rgba(0,229,255,0.2);
    border-radius: var(--radius-lg);
    padding: 2rem;
    margin-top: 2rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .ticket-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--cyan), var(--purple), var(--orange));
  }
  .ticket-id {
    font-family: var(--font-mono);
    font-size: 0.75rem;
    color: var(--text-muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }
  .ticket-code {
    font-family: var(--font-mono);
    font-size: 1.6rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--cyan), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    letter-spacing: 4px;
  }

  /* Scrollbar for modal */
  .modal::-webkit-scrollbar { width: 4px; }
  .modal::-webkit-scrollbar-track { background: transparent; }
  .modal::-webkit-scrollbar-thumb { background: var(--border); border-radius: 2px; }

  /* Mobile menu toggle */
  .menu-toggle { display: none; }

  @media (max-width: 768px) {
    .hero-content { grid-template-columns: 1fr; gap: 2rem; }
    .hero-stats { display: none; }
    .events-grid { grid-template-columns: 1fr; }
    .modal-details { grid-template-columns: 1fr; }
    .form-row { grid-template-columns: 1fr; }
    .nav-links { display: none; }
    .menu-toggle { display: flex; }
    .newsletter-form { flex-direction: column; }
    .footer-inner { flex-direction: column; align-items: flex-start; }
  }

  /* Glow line accent */
  .glow-line {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--cyan), var(--purple), transparent);
    opacity: 0.4;
    margin: 0;
  }

  /* View toggle */
  .view-toggle { display: flex; gap: 0.5rem; margin-bottom: 2rem; max-width: 1200px; margin-left: auto; margin-right: auto; justify-content: flex-end; padding: 0 2rem; }
  .view-btn {
    padding: 0.5rem;
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 8px;
    color: var(--text-muted);
    cursor: pointer;
    transition: all 0.2s;
    font-size: 1rem;
    width: 36px; height: 36px;
    display: flex; align-items: center; justify-content: center;
  }
  .view-btn.active { border-color: var(--cyan); color: var(--cyan); background: var(--cyan-dim); }

  /* List view */
  .events-grid.list-view { grid-template-columns: 1fr; }
  .events-grid.list-view .event-card {
    display: grid;
    grid-template-columns: 260px 1fr;
  }
  .events-grid.list-view .event-img-wrap { height: 100%; }
  .events-grid.list-view .event-image { height: 100%; }

  @media (max-width: 700px) {
    .events-grid.list-view .event-card { grid-template-columns: 1fr; }
    .events-grid.list-view .event-img-wrap { height: 180px; }
  }
</style>
</head>
<body>

<!-- NAVBAR -->
<nav class="navbar">
  <div class="nav-logo" onclick="scrollToTop()">TECH<span>PULSE</span></div>
  <ul class="nav-links">
    <li><a onclick="scrollTo('events')">Eventos</a></li>
    <li><a onclick="scrollTo('features')">Recursos</a></li>
    <li><a onclick="scrollTo('newsletter')">Newsletter</a></li>
  </ul>
  <div class="nav-actions">
    <div id="nav-auth-btns">
      <button class="btn btn-ghost" onclick="openAuth('login')">Entrar</button>
      <button class="btn btn-primary" onclick="openAuth('register')">Cadastrar</button>
    </div>
    <div id="nav-user-wrap" class="nav-user-wrap" style="display:none;">
      <div class="user-avatar" id="user-avatar" onclick="toggleUserMenu()"></div>
      <div class="user-menu" id="user-menu">
        <div class="user-menu-header">
          <div class="user-menu-name" id="menu-name"></div>
          <div class="user-menu-email" id="menu-email"></div>
        </div>
        <div class="menu-item" onclick="openMyRegistrations()">🎫 Minhas Inscrições</div>
        <div class="menu-item" onclick="openEditProfile()">⚙️ Editar Perfil</div>
        <div class="menu-item danger" onclick="logout()">↩ Sair</div>
      </div>
    </div>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <div>
      <div class="hero-tag">
        <div class="pulse-dot"></div>
        Plataforma #1 em Eventos Tech
      </div>
      <h1 class="hero-title">
        O Futuro da<br><span class="grad">Tecnologia</span><br>Acontece Aqui
      </h1>
      <p class="hero-subtitle">
        Encontre, explore e inscreva-se nos melhores eventos de tecnologia do Brasil. Hackathons, conferências, workshops e muito mais.
      </p>
      <div class="hero-cta">
        <button class="btn btn-primary" onclick="scrollTo('events')" style="padding:0.75rem 2rem;font-size:1rem;">
          🚀 Explorar Eventos
        </button>
        <button class="btn btn-ghost" onclick="openAuth('register')" style="padding:0.75rem 1.5rem;font-size:1rem;">
          Criar conta grátis
        </button>
      </div>
    </div>
    <div class="hero-stats">
      <div class="stat-card">
        <div class="stat-number">8+</div>
        <div class="stat-label">Eventos Ativos</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">2.4K</div>
        <div class="stat-label">Participantes</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">98%</div>
        <div class="stat-label">Satisfação</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">15+</div>
        <div class="stat-label">Palestrantes</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">5</div>
        <div class="stat-label">Cidades</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">12</div>
        <div class="stat-label">Parceiros</div>
      </div>
    </div>
  </div>
</section>

<div class="glow-line"></div>

<!-- SEARCH & FILTER -->
<section class="search-section" id="search">
  <div class="search-wrapper">
    <div class="search-bar">
      <div class="search-input-wrap">
        <span class="search-icon">🔍</span>
        <input class="input" id="search-input" type="text" placeholder="Buscar eventos por nome, tecnologia ou tema…" oninput="filterEvents()">
      </div>
      <div class="date-input-wrap">
        <span class="search-icon">📅</span>
        <input class="input" id="date-input" type="date" oninput="filterEvents()">
      </div>
      <button class="btn btn-outline" onclick="clearFilters()">✕ Limpar</button>
    </div>
    <div class="filter-chips">
      <span class="filter-label">Filtrar:</span>
      <div class="chip active" onclick="setCategory('all', this)">Todos</div>
      <div class="chip" onclick="setCategory('AI', this)">🤖 IA & ML</div>
      <div class="chip" onclick="setCategory('dev', this)">💻 Dev</div>
      <div class="chip" onclick="setCategory('security', this)">🔐 Segurança</div>
      <div class="chip" onclick="setCategory('cloud', this)">☁️ Cloud</div>
      <div class="chip" onclick="setCategory('ux', this)">🎨 UX/UI</div>
      <div class="chip" onclick="setCategory('web3', this)">🌐 Web3</div>
      <div class="chip" onclick="setCategory('free', this)">🎁 Gratuito</div>
    </div>
    <div class="results-count" id="results-count"></div>
  </div>
</section>

<!-- VIEW TOGGLE -->
<div class="view-toggle" style="margin-top:2rem;">
  <button class="view-btn active" id="grid-btn" onclick="setView('grid')" title="Grade">⊞</button>
  <button class="view-btn" id="list-btn" onclick="setView('list')" title="Lista">☰</button>
</div>

<!-- EVENTS -->
<section class="events-section" id="events">
  <div class="events-grid" id="events-grid"></div>
</section>

<!-- FEATURES -->
<section class="features-section" id="features">
  <div class="container">
    <div class="section-header">
      <span class="section-tag">// por que nos escolher</span>
      <h2 class="section-title">Uma experiência <span style="background:linear-gradient(135deg,var(--cyan),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">completa</span></h2>
      <p class="section-sub">Tudo que você precisa para participar dos melhores eventos tech em um único lugar.</p>
    </div>
    <div class="features-grid">
      <div class="feature-card">
        <span class="feature-icon">🎯</span>
        <div class="feature-title">Inscrição em 1 Clique</div>
        <div class="feature-desc">Cadastre-se e inscreva-se em qualquer evento de forma rápida e segura. Confirmação instantânea por e-mail.</div>
      </div>
      <div class="feature-card">
        <span class="feature-icon">🔔</span>
        <div class="feature-title">Lembretes Inteligentes</div>
        <div class="feature-desc">Receba notificações sobre os eventos que você se inscreveu. Nunca perca um evento importante.</div>
      </div>
      <div class="feature-card">
        <span class="feature-icon">🎫</span>
        <div class="feature-title">Ingresso Digital</div>
        <div class="feature-desc">Seu ingresso fica salvo diretamente na plataforma com QR Code exclusivo para acesso rápido.</div>
      </div>
      <div class="feature-card">
        <span class="feature-icon">🔍</span>
        <div class="feature-title">Busca Avançada</div>
        <div class="feature-desc">Filtre por data, categoria, localização e preço. Encontre exatamente o evento que você procura.</div>
      </div>
    </div>
  </div>
</section>

<!-- NEWSLETTER -->
<section class="newsletter-section" id="newsletter">
  <div class="container">
    <div class="newsletter-wrap">
      <span class="section-tag">// fique por dentro</span>
      <h2 class="section-title">Newsletter <span style="background:linear-gradient(135deg,var(--cyan),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">Tech</span></h2>
      <p class="section-sub" style="margin-top:0.75rem;">Receba novidades sobre eventos, tecnologia e oportunidades diretamente no seu e-mail.</p>
      <div class="newsletter-form">
        <input class="input" id="nl-email" type="email" placeholder="seu@email.com" style="padding-left:1.2rem;">
        <button class="btn btn-primary" onclick="subscribeNewsletter()" style="padding:0.85rem 1.5rem;white-space:nowrap;">Inscrever-se →</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div>
      <div class="footer-brand">TECHPULSE</div>
      <div class="footer-copy" style="margin-top:0.5rem;">© 2025 TechPulse Events. Todos os direitos reservados.</div>
    </div>
    <ul class="footer-links">
      <li><a href="#">Sobre</a></li>
      <li><a href="#">Contato</a></li>
      <li><a href="#">Privacidade</a></li>
      <li><a href="#">Termos</a></li>
    </ul>
  </div>
</footer>

<!-- ===================== EVENT DETAIL MODAL ===================== -->
<div class="modal-overlay" id="event-modal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('event-modal')">✕</button>
    <img class="modal-image" id="modal-img" src="" alt="">
    <div class="modal-body">
      <div id="modal-badge"></div>
      <h2 class="modal-title" id="modal-title"></h2>
      <div class="modal-details" id="modal-details"></div>
      <p class="modal-desc" id="modal-desc"></p>
      <div class="countdown-wrap" id="modal-countdown">
        <div class="countdown-label">⏱ Tempo para o evento</div>
        <div class="countdown-digits" id="countdown-digits"></div>
      </div>
      <div id="modal-action"></div>
    </div>
  </div>
</div>

<!-- ===================== AUTH MODAL ===================== -->
<div class="modal-overlay" id="auth-modal">
  <div class="modal auth-modal">
    <button class="modal-close" onclick="closeModal('auth-modal')">✕</button>
    <div class="modal-body" style="padding-top:2.5rem;">
      <div class="auth-tabs">
        <div class="auth-tab active" id="tab-login" onclick="switchTab('login')">Entrar</div>
        <div class="auth-tab" id="tab-register" onclick="switchTab('register')">Cadastrar</div>
      </div>
      <!-- LOGIN -->
      <div id="login-form">
        <div class="auth-form">
          <div class="form-group">
            <label class="form-label">E-mail</label>
            <input class="form-input" id="login-email" type="email" placeholder="seu@email.com">
          </div>
          <div class="form-group">
            <label class="form-label">Senha</label>
            <input class="form-input" id="login-pass" type="password" placeholder="••••••••">
          </div>
          <button class="btn btn-primary btn-full" onclick="doLogin()">Entrar na conta →</button>
          <p class="auth-switch">Não tem conta? <a onclick="switchTab('register')">Cadastre-se grátis</a></p>
        </div>
      </div>
      <!-- REGISTER -->
      <div id="register-form" style="display:none;">
        <div class="auth-form">
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">Nome</label>
              <input class="form-input" id="reg-name" type="text" placeholder="João">
            </div>
            <div class="form-group">
              <label class="form-label">Sobrenome</label>
              <input class="form-input" id="reg-last" type="text" placeholder="Silva">
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">E-mail</label>
            <input class="form-input" id="reg-email" type="email" placeholder="seu@email.com">
          </div>
          <div class="form-group">
            <label class="form-label">Área de atuação</label>
            <select class="form-input" id="reg-area" style="cursor:pointer;">
              <option value="">Selecione...</option>
              <option>Desenvolvimento de Software</option>
              <option>Inteligência Artificial / ML</option>
              <option>Segurança da Informação</option>
              <option>Cloud & DevOps</option>
              <option>UX/UI Design</option>
              <option>Blockchain / Web3</option>
              <option>Gestão de Produto</option>
              <option>Estudante</option>
              <option>Outra</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label">Senha</label>
            <input class="form-input" id="reg-pass" type="password" placeholder="Mínimo 6 caracteres">
          </div>
          <label class="form-check">
            <input type="checkbox" id="reg-terms">
            <span>Li e aceito os <a href="#" style="color:var(--cyan);">Termos de Uso</a> e a <a href="#" style="color:var(--cyan);">Política de Privacidade</a></span>
          </label>
          <button class="btn btn-primary btn-full" onclick="doRegister()">Criar conta grátis 🚀</button>
          <p class="auth-switch">Já tem conta? <a onclick="switchTab('login')">Faça login</a></p>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ===================== MY REGISTRATIONS MODAL ===================== -->
<div class="modal-overlay" id="reg-modal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('reg-modal')">✕</button>
    <div class="modal-body" style="padding-top:2.5rem;">
      <h2 class="modal-title" style="margin-bottom:1.5rem;">🎫 Minhas Inscrições</h2>
      <div id="my-registrations-list"></div>
    </div>
  </div>
</div>

<!-- ===================== EDIT PROFILE MODAL ===================== -->
<div class="modal-overlay" id="profile-modal">
  <div class="modal auth-modal">
    <button class="modal-close" onclick="closeModal('profile-modal')">✕</button>
    <div class="modal-body" style="padding-top:2.5rem;">
      <h2 class="modal-title" style="margin-bottom:1.5rem;">⚙️ Editar Perfil</h2>
      <div class="auth-form">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Nome</label>
            <input class="form-input" id="edit-name" type="text">
          </div>
          <div class="form-group">
            <label class="form-label">Sobrenome</label>
            <input class="form-input" id="edit-last" type="text">
          </div>
        </div>
        <div class="form-group">
          <label class="form-label">E-mail</label>
          <input class="form-input" id="edit-email" type="email">
        </div>
        <div class="form-group">
          <label class="form-label">Área de atuação</label>
          <select class="form-input" id="edit-area" style="cursor:pointer;">
            <option value="">Selecione...</option>
            <option>Desenvolvimento de Software</option>
            <option>Inteligência Artificial / ML</option>
            <option>Segurança da Informação</option>
            <option>Cloud & DevOps</option>
            <option>UX/UI Design</option>
            <option>Blockchain / Web3</option>
            <option>Gestão de Produto</option>
            <option>Estudante</option>
            <option>Outra</option>
          </select>
        </div>
        <button class="btn btn-primary btn-full" onclick="saveProfile()">Salvar Alterações</button>
      </div>
    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast">
  <div class="toast-icon" id="toast-icon"></div>
  <div class="toast-text">
    <div class="toast-title" id="toast-title"></div>
    <div class="toast-sub" id="toast-sub"></div>
  </div>
</div>

<script>
/* =====================================================
   DATA
===================================================== */
const events = [
  {
    id: 1,
    title: "AI Summit Brasil 2025",
    category: "AI",
    badge: "badge-ai",
    badgeLabel: "🤖 IA & ML",
    date: "2025-08-15",
    time: "09:00",
    location: "São Paulo, SP",
    format: "Presencial",
    price: 0,
    spots: 500,
    spotsLeft: 87,
    image: "https://images.unsplash.com/photo-1677442135703-1787eea5ce01?w=800&q=80",
    description: "O maior evento de Inteligência Artificial do Brasil reúne os principais especialistas em IA, Machine Learning, Deep Learning e LLMs do país e do mundo. Palestras técnicas, painéis estratégicos e workshops práticos sobre o futuro da IA.",
    long: "O AI Summit Brasil é o evento mais aguardado do ano para profissionais e entusiastas de Inteligência Artificial. Com mais de 500 participantes esperados, o evento contará com palestrantes internacionais, hackathon de IA, demonstrações ao vivo de modelos generativos, e muito mais. Uma oportunidade única de networking com os maiores nomes da IA no Brasil.",
    tags: ["ChatGPT", "LLMs", "Machine Learning", "Deep Learning", "Python"]
  },
  {
    id: 2,
    title: "Hackathon Inovação Tech",
    category: "dev",
    badge: "badge-dev",
    badgeLabel: "💻 Dev",
    date: "2025-07-20",
    time: "08:00",
    location: "Florianópolis, SC",
    format: "Presencial",
    price: 0,
    spots: 200,
    spotsLeft: 43,
    image: "https://images.unsplash.com/photo-1504384308090-c894fdcc538d?w=800&q=80",
    description: "48 horas de programação intensa com times multidisciplinares desenvolvendo soluções inovadoras para desafios reais. Mentores especialistas, prêmios incríveis e networking com as melhores startups do Sul do Brasil.",
    long: "O Hackathon Inovação Tech reúne desenvolvedores, designers, cientistas de dados e empreendedores para criar soluções em 48 horas. Os times competem em trilhas como: HealthTech, GreenTech, FinTech e EdTech. Com premiação de até R$ 50.000 em dinheiro e aceleração de startups.",
    tags: ["React", "Node.js", "Python", "Startup", "Inovação"]
  },
  {
    id: 3,
    title: "CyberSec Conference 2025",
    category: "security",
    badge: "badge-security",
    badgeLabel: "🔐 Segurança",
    date: "2025-09-05",
    time: "10:00",
    location: "Rio de Janeiro, RJ",
    format: "Híbrido",
    price: 290,
    spots: 300,
    spotsLeft: 125,
    image: "https://images.unsplash.com/photo-1563986768494-4dee2763ff3f?w=800&q=80",
    description: "A conferência de cibersegurança mais relevante do Brasil. Abrange segurança ofensiva e defensiva, pentest, LGPD, resposta a incidentes, threat intelligence e as últimas ameaças globais com especialistas de classe mundial.",
    long: "CyberSec Conference é o evento de referência em segurança da informação no Brasil. Reúne CISOs, analistas de segurança, pentesters e profissionais de compliance para discutir os desafios atuais: ransomware, engenharia social, zero-day exploits, e muito mais. Certificado de participação reconhecido internacionalmente.",
    tags: ["Pentest", "LGPD", "Ransomware", "SOC", "Threat Intel"]
  },
  {
    id: 4,
    title: "Cloud & DevOps Summit",
    category: "cloud",
    badge: "badge-cloud",
    badgeLabel: "☁️ Cloud",
    date: "2025-08-28",
    time: "09:30",
    location: "Belo Horizonte, MG",
    format: "Presencial",
    price: 180,
    spots: 250,
    spotsLeft: 98,
    image: "https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=800&q=80",
    description: "Workshop intensivo sobre arquiteturas cloud-native, Kubernetes, CI/CD, infraestrutura como código com Terraform e as melhores práticas de DevOps para times ágeis em ambientes de alta escala.",
    long: "O Cloud & DevOps Summit é o evento ideal para engenheiros de infraestrutura, SREs e arquitetos de nuvem. Os workshops cobrem AWS, Azure, GCP, Kubernetes, Helm, ArgoCD, GitOps, observabilidade com Grafana e Prometheus. Aprenda com cases reais de empresas como Nubank, iFood e Magazine Luiza.",
    tags: ["AWS", "Kubernetes", "Terraform", "CI/CD", "Docker"]
  },
  {
    id: 5,
    title: "UX/UI Design Week",
    category: "ux",
    badge: "badge-ux",
    badgeLabel: "🎨 UX/UI",
    date: "2025-07-10",
    time: "14:00",
    location: "Online",
    format: "Online",
    price: 0,
    spots: 1000,
    spotsLeft: 412,
    image: "https://images.unsplash.com/photo-1561070791-2526d30994b5?w=800&q=80",
    description: "Uma semana inteira dedicada ao design de produtos digitais. Figma, design systems, pesquisa com usuários, motion design, acessibilidade e as tendências de UX/UI para 2025 com designers das maiores empresas tech.",
    long: "UX/UI Design Week é uma imersão de 5 dias 100% online com palestras, workshops e mentoria ao vivo. Aprenda com designers do Google, Meta, Spotify e startups nacionais. Temas: Figma avançado, design tokens, acessibilidade WCAG, protótipos interativos, e como estruturar um portfólio que converte.",
    tags: ["Figma", "Design System", "Pesquisa", "Acessibilidade", "Motion"]
  },
  {
    id: 6,
    title: "Web3 & Blockchain Forum",
    category: "web3",
    badge: "badge-web3",
    badgeLabel: "🌐 Web3",
    date: "2025-10-18",
    time: "10:00",
    location: "São Paulo, SP",
    format: "Presencial",
    price: 350,
    spots: 400,
    spotsLeft: 201,
    image: "https://images.unsplash.com/photo-1639762681057-408e52192e55?w=800&q=80",
    description: "O maior fórum de Web3, DeFi, NFTs e blockchain do Brasil. Explore smart contracts, tokenização de ativos reais, DAOs, DeFi e o ecossistema cripto com especialistas, investidores e empreendedores do setor.",
    long: "Web3 & Blockchain Forum conecta desenvolvedores Solidity, investidores cripto, empreendedores Web3 e entusiastas de blockchain. O evento aborda Ethereum, Solana, Polkadot, DeFi protocols, Layer 2 solutions, tokenização de ativos e regulação cripto no Brasil. Painéis de debate com especialistas internacionais.",
    tags: ["Ethereum", "Solidity", "DeFi", "NFT", "DAO"]
  },
  {
    id: 7,
    title: "React & Next.js Conference",
    category: "dev",
    badge: "badge-dev",
    badgeLabel: "💻 Dev",
    date: "2025-09-22",
    time: "09:00",
    location: "Online",
    format: "Online",
    price: 0,
    spots: 800,
    spotsLeft: 320,
    image: "https://images.unsplash.com/photo-1587620962725-abab7fe55159?w=800&q=80",
    description: "Conferência dedicada ao ecossistema React e Next.js com foco em Server Components, App Router, performance, testes e as novidades do framework que domina o desenvolvimento front-end moderno.",
    long: "React & Next.js Conference traz os principais contribuidores do ecossistema para discutir o estado da arte do desenvolvimento front-end. Tópicos: React 19, Server Actions, Suspense, streaming SSR, Turbopack, Edge Runtime, testing com Vitest e muito mais. Evento 100% online e gratuito.",
    tags: ["React", "Next.js", "TypeScript", "Tailwind", "Frontend"]
  },
  {
    id: 8,
    title: "Data Science & Analytics World",
    category: "AI",
    badge: "badge-ai",
    badgeLabel: "🤖 IA & ML",
    date: "2025-11-07",
    time: "08:30",
    location: "Curitiba, PR",
    format: "Híbrido",
    price: 220,
    spots: 350,
    spotsLeft: 178,
    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&q=80",
    description: "O evento de referência em Data Science, Analytics e BI no Sul do Brasil. Python, R, Pandas, Spark, pipelines de dados, visualização com Power BI e Tableau, e modelagem preditiva com especialistas do mercado.",
    long: "Data Science & Analytics World reúne cientistas de dados, analistas de BI, engenheiros de dados e líderes de negócios para explorar como os dados transformam empresas. Cases reais de empresas como Ambev, Localiza, RD Station. Workshops hands-on com Python, SQL, dbt, Airflow e ferramentas de visualização modernas.",
    tags: ["Python", "Pandas", "Spark", "Power BI", "ML"]
  }
];

/* =====================================================
   STATE
===================================================== */
let currentUser = JSON.parse(localStorage.getItem('tp_user') || 'null');
let registrations = JSON.parse(localStorage.getItem('tp_registrations') || '[]');
let users = JSON.parse(localStorage.getItem('tp_users') || '[]');
let activeCategory = 'all';
let countdownInterval = null;
let currentEventId = null;

/* =====================================================
   INIT
===================================================== */
window.addEventListener('DOMContentLoaded', () => {
  renderEvents(events);
  updateNavAuth();
  document.addEventListener('click', (e) => {
    const menu = document.getElementById('user-menu');
    const avatar = document.getElementById('user-avatar');
    if (menu && avatar && !menu.contains(e.target) && !avatar.contains(e.target)) {
      menu.classList.remove('open');
    }
  });
  document.querySelectorAll('.modal-overlay').forEach(m => {
    m.addEventListener('click', (e) => {
      if (e.target === m) closeModal(m.id);
    });
  });
});

/* =====================================================
   RENDER EVENTS
===================================================== */
function renderEvents(data) {
  const grid = document.getElementById('events-grid');
  const count = document.getElementById('results-count');

  if (data.length === 0) {
    grid.innerHTML = `<div class="no-results"><div class="emoji">🔭</div><h3>Nenhum evento encontrado</h3><p>Tente ajustar os filtros ou a busca.</p></div>`;
    count.innerHTML = `<span>0</span> eventos encontrados`;
    return;
  }

  count.innerHTML = `<span>${data.length}</span> evento${data.length !== 1 ? 's' : ''} encontrado${data.length !== 1 ? 's' : ''}`;

  grid.innerHTML = data.map((e, i) => {
    const spotsPercent = Math.round(((e.spots - e.spotsLeft) / e.spots) * 100);
    const isFull = e.spotsLeft <= 0;
    const dateStr = formatDate(e.date);
    return `
    <div class="event-card" onclick="openEvent(${e.id})" style="animation-delay:${i * 0.07}s">
      <div class="event-img-wrap">
        <img class="event-image" src="${e.image}" alt="${e.title}" loading="lazy">
        <div class="event-category-badge ${e.badge}">${e.badgeLabel}</div>
      </div>
      <div class="event-body">
        <div class="event-meta">
          <span class="event-meta-item">📅 ${dateStr}</span>
          <span class="event-meta-item">📍 ${e.format}</span>
        </div>
        <h3 class="event-title">${e.title}</h3>
        <p class="event-desc">${e.description}</p>
        <div class="event-footer">
          <div>
            <div class="event-price ${e.price > 0 ? 'paid' : ''}">${e.price === 0 ? 'Gratuito' : 'R$ ' + e.price}</div>
            <div class="event-spots">${isFull ? '🔴 Esgotado' : `${e.spotsLeft} vagas restantes`}</div>
            <div class="spots-bar"><div class="spots-fill" style="width:${spotsPercent}%"></div></div>
          </div>
          <button class="btn btn-outline" style="font-size:0.8rem;padding:0.45rem 1rem;" onclick="event.stopPropagation();openEvent(${e.id})">
            ${isFull ? 'Ver mais' : 'Inscrever-se'}
          </button>
        </div>
      </div>
    </div>`;
  }).join('');
}

function formatDate(dateStr) {
  const d = new Date(dateStr + 'T12:00:00');
  return d.toLocaleDateString('pt-BR', { day: '2-digit', month: 'short', year: 'numeric' });
}

/* =====================================================
   FILTER LOGIC
===================================================== */
function filterEvents() {
  const q = document.getElementById('search-input').value.toLowerCase().trim();
  const dateVal = document.getElementById('date-input').value;

  let filtered = events.filter(e => {
    const matchText = !q || e.title.toLowerCase().includes(q) || e.description.toLowerCase().includes(q) || e.tags.some(t => t.toLowerCase().includes(q));
    const matchDate = !dateVal || e.date === dateVal;
    const matchCat = activeCategory === 'all' || activeCategory === 'free'
      ? (activeCategory === 'free' ? e.price === 0 : true)
      : e.category === activeCategory;
    return matchText && matchDate && matchCat;
  });

  renderEvents(filtered);
}

function setCategory(cat, el) {
  activeCategory = cat;
  document.querySelectorAll('.chip').forEach(c => c.classList.remove('active'));
  el.classList.add('active');
  filterEvents();
}

function clearFilters() {
  document.getElementById('search-input').value = '';
  document.getElementById('date-input').value = '';
  activeCategory = 'all';
  document.querySelectorAll('.chip').forEach((c, i) => c.classList.toggle('active', i === 0));
  filterEvents();
}

/* =====================================================
   VIEW TOGGLE
===================================================== */
function setView(view) {
  const grid = document.getElementById('events-grid');
  const gridBtn = document.getElementById('grid-btn');
  const listBtn = document.getElementById('list-btn');
  if (view === 'list') {
    grid.classList.add('list-view');
    listBtn.classList.add('active');
    gridBtn.classList.remove('active');
  } else {
    grid.classList.remove('list-view');
    gridBtn.classList.add('active');
    listBtn.classList.remove('active');
  }
}

/* =====================================================
   EVENT DETAIL MODAL
===================================================== */
function openEvent(id) {
  const e = events.find(ev => ev.id === id);
  if (!e) return;
  currentEventId = id;

  document.getElementById('modal-img').src = e.image;
  document.getElementById('modal-img').alt = e.title;
  document.getElementById('modal-badge').innerHTML = `<div class="event-category-badge ${e.badge}" style="display:inline-block;margin-bottom:0.75rem;">${e.badgeLabel}</div>`;
  document.getElementById('modal-title').textContent = e.title;
  document.getElementById('modal-desc').textContent = e.long;

  document.getElementById('modal-details').innerHTML = `
    <div class="modal-detail"><div class="modal-detail-label">📅 Data</div><div class="modal-detail-value">${formatDate(e.date)} · ${e.time}h</div></div>
    <div class="modal-detail"><div class="modal-detail-label">📍 Local</div><div class="modal-detail-value">${e.location}</div></div>
    <div class="modal-detail"><div class="modal-detail-label">💻 Formato</div><div class="modal-detail-value">${e.format}</div></div>
    <div class="modal-detail"><div class="modal-detail-label">🎟 Vagas</div><div class="modal-detail-value">${e.spotsLeft > 0 ? e.spotsLeft + ' disponíveis' : '🔴 Esgotado'}</div></div>
    <div class="modal-detail"><div class="modal-detail-label">💰 Valor</div><div class="modal-detail-value" style="color:${e.price===0?'var(--green)':'var(--cyan)'};">${e.price === 0 ? 'Gratuito' : 'R$ ' + e.price}</div></div>
    <div class="modal-detail"><div class="modal-detail-label">🏷 Tags</div><div class="modal-detail-value" style="font-size:0.8rem;">${e.tags.slice(0,3).join(' · ')}</div></div>
  `;

  startCountdown(e.date, e.time);
  renderModalAction(e);
  openModal('event-modal');
}

function renderModalAction(e) {
  const isRegistered = currentUser && registrations.some(r => r.eventId === e.id && r.userId === currentUser.email);
  const isFull = e.spotsLeft <= 0;

  if (isRegistered) {
    const reg = registrations.find(r => r.eventId === e.id && r.userId === currentUser.email);
    document.getElementById('modal-action').innerHTML = `
      <div class="ticket-card">
        <div class="ticket-id">Ingresso confirmado · TKT-${reg.ticketCode}</div>
        <div class="ticket-code">${reg.ticketCode}</div>
        <div style="margin-top:0.75rem;font-size:0.82rem;color:var(--text-muted);">Apresente este código na entrada do evento</div>
      </div>
      <div style="margin-top:1rem;display:flex;gap:1rem;flex-wrap:wrap;">
        <button class="btn btn-danger" onclick="cancelRegistration(${e.id})" style="flex:1;justify-content:center;">Cancelar inscrição</button>
      </div>
    `;
  } else if (isFull) {
    document.getElementById('modal-action').innerHTML = `
      <button class="btn btn-ghost btn-full" disabled style="opacity:0.5;cursor:not-allowed;">🔴 Vagas Esgotadas</button>
    `;
  } else {
    document.getElementById('modal-action').innerHTML = `
      <button class="btn btn-primary btn-full" onclick="registerForEvent(${e.id})" style="padding:0.9rem;font-size:1rem;">
        ${currentUser ? '🎟 Confirmar Inscrição' : '🔐 Entre para se inscrever'}
      </button>
    `;
  }
}

function startCountdown(dateStr, timeStr) {
  if (countdownInterval) clearInterval(countdownInterval);
  const target = new Date(`${dateStr}T${timeStr}:00`);

  function update() {
    const now = new Date();
    const diff = target - now;
    if (diff <= 0) {
      document.getElementById('countdown-digits').innerHTML = `<span style="-webkit-text-fill-color:var(--text-muted);font-size:1rem;">Evento encerrado</span>`;
      clearInterval(countdownInterval);
      return;
    }
    const d = Math.floor(diff / 86400000);
    const h = Math.floor((diff % 86400000) / 3600000);
    const m = Math.floor((diff % 3600000) / 60000);
    const s = Math.floor((diff % 60000) / 1000);
    document.getElementById('countdown-digits').innerHTML = `
      <div class="countdown-unit"><span>${String(d).padStart(2,'0')}</span><small>dias</small></div>
      <span class="countdown-sep">:</span>
      <div class="countdown-unit"><span>${String(h).padStart(2,'0')}</span><small>horas</small></div>
      <span class="countdown-sep">:</span>
      <div class="countdown-unit"><span>${String(m).padStart(2,'0')}</span><small>min</small></div>
      <span class="countdown-sep">:</span>
      <div class="countdown-unit"><span>${String(s).padStart(2,'0')}</span><small>seg</small></div>
    `;
  }
  update();
  countdownInterval = setInterval(update, 1000);
}

/* =====================================================
   REGISTER FOR EVENT
===================================================== */
function registerForEvent(eventId) {
  if (!currentUser) {
    closeModal('event-modal');
    openAuth('login');
    showToast('info', '🔐 Acesso necessário', 'Faça login para se inscrever');
    return;
  }

  const e = events.find(ev => ev.id === eventId);
  if (!e || e.spotsLeft <= 0) return;

  const code = generateCode();
  registrations.push({ eventId, userId: currentUser.email, ticketCode: code, date: new Date().toISOString(), eventTitle: e.title, eventDate: e.date });
  e.spotsLeft--;
  localStorage.setItem('tp_registrations', JSON.stringify(registrations));

  renderModalAction(e);
  renderEvents(applyCurrentFilters());
  showToast('success', '🎉 Inscrição confirmada!', `Ticket: ${code}`);
}

function cancelRegistration(eventId) {
  if (!currentUser) return;
  const idx = registrations.findIndex(r => r.eventId === eventId && r.userId === currentUser.email);
  if (idx === -1) return;
  registrations.splice(idx, 1);
  const e = events.find(ev => ev.id === eventId);
  if (e) e.spotsLeft++;
  localStorage.setItem('tp_registrations', JSON.stringify(registrations));
  renderModalAction(e);
  renderEvents(applyCurrentFilters());
  showToast('info', 'Inscrição cancelada', 'Você pode se inscrever novamente');
}

function generateCode() {
  const chars = 'ABCDEFGHJKLMNPQRSTUVWXYZ23456789';
  return Array.from({length: 8}, () => chars[Math.floor(Math.random() * chars.length)]).join('');
}

function applyCurrentFilters() {
  const q = document.getElementById('search-input').value.toLowerCase().trim();
  const dateVal = document.getElementById('date-input').value;
  return events.filter(e => {
    const matchText = !q || e.title.toLowerCase().includes(q) || e.description.toLowerCase().includes(q) || e.tags.some(t => t.toLowerCase().includes(q));
    const matchDate = !dateVal || e.date === dateVal;
    const matchCat = activeCategory === 'all' ? true : (activeCategory === 'free' ? e.price === 0 : e.category === activeCategory);
    return matchText && matchDate && matchCat;
  });
}

/* =====================================================
   AUTH
===================================================== */
function openAuth(tab) {
  switchTab(tab);
  openModal('auth-modal');
}

function switchTab(tab) {
  document.getElementById('login-form').style.display = tab === 'login' ? 'block' : 'none';
  document.getElementById('register-form').style.display = tab === 'register' ? 'block' : 'none';
  document.getElementById('tab-login').classList.toggle('active', tab === 'login');
  document.getElementById('tab-register').classList.toggle('active', tab === 'register');
}

function doLogin() {
  const email = document.getElementById('login-email').value.trim();
  const pass = document.getElementById('login-pass').value;
  if (!email || !pass) { showToast('error', 'Campos obrigatórios', 'Preencha e-mail e senha'); return; }
  const user = users.find(u => u.email === email && u.pass === pass);
  if (!user) { showToast('error', 'Credenciais inválidas', 'E-mail ou senha incorretos'); return; }
  currentUser = user;
  localStorage.setItem('tp_user', JSON.stringify(currentUser));
  updateNavAuth();
  closeModal('auth-modal');
  showToast('success', `Bem-vindo, ${user.name}!`, 'Login realizado com sucesso');
}

function doRegister() {
  const name = document.getElementById('reg-name').value.trim();
  const last = document.getElementById('reg-last').value.trim();
  const email = document.getElementById('reg-email').value.trim();
  const area = document.getElementById('reg-area').value;
  const pass = document.getElementById('reg-pass').value;
  const terms = document.getElementById('reg-terms').checked;

  if (!name || !last || !email || !pass) { showToast('error', 'Campos obrigatórios', 'Preencha todos os campos'); return; }
  if (pass.length < 6) { showToast('error', 'Senha muito curta', 'Mínimo 6 caracteres'); return; }
  if (!terms) { showToast('error', 'Aceite os termos', 'É necessário aceitar os termos de uso'); return; }
  if (users.find(u => u.email === email)) { showToast('error', 'E-mail já cadastrado', 'Tente fazer login'); return; }

  const user = { name, last, email, area, pass };
  users.push(user);
  localStorage.setItem('tp_users', JSON.stringify(users));
  currentUser = user;
  localStorage.setItem('tp_user', JSON.stringify(currentUser));
  updateNavAuth();
  closeModal('auth-modal');
  showToast('success', '🚀 Conta criada!', `Bem-vindo à TechPulse, ${name}!`);
}

function logout() {
  currentUser = null;
  localStorage.removeItem('tp_user');
  updateNavAuth();
  document.getElementById('user-menu').classList.remove('open');
  showToast('info', 'Até logo!', 'Você saiu da sua conta');
}

function updateNavAuth() {
  const authBtns = document.getElementById('nav-auth-btns');
  const userWrap = document.getElementById('nav-user-wrap');
  if (currentUser) {
    authBtns.style.display = 'none';
    userWrap.style.display = 'block';
    const initials = (currentUser.name[0] + (currentUser.last ? currentUser.last[0] : '')).toUpperCase();
    document.getElementById('user-avatar').textContent = initials;
    document.getElementById('menu-name').textContent = `${currentUser.name} ${currentUser.last || ''}`;
    document.getElementById('menu-email').textContent = currentUser.email;
  } else {
    authBtns.style.display = 'flex';
    userWrap.style.display = 'none';
  }
}

function toggleUserMenu() {
  document.getElementById('user-menu').classList.toggle('open');
}

/* =====================================================
   MY REGISTRATIONS
===================================================== */
function openMyRegistrations() {
  document.getElementById('user-menu').classList.remove('open');
  const myRegs = registrations.filter(r => r.userId === currentUser.email);
  const list = document.getElementById('my-registrations-list');
  if (myRegs.length === 0) {
    list.innerHTML = `<div style="text-align:center;padding:3rem;color:var(--text-muted);">
      <div style="font-size:2.5rem;margin-bottom:1rem;">🎟</div>
      <div style="font-family:var(--font-display);font-size:1.2rem;color:var(--text-secondary);margin-bottom:0.5rem;">Nenhuma inscrição ainda</div>
      <div style="font-size:0.875rem;">Explore os eventos e inscreva-se!</div>
    </div>`;
  } else {
    list.innerHTML = `<div class="registrations-list">${myRegs.map(r => {
      const e = events.find(ev => ev.id === r.eventId);
      return `<div class="reg-item">
        <div class="reg-info">
          <div class="reg-title">${r.eventTitle}</div>
          <div class="reg-meta">📅 ${formatDate(r.eventDate)} · 🎟 TKT-${r.ticketCode}</div>
        </div>
        <div style="display:flex;flex-direction:column;align-items:flex-end;gap:0.5rem;">
          <div class="reg-status confirmed">Confirmado</div>
          <button class="btn btn-danger" style="font-size:0.75rem;padding:0.35rem 0.8rem;" onclick="cancelRegistration(${r.eventId});openMyRegistrations();">Cancelar</button>
        </div>
      </div>`;
    }).join('')}</div>`;
  }
  openModal('reg-modal');
}

/* =====================================================
   EDIT PROFILE
===================================================== */
function openEditProfile() {
  document.getElementById('user-menu').classList.remove('open');
  if (!currentUser) return;
  document.getElementById('edit-name').value = currentUser.name || '';
  document.getElementById('edit-last').value = currentUser.last || '';
  document.getElementById('edit-email').value = currentUser.email || '';
  document.getElementById('edit-area').value = currentUser.area || '';
  openModal('profile-modal');
}

function saveProfile() {
  const name = document.getElementById('edit-name').value.trim();
  const last = document.getElementById('edit-last').value.trim();
  const email = document.getElementById('edit-email').value.trim();
  const area = document.getElementById('edit-area').value;
  if (!name || !email) { showToast('error', 'Campos obrigatórios', 'Nome e e-mail são obrigatórios'); return; }
  const oldEmail = currentUser.email;
  currentUser = { ...currentUser, name, last, email, area };
  const idx = users.findIndex(u => u.email === oldEmail);
  if (idx > -1) users[idx] = currentUser;
  localStorage.setItem('tp_users', JSON.stringify(users));
  localStorage.setItem('tp_user', JSON.stringify(currentUser));
  updateNavAuth();
  closeModal('profile-modal');
  showToast('success', 'Perfil atualizado!', 'Suas informações foram salvas');
}

/* =====================================================
   NEWSLETTER
===================================================== */
function subscribeNewsletter() {
  const email = document.getElementById('nl-email').value.trim();
  if (!email || !email.includes('@')) { showToast('error', 'E-mail inválido', 'Insira um e-mail válido'); return; }
  document.getElementById('nl-email').value = '';
  showToast('success', '📧 Inscrito!', 'Você receberá novidades em breve');
}

/* =====================================================
   MODALS
===================================================== */
function openModal(id) {
  document.getElementById(id).classList.add('open');
  document.body.style.overflow = 'hidden';
}

function closeModal(id) {
  document.getElementById(id).classList.remove('open');
  document.body.style.overflow = '';
  if (id === 'event-modal' && countdownInterval) {
    clearInterval(countdownInterval);
    countdownInterval = null;
  }
}

document.addEventListener('keydown', (e) => {
  if (e.key === 'Escape') {
    document.querySelectorAll('.modal-overlay.open').forEach(m => closeModal(m.id));
  }
});

/* =====================================================
   TOAST
===================================================== */
let toastTimeout;
function showToast(type, title, sub) {
  const toast = document.getElementById('toast');
  const icons = { success: '✅', error: '❌', info: 'ℹ️' };
  document.getElementById('toast-icon').textContent = icons[type] || 'ℹ️';
  document.getElementById('toast-title').textContent = title;
  document.getElementById('toast-sub').textContent = sub;
  toast.className = `toast ${type} show`;
  clearTimeout(toastTimeout);
  toastTimeout = setTimeout(() => { toast.classList.remove('show'); }, 4000);
}

/* =====================================================
   HELPERS
===================================================== */
function scrollTo(id) {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth', block: 'start' });
}
function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' });
}
</script>
</body>
</html>
