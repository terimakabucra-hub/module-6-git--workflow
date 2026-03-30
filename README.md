<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Glassmorphism Landing Page</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Inter", "Segoe UI", sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      color: #fff;
      background:
        radial-gradient(circle at top left, rgba(0, 255, 200, 0.18), transparent 30%),
        radial-gradient(circle at top right, rgba(140, 82, 255, 0.22), transparent 30%),
        radial-gradient(circle at bottom center, rgba(0, 140, 255, 0.18), transparent 35%),
        linear-gradient(135deg, #07111f, #0b1b34 45%, #071426 100%);
      min-height: 100vh;
      overflow-x: hidden;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .container {
      width: 90%;
      max-width: 1200px;
      margin: auto;
    }

    .glass {
      background: rgba(255, 255, 255, 0.08);
      border: 1px solid rgba(255, 255, 255, 0.15);
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.25);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
    }

    .blob {
      position: fixed;
      border-radius: 50%;
      filter: blur(70px);
      z-index: -1;
      opacity: 0.5;
    }

    .blob-1 {
      width: 260px;
      height: 260px;
      background: #00ffd5;
      top: 80px;
      left: -60px;
    }

    .blob-2 {
      width: 320px;
      height: 320px;
      background: #8c52ff;
      top: 100px;
      right: -80px;
    }

    .blob-3 {
      width: 260px;
      height: 260px;
      background: #00a6ff;
      bottom: 40px;
      left: 35%;
    }

    /* Navbar */
    .navbar {
      position: sticky;
      top: 20px;
      z-index: 1000;
      padding-top: 20px;
    }

    .nav-wrap {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 16px 24px;
      border-radius: 18px;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 800;
      letter-spacing: 0.5px;
    }

    .logo span {
      background: linear-gradient(90deg, #00ffd5, #8c52ff, #00a6ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .nav-links {
      display: flex;
      gap: 24px;
      align-items: center;
    }

    .nav-links a {
      color: rgba(255, 255, 255, 0.85);
      font-weight: 500;
      transition: 0.3s ease;
    }

    .nav-links a:hover {
      color: #ffffff;
    }

    .btn {
      display: inline-block;
      padding: 12px 22px;
      border-radius: 14px;
      font-weight: 700;
      transition: all 0.35s ease;
    }

    .btn-primary {
      background: linear-gradient(135deg, rgba(0,255,213,0.9), rgba(0,166,255,0.9));
      color: #04111f;
      box-shadow: 0 10px 25px rgba(0, 255, 213, 0.22);
    }

    .btn-primary:hover {
      transform: translateY(-3px) scale(1.02);
      box-shadow: 0 14px 30px rgba(0, 255, 213, 0.32);
    }

    .btn-outline {
      background: rgba(255,255,255,0.06);
      border: 1px solid rgba(255,255,255,0.18);
      color: #fff;
    }

    .btn-outline:hover {
      background: rgba(255,255,255,0.12);
      transform: translateY(-3px);
    }

    /* Hero */
    .hero {
      padding: 90px 0 70px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 30px;
      align-items: center;
    }

    .hero-text h1 {
      font-size: 3.7rem;
      line-height: 1.1;
      margin-bottom: 22px;
      font-weight: 900;
    }

    .hero-text h1 span {
      background: linear-gradient(90deg, #ffffff, #b8fff4, #b8d5ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .hero-text p {
      color: rgba(255,255,255,0.78);
      font-size: 1.07rem;
      max-width: 650px;
      margin-bottom: 28px;
    }

    .hero-buttons {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
      margin-bottom: 28px;
    }

    .mini-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    .mini-badges span {
      padding: 10px 14px;
      border-radius: 999px;
      font-size: 0.92rem;
      color: rgba(255,255,255,0.92);
      background: rgba(255,255,255,0.08);
      border: 1px solid rgba(255,255,255,0.12);
      backdrop-filter: blur(12px);
    }

    .hero-panel {
      padding: 24px;
      border-radius: 28px;
      position: relative;
    }

    .dashboard-card {
      border-radius: 22px;
      padding: 22px;
      margin-bottom: 18px;
    }

    .dashboard-card h3 {
      font-size: 1.1rem;
      margin-bottom: 10px;
    }

    .dashboard-card p {
      color: rgba(255,255,255,0.72);
      font-size: 0.95rem;
      margin-bottom: 18px;
    }

    .progress-box {
      display: flex;
      justify-content: space-between;
      margin-bottom: 12px;
      color: rgba(255,255,255,0.85);
      font-size: 0.95rem;
    }

    .progress {
      width: 100%;
      height: 10px;
      border-radius: 999px;
      background: rgba(255,255,255,0.08);
      overflow: hidden;
    }

    .progress-bar {
      width: 82%;
      height: 100%;
      background: linear-gradient(90deg, #00ffd5, #00a6ff);
      border-radius: 999px;
    }

    .small-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
    }

    .small-card {
      padding: 18px;
      border-radius: 18px;
      text-align: center;
    }

    .small-card h4 {
      font-size: 1.5rem;
      margin-bottom: 6px;
      color: #fff;
    }

    .small-card p {
      font-size: 0.9rem;
      color: rgba(255,255,255,0.7);
    }

    /* Section */
    section {
      padding: 45px 0;
    }

    .section-title {
      text-align: center;
      font-size: 2.3rem;
      margin-bottom: 14px;
      font-weight: 800;
    }

    .section-subtitle {
      text-align: center;
      max-width: 760px;
      margin: 0 auto 40px;
      color: rgba(255,255,255,0.72);
    }

    /* Features */
    .feature-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
    }

    .feature-card {
      padding: 26px;
      border-radius: 24px;
      transition: 0.35s ease;
      position: relative;
      overflow: hidden;
    }

    .feature-card::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(255,255,255,0.06), rgba(255,255,255,0.01));
      pointer-events: none;
    }

    .feature-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 20px 45px rgba(0,0,0,0.24);
    }

    .icon {
      width: 56px;
      height: 56px;
      border-radius: 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5rem;
      margin-bottom: 18px;
      background: linear-gradient(135deg, rgba(0,255,213,0.18), rgba(140,82,255,0.18));
      border: 1px solid rgba(255,255,255,0.16);
    }

    .feature-card h3 {
      margin-bottom: 12px;
      font-size: 1.18rem;
    }

    .feature-card p {
      color: rgba(255,255,255,0.72);
      font-size: 0.96rem;
    }

    /* Stats */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 22px;
    }

    .stat-card {
      text-align: center;
      padding: 28px 20px;
      border-radius: 22px;
    }

    .stat-card h2 {
      font-size: 2.2rem;
      margin-bottom: 8px;
      background: linear-gradient(90deg, #00ffd5, #8c52ff, #00a6ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .stat-card p {
      color: rgba(255,255,255,0.72);
    }

    /* CTA */
    .cta-box {
      padding: 40px;
      border-radius: 30px;
      text-align: center;
    }

    .cta-box h2 {
      font-size: 2.3rem;
      margin-bottom: 14px;
    }

    .cta-box p {
      max-width: 760px;
      margin: 0 auto 24px;
      color: rgba(255,255,255,0.75);
    }

    /* Footer */
    .footer {
      padding: 20px 0 40px;
      text-align: center;
      color: rgba(255,255,255,0.58);
      font-size: 0.95rem;
    }

    /* Responsive */
    @media (max-width: 992px) {
      .hero-grid,
      .feature-grid,
      .stats-grid {
        grid-template-columns: 1fr 1fr;
      }

      .hero-text h1 {
        font-size: 3rem;
      }
    }

    @media (max-width: 768px) {
      .nav-wrap {
        flex-direction: column;
        gap: 14px;
      }

      .nav-links {
        flex-wrap: wrap;
        justify-content: center;
      }

      .hero-grid,
      .feature-grid,
      .stats-grid,
      .small-grid {
        grid-template-columns: 1fr;
      }

      .hero-text h1 {
        font-size: 2.3rem;
      }

      .section-title,
      .cta-box h2 {
        font-size: 1.8rem;
      }

      .hero {
        padding-top: 60px;
      }
    }
  </style>
</head>
<body>

  <div class="blob blob-1"></div>
  <div class="blob blob-2"></div>
  <div class="blob blob-3"></div>

  <!-- Navbar -->
  <div class="navbar">
    <div class="container">
      <div class="nav-wrap glass">
        <div class="logo">Glass<span>Flow</span></div>
        <div class="nav-links">
          <a href="#home">Home</a>
          <a href="#features">Features</a>
          <a href="#stats">Stats</a>
          <a href="#contact">Contact</a>
          <a href="#" class="btn btn-primary">Launch Project</a>
        </div>
      </div>
    </div>
  </div>

  <!-- Hero -->
  <section class="hero" id="home">
    <div class="container hero-grid">
      <div class="hero-text">
        <h1>Build an <span>ultra modern</span> landing page with stunning glass UI.</h1>
        <p>
          A next-level glassmorphism design for your Git & GitHub assignment project.
          Clean layout, premium visuals, modern gradients, and a fully responsive structure
          that makes your repository look much more professional.
        </p>

        <div class="hero-buttons">
          <a href="#features" class="btn btn-primary">Explore Design</a>
          <a href="#contact" class="btn btn-outline">Get Started</a>
        </div>

        <div class="mini-badges">
          <span>✨ Glassmorphism UI</span>
          <span>🚀 Premium Landing Page</span>
          <span>📱 Fully Responsive</span>
        </div>
      </div>

      <div class="hero-panel glass">
        <div class="dashboard-card glass">
          <h3>Project Dashboard</h3>
          <p>Your workflow is looking clean, polished, and production-ready.</p>

          <div class="progress-box">
            <span>Project Completion</span>
            <span>82%</span>
          </div>
          <div class="progress">
            <div class="progress-bar"></div>
          </div>
        </div>

        <div class="small-grid">
          <div class="small-card glass">
            <h4>12+</h4>
            <p>Commits Added</p>
          </div>
          <div class="small-card glass">
            <h4>03</h4>
            <p>Branches Used</p>
          </div>
          <div class="small-card glass">
            <h4>01</h4>
            <p>Conflict Solved</p>
          </div>
          <div class="small-card glass">
            <h4>100%</h4>
            <p>GitHub Synced</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Features -->
  <section id="features">
    <div class="container">
      <h2 class="section-title">Why this design feels premium</h2>
      <p class="section-subtitle">
        This layout combines futuristic glass surfaces, soft blur layers, vibrant gradients,
        and clean spacing to create a high-end modern landing page experience.
      </p>

      <div class="feature-grid">
        <div class="feature-card glass">
          <div class="icon">💎</div>
          <h3>Glassmorphism Interface</h3>
          <p>
            Transparent surfaces, subtle borders, and layered blur effects create a
            modern premium visual identity.
          </p>
        </div>

        <div class="feature-card glass">
          <div class="icon">⚡</div>
          <h3>Fast & Clean Layout</h3>
          <p>
            Structured sections with strong hierarchy make the content easy to read
            and visually impressive.
          </p>
        </div>

        <div class="feature-card glass">
          <div class="icon">🎯</div>
          <h3>Assignment Ready</h3>
          <p>
            Perfect for showing your project in a cleaner way before committing,
            branching, and pushing to GitHub.
          </p>
        </div>

        <div class="feature-card glass">
          <div class="icon">🌈</div>
          <h3>Gradient Visual System</h3>
          <p>
            Bright neon-style gradients add a futuristic vibe without making the
            design feel messy.
          </p>
        </div>

        <div class="feature-card glass">
          <div class="icon">🧠</div>
          <h3>Professional Feel</h3>
          <p>
            The overall UI looks like a startup SaaS homepage, which makes your
            simple project look more polished.
          </p>
        </div>

        <div class="feature-card glass">
          <div class="icon">📱</div>
          <h3>Responsive Design</h3>
          <p>
            The layout automatically adjusts for laptop, tablet, and mobile screens
            so it stays beautiful everywhere.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Stats -->
  <section id="stats">
    <div class="container">
      <h2 class="section-title">Workflow at a glance</h2>
      <p class="section-subtitle">
        A simple but stylish way to visually represent your Git workflow progress.
      </p>

      <div class="stats-grid">
        <div class="stat-card glass">
          <h2>15+</h2>
          <p>Git Commands Used</p>
        </div>
        <div class="stat-card glass">
          <h2>5</h2>
          <p>Meaningful Commits</p>
        </div>
        <div class="stat-card glass">
          <h2>2</h2>
          <p>Merged Branches</p>
        </div>
        <div class="stat-card glass">
          <h2>1</h2>
          <p>Pull Request Done</p>
        </div>
      </div>
    </div>
  </section>

  <!-- CTA -->
  <section id="contact">
    <div class="container">
      <div class="cta-box glass">
        <h2>Ready to push this to GitHub?</h2>
        <p>
          Use this page as your final project homepage, then commit it with a meaningful
          message and publish your repository publicly for submission.
        </p>
        <a href="#" class="btn btn-primary">Publish Project</a>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <div class="footer">
    <div class="container">
      <p>© 2025 GlassFlow. Designed for your Git & GitHub workflow project.</p>
    </div>
  </div>
 
 
</body> 
</html>

