<script lang="ts">
    import BlurFade from './BlurFade.svelte'; 
    import type { ComponentType } from 'svelte';
    import { clsx } from 'clsx';
    import { twMerge } from 'tailwind-merge';
  
    
    function cn(...inputs: (string | undefined)[]) {
      return twMerge(clsx(inputs));
    }
  
    export let navItems: {
      name: string;
      link: string;
      icon?: ComponentType;
    }[] = [];
  
    export let className: string | undefined = undefined;
  </script>
  
  <BlurFade
  delay={0.7}
  yOffset={10} 
  blur="10px" 
  class="flex md:hidden fixed inset-x-0 bottom-8 z-[5000] mx-auto max-w-fit items-center justify-center space-x-4 
    rounded-full backdrop-filter backdrop-blur-sm border border-transparent bg-white py-2 pl-8 pr-2 shadow-md 
    dark:border-white/[0.2] dark:bg-white/[0.04]"
>
  
  {#each navItems as navItem (`link-${navItem.name}`)}
    <a
      href={navItem.link}
      class={cn(
        'relative flex items-center space-x-1 text-neutral-600 hover:text-neutral-500 dark:text-neutral-50 dark:hover:text-neutral-300'
      )}
    >
      {#if navItem.icon}
        <svelte:component
          this={navItem.icon}
          class="block h-4 w-4 text-neutral-500 dark:text-white"
        />
      {/if}
      <span class="text-sm">{navItem.name}</span>
    </a>
  {/each}

  <button
    class="relative rounded-full border border-neutral-200 px-4 py-2 text-sm font-medium text-black 
      dark:border-white/[0.2] dark:text-white"
  >
    <span>Contact</span>
    <span
      class="absolute inset-x-0 -bottom-px mx-auto h-px w-1/2 bg-gradient-to-r from-transparent to-transparent"
    />
  </button>
</BlurFade>
