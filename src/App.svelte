<script lang="ts">
  import FullpageContainer from "./lib/components/FullpageContainer.svelte";
  import FullpageSection from "./lib/components/FullpageSection.svelte";
  import Header from "./lib/components/Header.svelte";
  import Hero from "./lib/components/Hero.svelte";
  import About from "./lib/components/About.svelte";
  import Skills from "./lib/components/Skills.svelte";
  import Contact from "./lib/components/Contact.svelte";
  import ParticlesBackground from "./lib/components/ParticlesBackground.svelte";

  let activeSection = 0;

  function handleSectionChange(event: CustomEvent<number>) {
    activeSection = event.detail;
  }
</script>

<ParticlesBackground />
<Header {activeSection} />

<FullpageContainer on:change={handleSectionChange}>
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
</FullpageContainer>

<style>
  :global(html, body) {
    overflow: hidden;
    height: 100%;
  }
</style>
