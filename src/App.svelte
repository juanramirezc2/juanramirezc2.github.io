<script lang="ts">
  import Header from './lib/components/Header.svelte'
  import Hero from './lib/components/Hero.svelte'
  import About from './lib/components/About.svelte'
  import Skills from './lib/components/Skills.svelte'
  import Contact from './lib/components/Contact.svelte'
</script>

<Header />
<main>
  <Hero />
  <About />
  <Skills />
  <Contact />
</main>

<style>
  main {
    min-height: 100vh;
  }
</style>
