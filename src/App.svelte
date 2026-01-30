<script lang="ts">
  import { Fullpage, FullpageSection } from 'svelte-fullpage';
  import { onMount } from 'svelte';
  import Header from './lib/components/Header.svelte';
  import Hero from './lib/components/Hero.svelte';
  import About from './lib/components/About.svelte';
  import Skills from './lib/components/Skills.svelte';
  import Contact from './lib/components/Contact.svelte';
  import ParticlesBackground from './lib/components/ParticlesBackground.svelte';

  let activeSection = 0;
  // eslint-disable-next-line @typescript-eslint/no-explicit-any
  let fullpageController: any;

  function handleSectionChange(event: CustomEvent) {
    activeSection = event.detail;
  }

  onMount(() => {
    const handleGoto = (event: CustomEvent) => {
      if (fullpageController) {
        fullpageController.goto(event.detail);
      }
    };

    window.addEventListener('fullpage:goto', handleGoto as EventListener);

    return () => {
      window.removeEventListener('fullpage:goto', handleGoto as EventListener);
    };
  });
</script>

<ParticlesBackground />
<Header {activeSection} />

<Fullpage
  bind:controller={fullpageController}
  arrows={false}
  drag={true}
  duration={500}
  on:change={handleSectionChange}
>
  <FullpageSection>
    <Hero />
  </FullpageSection>
  <FullpageSection>
    <About />
  </FullpageSection>
  <FullpageSection>
    <Skills />
  </FullpageSection>
  <FullpageSection>
    <Contact />
  </FullpageSection>
</Fullpage>

<style>
  :global(html, body) {
    overflow: hidden;
    height: 100%;
  }

  :global(.fullpage-container) {
    background: transparent !important;
  }

  :global(.fullpage-section) {
    background: transparent !important;
  }
</style>
