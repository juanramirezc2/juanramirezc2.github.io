<script lang="ts">
  import { getContext, onMount } from "svelte";

  const registerSection = getContext<(el: HTMLElement) => void>("registerSection");

  let sectionEl: HTMLElement;

  onMount(() => {
    if (registerSection) {
      registerSection(sectionEl);
    }
  });
</script>

<section bind:this={sectionEl}>
  <slot />
</section>

<style>
  section {
    height: 100vh;
    scroll-snap-align: start;
    scroll-snap-stop: always;
  }
</style>
