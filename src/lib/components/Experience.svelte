<script lang="ts">
  import { onMount } from 'svelte';

  type Job = {
    period: string;
    title: string;
    company: string;
  };

  const jobs: Job[] = [
    { period: '2022 — Now',  title: 'Frontend Engineering Lead',          company: 'Boldin' },
    { period: '2020 — 2022', title: 'Staff Software Engineer',            company: 'Software Mind Americas' },
    { period: '2019 — 2020', title: 'Senior Frontend Engineer',           company: 'Rockstar Coders' },
    { period: '2018 — 2019', title: 'Senior Frontend Developer',          company: 'Zaga' },
    { period: '2016 — 2018', title: 'Freelance Software Engineer',        company: 'Autónomo' },
    { period: '2015',        title: 'Senior Frontend Developer',          company: 'XumaK' },
    { period: '2014',        title: 'Senior Frontend Developer',          company: 'American Media' },
    { period: '2013 — 2014', title: 'Fullstack Developer',                company: 'Paradiso Solutions' },
    { period: '2011 — 2013', title: 'Web Developer',                      company: 'A&A Soluciones — TIC' },
    { period: '2009 — 2011', title: 'Peer-Assisted Learning Leader',      company: 'Universidad Tecnológica de Pereira' }
  ];

  let visible = false;

  onMount(() => {
    visible = true;
  });

  function entryDelay(index: number): string {
    return `${index * 80}ms`;
  }
</script>

<section id="experience">
  <div class="container">
    <div class="glass-card">
      <h2>Experience</h2>
      <ol class="timeline">
        {#each jobs as job, index}
          <li
            class="timeline-item"
            class:animate={visible}
            style="--entry-delay: {entryDelay(index)};"
          >
            <span class="dot"></span>
            <p class="period">{job.period}</p>
            <p class="role">
              <span class="title">{job.title}</span>
              <span class="separator">·</span>
              <span class="company">{job.company}</span>
            </p>
          </li>
        {/each}
      </ol>
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
    padding-bottom: 2rem;
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

  .timeline {
    position: relative;
    list-style: none;
    margin: 0;
    padding: 0 0 0 1.75rem;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 0.4rem;
    top: 0.45rem;
    bottom: 0.45rem;
    width: 2px;
    background: rgba(255, 255, 255, 0.12);
    border-radius: 1px;
  }

  .timeline-item {
    position: relative;
    display: grid;
    grid-template-columns: 8.5rem 1fr;
    gap: 1.5rem;
    align-items: baseline;
    padding-bottom: 0.75rem;
    opacity: 0;
    transform: translateY(8px);
    transition:
      opacity 500ms cubic-bezier(0.16, 1, 0.3, 1),
      transform 500ms cubic-bezier(0.16, 1, 0.3, 1);
    transition-delay: var(--entry-delay);
  }

  .timeline-item:last-child {
    padding-bottom: 0;
  }

  .timeline-item.animate {
    opacity: 1;
    transform: translateY(0);
  }

  .dot {
    position: absolute;
    left: -1.45rem;
    top: 0.4rem;
    width: 0.65rem;
    height: 0.65rem;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.18);
  }

  .period {
    color: var(--accent);
    font-weight: 600;
    font-size: 0.875rem;
    margin: 0;
    letter-spacing: 0.02em;
    white-space: nowrap;
  }

  .role {
    margin: 0;
    font-size: 0.95rem;
    line-height: 1.4;
    color: var(--text);
  }

  .title {
    font-weight: 600;
  }

  .separator {
    color: var(--text-secondary);
    margin: 0 0.4rem;
  }

  .company {
    color: var(--text-secondary);
    font-weight: 500;
  }

  @media (prefers-color-scheme: light) {
    .glass-card {
      background: transparent;
      border: 1px solid rgba(0, 0, 0, 0.05);
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.03);
    }

    .timeline::before {
      background: rgba(0, 0, 0, 0.12);
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

    .timeline {
      padding-left: 1.5rem;
    }

    .timeline-item {
      grid-template-columns: 1fr;
      gap: 0.15rem;
      padding-bottom: 0.85rem;
    }

    .period {
      font-size: 0.8rem;
    }

    .role {
      font-size: 0.9rem;
    }

    .separator {
      margin: 0 0.3rem;
    }
  }
</style>
