<section id="hero">
  <div class="container">
    <div class="hero-content">
      <div class="glass-card">
        <h1>Juan Ramirez</h1>
        <p class="title">Frontend Engineering Lead</p>
        <p class="tagline">
          Building exceptional user experiences with modern web technologies
        </p>
        <div class="cta">
          <a href="#contact" class="btn primary">Get in Touch</a>
          <a href="#about" class="btn secondary">Learn More</a>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  section {
    min-height: 100vh;
    height: 100%;
    display: flex;
    align-items: center;
    padding-top: 4rem;
    position: relative;
  }

  .container {
    position: relative;
    z-index: 1;
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 1.5rem;
    width: 100%;
  }

  .hero-content {
    max-width: 650px;
  }

  .glass-card {
    background: rgba(15, 23, 42, 0.6);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 1.5rem;
    padding: 2.5rem;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
  }

  h1 {
    font-size: 3.5rem;
    font-weight: 800;
    margin-bottom: 0.5rem;
    background: linear-gradient(135deg, var(--accent) 0%, var(--text) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .title {
    font-size: 1.5rem;
    color: var(--accent);
    font-weight: 600;
    margin-bottom: 1rem;
  }

  .tagline {
    font-size: 1.25rem;
    color: var(--text-secondary);
    margin-bottom: 2rem;
  }

  .cta {
    display: flex;
    gap: 1rem;
  }

  .btn {
    padding: 0.75rem 1.5rem;
    border-radius: 0.5rem;
    font-weight: 600;
    transition: all 0.2s ease;
  }

  .btn.primary {
    background-color: var(--accent);
    color: white;
  }

  .btn.primary:hover {
    background-color: var(--accent-hover);
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(59, 130, 246, 0.4);
  }

  .btn.secondary {
    border: 2px solid var(--border);
    color: var(--text);
    background: rgba(255, 255, 255, 0.05);
  }

  .btn.secondary:hover {
    border-color: var(--accent);
    color: var(--accent);
    transform: translateY(-2px);
  }

  @media (prefers-color-scheme: light) {
    .glass-card {
      background: rgba(255, 255, 255, 0.7);
      border: 1px solid rgba(255, 255, 255, 0.8);
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
    }
  }

  @media (max-width: 640px) {
    section {
      padding-top: 5rem;
      padding-bottom: 2rem;
    }

    .glass-card {
      padding: 1.75rem;
      border-radius: 1rem;
    }

    h1 {
      font-size: 2.25rem;
    }

    .title {
      font-size: 1.15rem;
    }

    .tagline {
      font-size: 1rem;
      margin-bottom: 1.5rem;
    }

    .cta {
      flex-direction: column;
    }

    .btn {
      text-align: center;
    }
  }

  @media (max-width: 380px) {
    .glass-card {
      padding: 1.25rem;
    }

    h1 {
      font-size: 1.875rem;
    }

    .title {
      font-size: 1rem;
    }
  }
</style>
