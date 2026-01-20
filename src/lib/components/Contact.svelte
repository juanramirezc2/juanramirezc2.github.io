<script lang="ts">
  const contacts = [
    {
      label: 'Email',
      href: 'mailto:hello@juangramirez.me',
      text: 'hello@juangramirez.me',
      icon: 'M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z'
    },
    {
      label: 'LinkedIn',
      href: 'https://linkedin.com/in/juangramirez',
      text: 'linkedin.com/in/juangramirez',
      icon: 'M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z M4 6a2 2 0 100-4 2 2 0 000 4z'
    },
    {
      label: 'GitHub',
      href: 'https://github.com/juanramirezc2',
      text: 'github.com/juanramirezc2',
      icon: 'M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22'
    }
  ]
</script>

<section id="contact">
  <div class="container">
    <h2>Get in Touch</h2>
    <p class="intro">
      I'm always open to discussing new opportunities, interesting projects,
      or just having a chat about web development.
    </p>
    <div class="contact-links">
      {#each contacts as contact}
        <a href={contact.href} class="contact-link" target="_blank" rel="noopener noreferrer">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d={contact.icon} />
          </svg>
          <span>{contact.text}</span>
        </a>
      {/each}
    </div>
  </div>
</section>

<footer>
  <div class="container">
    <p>&copy; {new Date().getFullYear()} Juan Ramirez. All rights reserved.</p>
  </div>
</footer>

<style>
  section {
    background-color: var(--bg-secondary);
  }

  .intro {
    font-size: 1.125rem;
    color: var(--text-secondary);
    max-width: 500px;
    margin-bottom: 2rem;
  }

  .contact-links {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .contact-link {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    color: var(--text);
    font-size: 1.125rem;
    transition: color 0.2s ease;
  }

  .contact-link:hover {
    color: var(--accent);
  }

  .contact-link svg {
    flex-shrink: 0;
  }

  footer {
    padding: 2rem 0;
    text-align: center;
    border-top: 1px solid var(--border);
  }

  footer p {
    color: var(--text-secondary);
    font-size: 0.875rem;
  }
</style>
