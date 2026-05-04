<section id="about">
  <div class="container">
    <div class="glass-card">
      <h2>About Me</h2>
      <div class="about-content">
        <p>
          I'm a senior fullstack developer with 15+ years of experience
          building production web applications end-to-end — from polished
          React/Next.js and TypeScript frontends to Node.js, Rails, and
          PHP backends. I have a strong UX foundation that helps me
          translate product and design intent into accessible, performant,
          intuitive interfaces.
        </p>
        <p>
          Most recently I've focused on AI and agentic software engineering:
          designing multi-step agent workflows, integrating LLMs and external
          APIs into production systems, and applying RAG, prompt engineering,
          function calling, tool use, and Model Context Protocol (MCP) servers
          to ship real product features. I deliver simple, reliable solutions
          to complex problems and lead engineers toward the same.
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
    background: transparent;
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 1.5rem;
    padding: 2.5rem;
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
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
      background: transparent;
      border: 1px solid rgba(0, 0, 0, 0.05);
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.03);
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
