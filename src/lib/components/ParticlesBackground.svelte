<script lang="ts">
  import Particles, { particlesInit } from '@tsparticles/svelte';
  import { loadSlim } from '@tsparticles/slim';
  import { onMount } from 'svelte';
  import type { ISourceOptions } from '@tsparticles/engine';

  const particlesConfig: ISourceOptions = {
    particles: {
      number: {
        value: 60,
        density: {
          enable: true,
          width: 1920,
          height: 1080
        }
      },
      color: {
        value: ['#3b82f6', '#60a5fa', '#93c5fd']
      },
      shape: {
        type: 'circle'
      },
      opacity: {
        value: { min: 0.3, max: 0.7 },
        animation: {
          enable: true,
          speed: 0.5,
          sync: false
        }
      },
      size: {
        value: { min: 1, max: 4 }
      },
      links: {
        enable: true,
        distance: 150,
        color: '#3b82f6',
        opacity: 0.2,
        width: 1
      },
      move: {
        enable: true,
        speed: 1,
        direction: 'none',
        random: true,
        straight: false,
        outModes: {
          default: 'bounce'
        }
      }
    },
    interactivity: {
      events: {
        onHover: {
          enable: true,
          mode: 'grab'
        },
        resize: {
          enable: true
        }
      },
      modes: {
        grab: {
          distance: 140,
          links: {
            opacity: 0.4
          }
        }
      }
    },
    detectRetina: true,
    fullScreen: {
      enable: false
    },
    background: {
      color: 'transparent'
    }
  };

  onMount(async () => {
    await particlesInit(async (engine) => {
      await loadSlim(engine);
    });
  });
</script>

<div class="particles-wrapper">
  <Particles
    id="tsparticles"
    options={particlesConfig}
  />
</div>

<style>
  .particles-wrapper {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 0;
    pointer-events: none;
  }

  .particles-wrapper :global(#tsparticles) {
    width: 100%;
    height: 100%;
  }

  .particles-wrapper :global(canvas) {
    display: block;
  }
</style>
