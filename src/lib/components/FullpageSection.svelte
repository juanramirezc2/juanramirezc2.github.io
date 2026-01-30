<script lang="ts">
  import { getContext, onMount } from "svelte";
  import type { Writable } from "svelte/store";

  interface FullpageContext {
    registerSection: (el: HTMLElement) => number;
    sectionCount: Writable<number>;
  }

  const { registerSection, sectionCount } = getContext<FullpageContext>("fullpage");

  let sectionEl: HTMLElement;
  let index = -1;

  $: isLastSection = index === $sectionCount - 1;

  function scrollToNext() {
    window.dispatchEvent(new CustomEvent("fullpage:goto", { detail: index + 1 }));
  }

  onMount(() => {
    index = registerSection(sectionEl);
  });
</script>

<section bind:this={sectionEl}>
  <slot />
  {#if !isLastSection && index >= 0}
    <button class="scroll-indicator" on:click={scrollToNext} aria-label="Scroll to next section">
      <i class="fa-solid fa-chevron-down"></i>
    </button>
  {/if}
</section>

<style>
  section {
    height: 100vh;
    scroll-snap-align: start;
    scroll-snap-stop: always;
    position: relative;
  }

  .scroll-indicator {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    animation: bounce 2s infinite;
    color: var(--text-secondary);
    font-size: 1.5rem;
    opacity: 0.7;
    cursor: pointer;
    transition: opacity 0.2s ease, color 0.2s ease;
    background: none;
    border: none;
    padding: 0.5rem;
    z-index: 10;
  }

  .scroll-indicator:hover {
    opacity: 1;
    color: var(--accent);
  }

  @keyframes bounce {
    0%, 20%, 50%, 80%, 100% {
      transform: translateX(-50%) translateY(0);
    }
    40% {
      transform: translateX(-50%) translateY(-10px);
    }
    60% {
      transform: translateX(-50%) translateY(-5px);
    }
  }

  @media (max-width: 640px) {
    .scroll-indicator {
      bottom: 1.5rem;
      font-size: 1.25rem;
    }
  }
</style>
