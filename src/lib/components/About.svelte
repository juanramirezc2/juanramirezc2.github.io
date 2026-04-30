<section id="about">
  <div class="container">
    <div class="glass-card">
      <h2>About Me</h2>
      <div class="about-content">
        <p>
          I'm a senior fullstack developer with over 15 years of experience
          building scalable, performant web applications end-to-end. I work
          across the stack — from TypeScript-driven interfaces in React and
          Svelte to the Node.js services and APIs that power them.
        </p>
        <p>
          I believe in clean code, thoughtful architecture, and creating products
          that make a real impact. Outside of shipping production work, I enjoy
          tinkering with AI and building agentic workflows — exploring how
          LLM-driven tools can reshape day-to-day engineering. I also spend time
          mentoring developers and contributing to the web development community.
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
