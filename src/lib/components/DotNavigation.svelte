<script lang="ts">
  export let activeSection: number;
  export let sectionCount: number;

  function goto(index: number) {
    window.dispatchEvent(
      new CustomEvent("fullpage:goto", { detail: index })
    );
  }
</script>

<nav class="dot-nav" aria-label="Section navigation">
  {#each Array(sectionCount) as _, i}
    <button
      class:active={activeSection === i}
      on:click={() => goto(i)}
      aria-label="Go to section {i + 1}"
      aria-current={activeSection === i ? "true" : undefined}
    />
  {/each}
</nav>

<style>
  .dot-nav {
    position: fixed;
    right: 1.5rem;
    top: 50%;
    transform: translateY(-50%);
    display: flex;
    flex-direction: column;
    gap: 1rem;
    z-index: 1000;
    padding: 0.75rem;
    background: rgba(128, 128, 128, 0.1);
    border-radius: 1rem;
    backdrop-filter: blur(4px);
  }

  button {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    border: none;
    background: rgba(255, 255, 255, 0.7);
    cursor: pointer;
    padding: 0;
    transition: all 0.3s ease;
  }

  button:hover {
    transform: scale(1.2);
    background: rgba(255, 255, 255, 0.9);
  }

  button.active {
    width: 12px;
    height: 12px;
    background: var(--accent, #3b82f6);
    box-shadow: 0 0 8px var(--accent, #3b82f6);
  }

  @media (max-width: 768px) {
    .dot-nav {
      right: 0.75rem;
      padding: 0.5rem;
    }

    button {
      width: 8px;
      height: 8px;
    }

    button.active {
      width: 10px;
      height: 10px;
    }
  }
</style>
