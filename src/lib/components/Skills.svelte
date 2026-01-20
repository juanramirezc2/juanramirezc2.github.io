<script lang="ts">
  const skills = [
    { category: 'Languages', items: ['TypeScript', 'JavaScript', 'HTML', 'CSS'] },
    { category: 'Frameworks', items: ['React', 'Svelte', 'Next.js', 'Vue'] },
    { category: 'Tools', items: ['Git', 'Vite', 'Webpack', 'Docker'] },
    { category: 'Other', items: ['Node.js', 'REST APIs', 'GraphQL', 'CI/CD'] }
  ]
</script>

<section id="skills">
  <div class="container">
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
</section>

<style>
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
  }

  .skill-card {
    background-color: var(--bg-secondary);
    padding: 1.5rem;
    border-radius: 0.75rem;
    border: 1px solid var(--border);
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
</style>
