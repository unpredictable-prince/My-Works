<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>README — Data Scientist & ML Engineer</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #0a0a0f;
      --surface: #111118;
      --border: #1e1e2e;
      --accent: #00f5a0;
      --accent2: #00c9ff;
      --muted: #444466;
      --text: #e0e0f0;
      --text-dim: #8888aa;
      --mono: 'Space Mono', monospace;
      --display: 'Syne', sans-serif;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--mono);
      font-size: 14px;
      line-height: 1.7;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* Grid overlay */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,245,160,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,245,160,0.03) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
      z-index: 0;
    }

    .container {
      max-width: 860px;
      margin: 0 auto;
      padding: 60px 32px 100px;
      position: relative;
      z-index: 1;
    }

    /* ── HEADER ── */
    .header {
      border-left: 3px solid var(--accent);
      padding-left: 24px;
      margin-bottom: 64px;
      animation: fadeUp 0.7s ease both;
    }

    .badge {
      display: inline-block;
      font-family: var(--mono);
      font-size: 11px;
      letter-spacing: 0.15em;
      color: var(--accent);
      text-transform: uppercase;
      margin-bottom: 12px;
      opacity: 0.8;
    }

    .badge::before { content: '> '; }

    h1 {
      font-family: var(--display);
      font-size: clamp(2.4rem, 6vw, 4rem);
      font-weight: 800;
      line-height: 1.05;
      letter-spacing: -0.02em;
      color: #fff;
      margin-bottom: 8px;
    }

    .tagline {
      font-family: var(--mono);
      color: var(--text-dim);
      font-size: 13px;
      margin-top: 14px;
      max-width: 520px;
    }

    .tagline span { color: var(--accent2); }

    /* ── SECTION ── */
    section {
      margin-bottom: 56px;
      animation: fadeUp 0.7s ease both;
    }

    section:nth-child(2) { animation-delay: 0.1s; }
    section:nth-child(3) { animation-delay: 0.2s; }
    section:nth-child(4) { animation-delay: 0.3s; }
    section:nth-child(5) { animation-delay: 0.4s; }

    .section-label {
      font-family: var(--mono);
      font-size: 10px;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 20px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    h2 {
      font-family: var(--display);
      font-size: 1.5rem;
      font-weight: 700;
      color: #fff;
      margin-bottom: 16px;
    }

    p {
      color: var(--text-dim);
      max-width: 640px;
      margin-bottom: 12px;
    }

    /* ── ABOUT ── */
    .about-box {
      background: var(--surface);
      border: 1px solid var(--border);
      border-left: 3px solid var(--accent2);
      padding: 24px 28px;
      border-radius: 4px;
    }

    .about-box p { max-width: 100%; }

    /* ── SKILLS ── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
      gap: 12px;
    }

    .skill-category {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 16px 18px;
      border-radius: 4px;
      transition: border-color 0.2s;
    }

    .skill-category:hover { border-color: var(--accent); }

    .skill-cat-name {
      font-size: 10px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 10px;
    }

    .skill-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }

    .tag {
      font-size: 11px;
      color: var(--text-dim);
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--border);
      padding: 2px 8px;
      border-radius: 2px;
    }

    /* ── PROJECTS ── */
    .projects-list {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .project-card {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 22px 26px;
      border-radius: 4px;
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 12px;
      align-items: start;
      transition: border-color 0.2s, transform 0.2s;
      cursor: default;
    }

    .project-card:hover {
      border-color: var(--accent);
      transform: translateX(4px);
    }

    .project-name {
      font-family: var(--display);
      font-size: 1rem;
      font-weight: 700;
      color: #fff;
      margin-bottom: 6px;
    }

    .project-desc {
      color: var(--text-dim);
      font-size: 12px;
      margin: 0;
      max-width: 100%;
    }

    .project-stack {
      display: flex;
      flex-wrap: wrap;
      gap: 5px;
      margin-top: 12px;
    }

    .stack-tag {
      font-size: 10px;
      color: var(--accent2);
      border: 1px solid rgba(0,201,255,0.25);
      padding: 2px 7px;
      border-radius: 2px;
      letter-spacing: 0.05em;
    }

    .project-status {
      font-size: 10px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--accent);
      white-space: nowrap;
      padding-top: 2px;
    }

    .project-status.wip { color: #f5a623; }

    /* ── CONTACT ── */
    .contact-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 12px;
    }

    .contact-item {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 16px 20px;
      border-radius: 4px;
      text-decoration: none;
      transition: border-color 0.2s, background 0.2s;
      display: block;
    }

    .contact-item:hover {
      border-color: var(--accent2);
      background: rgba(0,201,255,0.05);
    }

    .contact-label {
      font-size: 10px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 6px;
    }

    .contact-value {
      color: var(--accent2);
      font-size: 13px;
      word-break: break-all;
    }

    /* ── FOOTER ── */
    footer {
      margin-top: 80px;
      border-top: 1px solid var(--border);
      padding-top: 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 12px;
      color: var(--muted);
      font-size: 11px;
    }

    .cursor {
      display: inline-block;
      width: 8px;
      height: 14px;
      background: var(--accent);
      margin-left: 4px;
      vertical-align: middle;
      animation: blink 1s step-end infinite;
    }

    @keyframes blink { 50% { opacity: 0; } }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <header class="header">
    <div class="badge">README.md</div>
    <h1>Prince Singh<span class="cursor"></span></h1>
    <p class="tagline">
      Data Scientist &amp; ML Engineer — turning raw data into<br/>
      <span>intelligent systems, insights, and decisions</span>.
    </p>
  </header>

  <!-- ABOUT -->
  <section>
    <div class="section-label">01 — About</div>
    <div class="about-box">
      <p>
        Hi! I'm a passionate Data Scientist and ML Engineer with experience building end-to-end
        machine learning pipelines, deploying production models, and extracting actionable insight
        from complex datasets. I enjoy working at the intersection of rigorous statistics and
        real-world engineering.
      </p>
      <p style="margin-bottom:0;">
        When I'm not training models, I'm exploring open datasets, contributing to research, or
        writing about applied ML. I believe clean data and clear communication are as important
        as any algorithm.
      </p>
    </div>
  </section>

  <!-- SKILLS -->
  <section>
    <div class="section-label">02 — Skills &amp; Technologies</div>
    <div class="skills-grid">
      <div class="skill-category">
        <div class="skill-cat-name">Languages</div>
        <div class="skill-tags">
          <span class="tag">Python</span>
          <span class="tag">SQL</span>
          <span class="tag">R</span>
          <span class="tag">Bash</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-name">ML / DL</div>
        <div class="skill-tags">
          <span class="tag">PyTorch</span>
          <span class="tag">TensorFlow</span>
          <span class="tag">Scikit-learn</span>
          <span class="tag">XGBoost</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-name">Data</div>
        <div class="skill-tags">
          <span class="tag">Pandas</span>
          <span class="tag">NumPy</span>
          <span class="tag">Spark</span>
          <span class="tag">dbt</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-name">MLOps</div>
        <div class="skill-tags">
          <span class="tag">MLflow</span>
          <span class="tag">Docker</span>
          <span class="tag">Airflow</span>
          <span class="tag">FastAPI</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-name">Cloud</div>
        <div class="skill-tags">
          <span class="tag">AWS</span>
          <span class="tag">GCP</span>
          <span class="tag">Azure</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-name">Visualization</div>
        <div class="skill-tags">
          <span class="tag">Plotly</span>
          <span class="tag">Tableau</span>
          <span class="tag">Seaborn</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section>
    <div class="section-label">03 — Projects &amp; Works</div>
    <div class="projects-list">

      <div class="project-card">
        <div>
          <div class="project-name">Customer Churn Predictor</div>
          <p class="project-desc">
            End-to-end ML pipeline predicting customer churn for a SaaS product. Achieved 91% AUC
            using gradient boosting with SHAP-based explainability dashboard.
          </p>
          <div class="project-stack">
            <span class="stack-tag">Python</span>
            <span class="stack-tag">XGBoost</span>
            <span class="stack-tag">SHAP</span>
            <span class="stack-tag">FastAPI</span>
            <span class="stack-tag">Docker</span>
          </div>
        </div>
        <div class="project-status">Deployed</div>
      </div>

      <div class="project-card">
        <div>
          <div class="project-name">NLP Sentiment Analyzer</div>
          <p class="project-desc">
            Fine-tuned BERT model for multi-class sentiment analysis on product reviews.
            Includes a REST API and a lightweight React demo interface.
          </p>
          <div class="project-stack">
            <span class="stack-tag">PyTorch</span>
            <span class="stack-tag">HuggingFace</span>
            <span class="stack-tag">BERT</span>
            <span class="stack-tag">FastAPI</span>
          </div>
        </div>
        <div class="project-status">Open Source</div>
      </div>

      <div class="project-card">
        <div>
          <div class="project-name">Time-Series Forecasting Engine</div>
          <p class="project-desc">
            Automated forecasting system comparing ARIMA, Prophet, and LSTM models for
            retail demand planning. Reduces inventory waste by ~18%.
          </p>
          <div class="project-stack">
            <span class="stack-tag">Python</span>
            <span class="stack-tag">Prophet</span>
            <span class="stack-tag">LSTM</span>
            <span class="stack-tag">Airflow</span>
            <span class="stack-tag">MLflow</span>
          </div>
        </div>
        <div class="project-status wip">In Progress</div>
      </div>

      <div class="project-card">
        <div>
          <div class="project-name">EDA Automation Tool</div>
          <p class="project-desc">
            CLI + notebook tool that auto-generates statistical summaries, distribution plots,
            correlation heatmaps, and data quality reports from any CSV.
          </p>
          <div class="project-stack">
            <span class="stack-tag">Python</span>
            <span class="stack-tag">Pandas</span>
            <span class="stack-tag">Plotly</span>
            <span class="stack-tag">Jinja2</span>
          </div>
        </div>
        <div class="project-status">Open Source</div>
      </div>

    </div>
  </section>

  <!-- CONTACT -->
  <section>
    <div class="section-label">04 — Contact</div>
    <div class="contact-grid">
      <a class="contact-item" href="mailto:yourname@email.com">
        <div class="contact-label">Email</div>
        <div class="contact-value">yourname@email.com</div>
      </a>
      <a class="contact-item" href="https://github.com/yourusername" target="_blank">
        <div class="contact-label">GitHub</div>
        <div class="contact-value">github.com/yourusername</div>
      </a>
      <a class="contact-item" href="https://linkedin.com/in/yourusername" target="_blank">
        <div class="contact-label">LinkedIn</div>
        <div class="contact-value">linkedin.com/in/yourusername</div>
      </a>
      <a class="contact-item" href="https://yourwebsite.com" target="_blank">
        <div class="contact-label">Portfolio</div>
        <div class="contact-value">yourwebsite.com</div>
      </a>
    </div>
  </section>

  <footer>
    <span>// README generated — update with your real details</span>
    <span>Data Scientist &amp; ML Engineer</span>
  </footer>

</div>
</body>
</html>
