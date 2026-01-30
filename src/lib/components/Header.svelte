<script lang="ts">
  export let activeSection = 0;

  const navItems = [
    { label: 'About', index: 1 },
    { label: 'Skills', index: 2 },
    { label: 'Contact', index: 3 }
  ];

  function scrollToSection(index: number) {
    const event = new CustomEvent('fullpage:goto', {
      detail: index,
      bubbles: true
    });
    window.dispatchEvent(event);
  }

  function goHome() {
    scrollToSection(0);
  }
</script>

<header>
  <div class="container">
    <nav>
      <button class="logo" on:click={goHome} class:active={activeSection === 0}>
        JR
      </button>
      <ul>
        {#each navItems as item}
          <li>
            <button
              on:click={() => scrollToSection(item.index)}
              class:active={activeSection === item.index}
            >
              {item.label}
            </button>
          </li>
        {/each}
      </ul>
    </nav>
  </div>
</header>

<style>
  header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: rgba(15, 23, 42, 0.8);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    z-index: 100;
  }

  .container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 1.5rem;
  }

  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 4rem;
  }

  .logo {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--text);
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.25rem 0.5rem;
    border-radius: 0.25rem;
    transition: color 0.2s ease;
  }

  .logo:hover,
  .logo.active {
    color: var(--accent);
  }

  ul {
    display: flex;
    gap: 0.5rem;
    list-style: none;
  }

  ul button {
    color: var(--text-secondary);
    font-weight: 500;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    transition: color 0.2s ease, background-color 0.2s ease;
    font-size: 1rem;
  }

  ul button:hover {
    color: var(--accent);
  }

  ul button.active {
    color: var(--accent);
    background: rgba(59, 130, 246, 0.1);
  }

  @media (prefers-color-scheme: light) {
    header {
      background: rgba(255, 255, 255, 0.8);
      border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    }
  }

  @media (max-width: 640px) {
    ul {
      gap: 0;
    }

    ul button {
      padding: 0.5rem 0.75rem;
      font-size: 0.875rem;
    }

    .logo {
      font-size: 1.25rem;
    }
  }
</style>
