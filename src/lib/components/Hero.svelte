<section id="hero">
  <div class="container">
    <div class="hero-content">
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
</section>

<style>
  section {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding-top: 4rem;
  }

  .hero-content {
    max-width: 600px;
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
  }

  .btn.secondary {
    border: 2px solid var(--border);
    color: var(--text);
  }

  .btn.secondary:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  @media (max-width: 640px) {
    h1 {
      font-size: 2.5rem;
    }

    .title {
      font-size: 1.25rem;
    }

    .tagline {
      font-size: 1rem;
    }

    .cta {
      flex-direction: column;
    }
  }
</style>
