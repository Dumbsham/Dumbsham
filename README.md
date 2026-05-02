<div>
  
<style>
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;700&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --acid: #C8F53D;
    --acid-dim: #a8d42a;
    --dark: #0A0A0A;
    --dark2: #111111;
    --dark3: #1A1A1A;
    --dark4: #222222;
    --mid: #333333;
    --text: #F0F0F0;
    --muted: #888888;
    --border: #2A2A2A;
    --glow: rgba(200, 245, 61, 0.15);
  }

  .profile-root {
    font-family: 'Syne', sans-serif;
    background: var(--dark);
    color: var(--text);
    padding: 2rem 1.5rem;
    min-height: 100vh;
    position: relative;
    overflow: hidden;
  }

  .bg-grid {
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(200,245,61,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(200,245,61,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .content { position: relative; z-index: 1; max-width: 780px; margin: 0 auto; }

  /* HERO */
  .hero {
    display: flex;
    align-items: flex-start;
    gap: 2rem;
    margin-bottom: 3rem;
    padding-bottom: 3rem;
    border-bottom: 1px solid var(--border);
  }

  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
  }

  .avatar-ring {
    width: 88px;
    height: 88px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--acid), #5af, var(--acid));
    padding: 2px;
    animation: spin-ring 8s linear infinite;
  }

  @keyframes spin-ring {
    0% { background: linear-gradient(135deg, var(--acid), #5af, var(--acid)); }
    50% { background: linear-gradient(315deg, var(--acid), #f5a, var(--acid)); }
    100% { background: linear-gradient(135deg, var(--acid), #5af, var(--acid)); }
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--dark2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2rem;
    font-weight: 800;
    color: var(--acid);
    letter-spacing: -1px;
  }

  .status-dot {
    position: absolute;
    bottom: 4px;
    right: 4px;
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background: #22c55e;
    border: 2px solid var(--dark);
    animation: pulse-dot 2s ease-in-out infinite;
  }

  @keyframes pulse-dot {
    0%, 100% { box-shadow: 0 0 0 0 rgba(34,197,94,0.4); }
    50% { box-shadow: 0 0 0 6px rgba(34,197,94,0); }
  }

  .hero-info { flex: 1; }

  .hero-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--acid);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 0.4rem;
    opacity: 0.85;
  }

  .hero-name {
    font-size: 2.8rem;
    font-weight: 800;
    line-height: 1;
    letter-spacing: -2px;
    margin-bottom: 0.5rem;
  }

  .hero-name span { color: var(--acid); }

  .hero-bio {
    font-size: 0.9rem;
    color: var(--muted);
    line-height: 1.6;
    max-width: 500px;
    margin-bottom: 1.2rem;
  }

  .hero-links {
    display: flex;
    gap: 0.6rem;
    flex-wrap: wrap;
  }

  .pill-link {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 5px 12px;
    border-radius: 100px;
    border: 1px solid var(--border);
    color: var(--muted);
    text-decoration: none;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    gap: 5px;
    cursor: pointer;
  }

  .pill-link:hover { border-color: var(--acid); color: var(--acid); }

  /* NOW BUILDING */
  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--acid);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .now-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 2.5rem;
  }

  .now-card {
    background: var(--dark2);
    padding: 1.2rem;
    transition: background 0.2s;
    position: relative;
  }

  .now-card:hover { background: var(--dark3); }

  .now-icon {
    font-size: 1.4rem;
    margin-bottom: 0.6rem;
  }

  .now-title {
    font-size: 0.85rem;
    font-weight: 600;
    margin-bottom: 0.3rem;
    color: var(--text);
  }

  .now-desc {
    font-size: 0.75rem;
    color: var(--muted);
    line-height: 1.5;
  }

  .now-badge {
    position: absolute;
    top: 1rem;
    right: 1rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    padding: 2px 8px;
    border-radius: 100px;
    background: rgba(200,245,61,0.1);
    color: var(--acid);
    border: 1px solid rgba(200,245,61,0.2);
  }

  /* PROJECTS */
  .projects { margin-bottom: 2.5rem; }

  .project-card {
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.2rem 1.4rem;
    margin-bottom: 10px;
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    background: var(--dark2);
    transition: all 0.2s;
    cursor: pointer;
    text-decoration: none;
    color: inherit;
  }

  .project-card:hover {
    border-color: rgba(200,245,61,0.3);
    background: var(--dark3);
    transform: translateX(4px);
  }

  .project-card.featured {
    border-color: rgba(200,245,61,0.2);
    background: linear-gradient(135deg, rgba(200,245,61,0.04) 0%, var(--dark2) 100%);
  }

  .project-card.featured:hover {
    border-color: rgba(200,245,61,0.5);
  }

  .proj-icon-wrap {
    width: 40px;
    height: 40px;
    border-radius: 10px;
    background: var(--dark4);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
    border: 1px solid var(--border);
  }

  .proj-info { flex: 1; }

  .proj-header {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 0.25rem;
  }

  .proj-name {
    font-size: 0.9rem;
    font-weight: 700;
    color: var(--text);
  }

  .proj-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    padding: 2px 7px;
    border-radius: 4px;
    background: var(--dark4);
    color: var(--muted);
    border: 1px solid var(--border);
  }

  .proj-tag.impact { background: rgba(200,245,61,0.08); color: var(--acid); border-color: rgba(200,245,61,0.2); }
  .proj-tag.ai { background: rgba(90,170,255,0.08); color: #5af; border-color: rgba(90,170,255,0.2); }
  .proj-tag.ml { background: rgba(250,100,200,0.08); color: #f5a; border-color: rgba(250,100,200,0.2); }

  .proj-desc {
    font-size: 0.78rem;
    color: var(--muted);
    line-height: 1.5;
    margin-bottom: 0.5rem;
  }

  .proj-stack {
    display: flex;
    gap: 5px;
    flex-wrap: wrap;
  }

  .stack-chip {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 4px;
    background: var(--dark4);
    color: #888;
    border: 1px solid var(--border);
  }

  .proj-arrow {
    color: var(--muted);
    font-size: 1rem;
    margin-top: 4px;
    transition: all 0.2s;
  }

  .project-card:hover .proj-arrow {
    color: var(--acid);
    transform: translate(2px, -2px);
  }

  /* TECH STACK */
  .stack-section { margin-bottom: 2.5rem; }

  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 8px;
  }

  .stack-item {
    background: var(--dark2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 0.8rem 1rem;
    display: flex;
    align-items: center;
    gap: 8px;
    transition: all 0.2s;
  }

  .stack-item:hover {
    border-color: rgba(200,245,61,0.25);
    background: var(--dark3);
  }

  .stack-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .stack-name {
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--text);
  }

  .stack-role {
    font-size: 0.68rem;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
  }

  /* FOOTER */
  .footer {
    border-top: 1px solid var(--border);
    padding-top: 1.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: gap;
  }

  .footer-left {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  .footer-left span { color: var(--acid); }

  .cta-btn {
    font-family: 'Syne', sans-serif;
    font-size: 0.8rem;
    font-weight: 700;
    padding: 8px 20px;
    border-radius: 100px;
    background: var(--acid);
    color: var(--dark);
    border: none;
    cursor: pointer;
    letter-spacing: 0.02em;
    transition: all 0.2s;
  }

  .cta-btn:hover {
    background: var(--acid-dim);
    transform: translateY(-1px);
  }

  /* Animations */
  .fade-up {
    animation: fadeUp 0.5s ease both;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero { animation: fadeUp 0.4s ease both; }
  .now-grid { animation: fadeUp 0.5s 0.1s ease both; }
  .projects { animation: fadeUp 0.5s 0.2s ease both; }
  .stack-section { animation: fadeUp 0.5s 0.3s ease both; }
  .footer { animation: fadeUp 0.5s 0.4s ease both; }

  .terminal-cursor {
    display: inline-block;
    width: 2px;
    height: 1.2em;
    background: var(--acid);
    vertical-align: text-bottom;
    margin-left: 2px;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }
</style>

<div class="profile-root">
  <div class="bg-grid"></div>
  <div class="content">

    <!-- HERO -->
    <div class="hero">
      <div class="avatar-wrap">
        <div class="avatar-ring">
          <div class="avatar-inner">S</div>
        </div>
        <div class="status-dot"></div>
      </div>
      <div class="hero-info">
        <div class="hero-tag">// software developer &amp; ai builder</div>
        <h1 class="hero-name">Saksham<span>.</span></h1>
        <p class="hero-bio">Building intelligent agents, voice-first AI platforms, and predictive ML models. Exploring the intersection of modern web tech and applied AI — with a focus on social impact.</p>
        <div class="hero-links">
          <a class="pill-link" href="https://github.com/Dumbsham" target="_blank">⌥ github</a>
          <a class="pill-link" href="https://linkedin.com/in/YOUR_LINKEDIN_USERNAME" target="_blank">⌥ linkedin</a>
          <a class="pill-link" href="mailto:YOUR_EMAIL@example.com">⌥ email</a>
          <a class="pill-link" href="https://YOUR_PORTFOLIO_WEBSITE.com" target="_blank">⌥ portfolio</a>
        </div>
      </div>
    </div>

    <!-- NOW BUILDING -->
    <div class="section-label">currently building</div>
    <div class="now-grid">
      <div class="now-card">
        <div class="now-badge">active</div>
        <div class="now-icon">🌐</div>
        <div class="now-title">Saksham AI Platform</div>
        <div class="now-desc">Voice-first AI for underutilized women in India — multilingual, personalized skill discovery.</div>
      </div>
      <div class="now-card">
        <div class="now-badge">active</div>
        <div class="now-icon">🤖</div>
        <div class="now-title">AI Agents</div>
        <div class="now-desc">Research Agent &amp; DSA Tutor Agent — automating learning and deep research workflows.</div>
      </div>
      <div class="now-card">
        <div class="now-badge">active</div>
        <div class="now-icon">📊</div>
        <div class="now-title">ML Models</div>
        <div class="now-desc">End-to-end predictive models across healthcare, finance, and automotive datasets.</div>
      </div>
    </div>

    <!-- PROJECTS -->
    <div class="section-label">projects</div>
    <div class="projects">

      <a class="project-card featured" href="https://github.com/Dumbsham/Saksham" target="_blank">
        <div class="proj-icon-wrap">🪔</div>
        <div class="proj-info">
          <div class="proj-header">
            <span class="proj-name">Saksham + SakshamAI</span>
            <span class="proj-tag impact">social impact</span>
          </div>
          <div class="proj-desc">Voice-first, multilingual AI platform enabling underutilized women in India to discover skills and connect to verified income opportunities with personalized guidance.</div>
          <div class="proj-stack">
            <span class="stack-chip">TypeScript</span>
            <span class="stack-chip">Python</span>
            <span class="stack-chip">AI Agents</span>
            <span class="stack-chip">NLP</span>
          </div>
        </div>
        <div class="proj-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/Dumbsham/DSA_Tutor_Agent" target="_blank">
        <div class="proj-icon-wrap">🧠</div>
        <div class="proj-info">
          <div class="proj-header">
            <span class="proj-name">DSA Tutor Agent</span>
            <span class="proj-tag ai">AI</span>
          </div>
          <div class="proj-desc">Interactive AI tutoring agent for learning and practicing Data Structures &amp; Algorithms.</div>
          <div class="proj-stack">
            <span class="stack-chip">TypeScript</span>
            <span class="stack-chip">JavaScript</span>
            <span class="stack-chip">Python</span>
          </div>
        </div>
        <div class="proj-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/Dumbsham/Research_Agent" target="_blank">
        <div class="proj-icon-wrap">🔍</div>
        <div class="proj-info">
          <div class="proj-header">
            <span class="proj-name">Research Agent</span>
            <span class="proj-tag ai">AI</span>
          </div>
          <div class="proj-desc">Python-based autonomous agent for automating and accelerating deep research tasks.</div>
          <div class="proj-stack">
            <span class="stack-chip">Python</span>
            <span class="stack-chip">LLM Orchestration</span>
          </div>
        </div>
        <div class="proj-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/Dumbsham/Heart-Disease-Prediction-Project" target="_blank">
        <div class="proj-icon-wrap">🩺</div>
        <div class="proj-info">
          <div class="proj-header">
            <span class="proj-name">Predictive ML Models</span>
            <span class="proj-tag ml">ML</span>
          </div>
          <div class="proj-desc">Heart Disease, Car Price &amp; Insurance Premium predictors — end-to-end data science projects with real-world datasets.</div>
          <div class="proj-stack">
            <span class="stack-chip">Jupyter</span>
            <span class="stack-chip">scikit-learn</span>
            <span class="stack-chip">Python</span>
            <span class="stack-chip">Pandas</span>
          </div>
        </div>
        <div class="proj-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/Dumbsham/daily-satire-factory" target="_blank">
        <div class="proj-icon-wrap">🗞️</div>
        <div class="proj-info">
          <div class="proj-header">
            <span class="proj-name">Daily Satire Factory</span>
            <span class="proj-tag">creative</span>
          </div>
          <div class="proj-desc">Full-stack creative project blending Python automation with TypeScript web interfaces.</div>
          <div class="proj-stack">
            <span class="stack-chip">Python</span>
            <span class="stack-chip">TypeScript</span>
          </div>
        </div>
        <div class="proj-arrow">↗</div>
      </a>
    </div>

    <!-- TECH STACK -->
    <div class="stack-section">
      <div class="section-label">tech stack</div>
      <div class="stack-grid">
        <div class="stack-item">
          <div class="stack-dot" style="background:#3178C6"></div>
          <div><div class="stack-name">TypeScript</div><div class="stack-role">primary lang</div></div>
        </div>
        <div class="stack-item">
          <div class="stack-dot" style="background:#3776AB"></div>
          <div><div class="stack-name">Python</div><div class="stack-role">AI / DS / ML</div></div>
        </div>
        <div class="stack-item">
          <div class="stack-dot" style="background:#F7DF1E"></div>
          <div><div class="stack-name">JavaScript</div><div class="stack-role">web</div></div>
        </div>
        <div class="stack-item">
          <div class="stack-dot" style="background:#61DAFB"></div>
          <div><div class="stack-name">React / Next.js</div><div class="stack-role">frontend</div></div>
        </div>
        <div class="stack-item">
          <div class="stack-dot" style="background:#F37626"></div>
          <div><div class="stack-name">Jupyter</div><div class="stack-role">data science</div></div>
        </div>
        <div class="stack-item">
          <div class="stack-dot" style="background:#c8f53d"></div>
          <div><div class="stack-name">AI Agents</div><div class="stack-role">LLMs / tools</div></div>
        </div>
        <div class="stack-item">
          <div class="stack-dot" style="background:#FF6F00"></div>
          <div><div class="stack-name">ML / scikit</div><div class="stack-role">modeling</div></div>
        </div>
        <div class="stack-item">
          <div class="stack-dot" style="background:#1572B6"></div>
          <div><div class="stack-name">CSS</div><div class="stack-role">styling</div></div>
        </div>
      </div>
    </div>

    <!-- FOOTER -->
    <div class="footer">
      <div class="footer-left">
        <span>open to work</span> · Dādri, UP, India · building at the intersection of AI &amp; impact<span class="terminal-cursor"></span>
      </div>
      <button class="cta-btn" onclick="sendPrompt('Help me write a compelling README for one of my GitHub projects')">work with me ↗</button>
    </div>

  </div>
</div>

</div>
