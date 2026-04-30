<script lang="ts">
  import { onMount } from 'svelte';

  const maxYears = 10;

  const skills = [
    {
      category: 'Languages',
      items: [
        { name: 'TypeScript', years: 6 },
        { name: 'JavaScript', years: 10 },
        { name: 'HTML', years: 10 },
        { name: 'CSS', years: 10 },
      ]
    },
    {
      category: 'Frontend',
      items: [
        { name: 'React', years: 7 },
        { name: 'Svelte', years: 3 },
        { name: 'Next.js', years: 4 },
        { name: 'Vue', years: 2 },
      ]
    },
    {
      category: 'Backend',
      items: [
        { name: 'Node.js', years: 8 },
        { name: 'REST APIs', years: 8 },
        { name: 'GraphQL', years: 4 },
        { name: 'CI/CD', years: 5 },
      ]
    },
    {
      category: 'Tools',
      items: [
        { name: 'Git', years: 9 },
        { name: 'Vite', years: 3 },
        { name: 'Webpack', years: 6 },
        { name: 'Docker', years: 4 },
      ]
    }
  ];

  let visible = false;

  onMount(() => {
    visible = true;
  });

  function barWidth(years: number): number {
    return Math.min((years / maxYears) * 100, 100);
  }

  function barDelay(catIndex: number, itemIndex: number): string {
    const base = catIndex * 200 + itemIndex * 100;
    return `${base}ms`;
  }

  function labelDelay(catIndex: number, itemIndex: number): string {
    const base = catIndex * 200 + itemIndex * 100 + 400;
    return `${base}ms`;
  }
</script>

<section id="skills">
  <div class="container">
    <div class="glass-card">
      <h2>Skills</h2>
      <div class="skills-grid">
        {#each skills as group, catIndex}
          <div class="skill-group">
            <h3>{group.category}</h3>
            <div class="bars">
              {#each group.items as skill, itemIndex}
                <div class="bar-row">
                  <div class="bar-track">
                    <div
                      class="bar-fill"
                      class:animate={visible}
                      style="--target-width: {barWidth(skill.years)}%; --bar-delay: {barDelay(catIndex, itemIndex)};"
                    ></div>
                    <span
                      class="bar-label"
                      class:animate={visible}
                      style="--label-delay: {labelDelay(catIndex, itemIndex)};"
                    >
                      {skill.name}
                      <span class="bar-years">{skill.years}y</span>
                    </span>
                  </div>
                </div>
              {/each}
            </div>
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
    background: transparent;
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 1.5rem;
    padding: 2.5rem;
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
  }

  h2 {
    font-size: 2rem;
    margin-bottom: 1.5rem;
    color: var(--text);
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }

  .skill-group {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
  }

  h3 {
    font-size: 1.125rem;
    margin-bottom: 0.75rem;
    color: var(--accent);
  }

  .bars {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .bar-row {
    width: 100%;
  }

  .bar-track {
    position: relative;
    width: 100%;
    height: 2rem;
    background: rgba(255, 255, 255, 0.05);
    border-radius: 0.375rem;
    overflow: hidden;
  }

  .bar-fill {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 0;
    background: linear-gradient(90deg, var(--accent), var(--accent-hover));
    border-radius: 0.375rem;
    opacity: 0.8;
    transition: width 600ms cubic-bezier(0.16, 1, 0.3, 1);
    transition-delay: var(--bar-delay);
  }

  .bar-fill.animate {
    width: var(--target-width);
  }

  .bar-label {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 0.75rem;
    font-size: 0.875rem;
    font-weight: 600;
    color: var(--text);
    opacity: 0;
    transition: opacity 400ms ease;
    transition-delay: var(--label-delay);
    pointer-events: none;
  }

  .bar-label.animate {
    opacity: 1;
  }

  .bar-years {
    font-weight: 400;
    font-size: 0.75rem;
    color: var(--text-secondary);
  }

  @media (prefers-color-scheme: light) {
    .glass-card {
      background: transparent;
      border: 1px solid rgba(0, 0, 0, 0.05);
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.03);
    }

    .bar-track {
      background: rgba(0, 0, 0, 0.05);
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
      grid-template-columns: 1fr;
      gap: 1.5rem;
    }

    h3 {
      font-size: 1rem;
    }

    .bar-track {
      height: 1.75rem;
    }

    .bar-label {
      font-size: 0.8rem;
    }
  }
</style>
