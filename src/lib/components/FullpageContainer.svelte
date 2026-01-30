<script lang="ts">
  import { setContext, onMount, onDestroy, createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher<{ change: number }>();

  let containerEl: HTMLElement;
  let sections: HTMLElement[] = [];
  let observer: IntersectionObserver;

  setContext("registerSection", (el: HTMLElement) => {
    sections = [...sections, el];
  });

  function goto(index: number) {
    if (sections[index]) {
      sections[index].scrollIntoView({ behavior: "smooth" });
    }
  }

  function handleGotoEvent(event: Event) {
    const customEvent = event as CustomEvent<number>;
    goto(customEvent.detail);
  }

  onMount(() => {
    observer = new IntersectionObserver(
      (entries) => {
        for (const entry of entries) {
          if (entry.isIntersecting) {
            const index = sections.indexOf(entry.target as HTMLElement);
            if (index !== -1) {
              dispatch("change", index);
            }
          }
        }
      },
      {
        root: containerEl,
        threshold: 0.5,
      }
    );

    // Observe sections after a tick to ensure they're registered
    setTimeout(() => {
      sections.forEach((section) => observer.observe(section));
    }, 0);

    window.addEventListener("fullpage:goto", handleGotoEvent);

    return () => {
      observer.disconnect();
      window.removeEventListener("fullpage:goto", handleGotoEvent);
    };
  });

  onDestroy(() => {
    if (observer) {
      observer.disconnect();
    }
  });
</script>

<div class="fullpage-container" bind:this={containerEl}>
  <slot />
</div>

<style>
  .fullpage-container {
    height: 100vh;
    overflow-y: scroll;
    scroll-snap-type: y mandatory;
    scroll-behavior: smooth;

    /* Hide scrollbar - Chrome, Safari, Opera */
    -ms-overflow-style: none;
    scrollbar-width: none;
  }

  .fullpage-container::-webkit-scrollbar {
    display: none;
  }
</style>
