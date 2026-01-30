<script lang="ts">
  const skills = [
    { category: 'Languages', items: ['TypeScript', 'JavaScript', 'HTML', 'CSS'] },
    { category: 'Frameworks', items: ['React', 'Svelte', 'Next.js', 'Vue'] },
    { category: 'Tools', items: ['Git', 'Vite', 'Webpack', 'Docker'] },
    { category: 'Other', items: ['Node.js', 'REST APIs', 'GraphQL', 'CI/CD'] }
  ];
</script>

<section id="skills">
  <div class="container">
    <div class="glass-card">
      <h2>Skills</h2>
      <div class="skills-grid">
        {#each skills as skill}
          <div class="skill-card">
            <h3>{skill.category}</h3>
            <ul>
              {#each skill.items as item}
                <li>{item}</li>
              {/each}
            </ul>
          </div>
        {/each}
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
  }

  h2 {
    font-size: 2rem;
    margin-bottom: 1.5rem;
    color: var(--text);
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1.5rem;
  }

  .skill-card {
    background: rgba(255, 255, 255, 0.05);
    padding: 1.5rem;
    border-radius: 0.75rem;
    border: 1px solid rgba(255, 255, 255, 0.1);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .skill-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 24px rgba(59, 130, 246, 0.15);
  }

  h3 {
    font-size: 1.125rem;
    margin-bottom: 1rem;
    color: var(--accent);
  }

  ul {
    list-style: none;
  }

  li {
    color: var(--text-secondary);
    padding: 0.25rem 0;
  }

  @media (prefers-color-scheme: light) {
    .glass-card {
      background: rgba(255, 255, 255, 0.7);
      border: 1px solid rgba(255, 255, 255, 0.8);
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
    }

    .skill-card {
      background: rgba(255, 255, 255, 0.5);
      border: 1px solid rgba(0, 0, 0, 0.05);
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

    .skills-grid {
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
    }

    .skill-card {
      padding: 1rem;
    }

    h3 {
      font-size: 1rem;
    }

    li {
      font-size: 0.875rem;
    }
  }

  @media (max-width: 380px) {
    .skills-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
