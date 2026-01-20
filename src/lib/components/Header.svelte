<script lang="ts">
  const navItems = [
    { label: 'About', href: '#about' },
    { label: 'Skills', href: '#skills' },
    { label: 'Contact', href: '#contact' }
  ]
</script>

<header>
  <div class="container">
    <nav>
      <a href="/" class="logo">JR</a>
      <ul>
        {#each navItems as item}
          <li>
            <a href={item.href}>{item.label}</a>
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
    background-color: var(--bg);
    border-bottom: 1px solid var(--border);
    z-index: 100;
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
  }

  .logo:hover {
    color: var(--accent);
  }

  ul {
    display: flex;
    gap: 2rem;
    list-style: none;
  }

  ul a {
    color: var(--text-secondary);
    font-weight: 500;
  }

  ul a:hover {
    color: var(--accent);
  }
</style>
