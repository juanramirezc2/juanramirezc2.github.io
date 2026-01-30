<section id="about">
  <div class="container">
    <div class="glass-card">
      <h2>About Me</h2>
      <div class="about-content">
        <p>
          I'm a passionate Frontend Engineering Lead with expertise in building
          scalable, performant web applications. With years of experience leading
          engineering teams, I specialize in crafting exceptional user experiences
          using modern technologies like TypeScript, React, and Svelte.
        </p>
        <p>
          I believe in clean code, thoughtful architecture, and creating products
          that make a real impact. When I'm not coding, you'll find me exploring
          new technologies, mentoring developers, and contributing to the web
          development community.
        </p>
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
  }

  .container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 1.5rem;
    width: 100%;
  }

  .glass-card {
    background: rgba(15, 23, 42, 0.6);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 1.5rem;
    padding: 2.5rem;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
    max-width: 800px;
  }

  h2 {
    font-size: 2rem;
    margin-bottom: 1.5rem;
    color: var(--text);
  }

  .about-content {
    max-width: 700px;
  }

  p {
    font-size: 1.125rem;
    color: var(--text-secondary);
    margin-bottom: 1.5rem;
    line-height: 1.7;
  }

  p:last-child {
    margin-bottom: 0;
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
    }

    .glass-card {
      padding: 1.75rem;
      border-radius: 1rem;
    }

    h2 {
      font-size: 1.75rem;
    }

    p {
      font-size: 1rem;
    }
  }
</style>
