<script>
  import BlurFadeImage from "./BlurFadeImage.svelte";
  import Icon from '@iconify/svelte';

  const projects = [
  { 
    title: "Kaizen To-Do-List", 
    image: "../public/kaizen.png", 
    description: "This project transforms the traditional to-do list into a gamified experience...",
    technologies: ["Nuxt", "Supabase", "Tailwind", "Figma"],
    url: "https://projet-kaizen.vercel.app/"  
  },
  { 
    title: "Photolio", 
    image: "../public/photolio.png", 
    description: "This platform allows photographers to create a beautiful...",
    technologies: ["Nuxt", "Supabase", "Tailwind", "Figma"],
    url: "https://photolio-dev-beta.vercel.app/login"  
  },
  { 
    title: "Ace", 
    image: "../public/ace.png", 
    description: "Description du projet 3",
    technologies: ["Figma"],
    url: "https://example.com/ace" 
  },
  { 
    title: "Kaizen V2", 
    image: "../public/kaizen.png", 
    description: "Description du projet 4",
    technologies: ["Nuxt", "Supabase", "Tailwind"],
    url: "https://example.com/kaizen-v2" 
  }
];

</script>

<BlurFadeImage duration={2.2} delay={0.8} blur="10px" class="w-full">
  <section class="flex flex-wrap justify-center gap-5 p-4">
    {#each projects as project}
      <a href={project.url} target="_blank" class="project-card group" rel="noopener noreferrer">
        <img src={project.image} alt={project.title} class="project-image group-hover:scale-105" />
        
        <div class="badges-container">
          {#each project.technologies as tech}
            <div class="badge">{tech}</div>
          {/each}
        </div>
        
        <div class="icon-container">
          <Icon icon="heroicons:arrow-up-right-16-solid" width="42" height="42" />
        </div>
        
        <div class="project-info">
          <div class="project-title">{project.title}</div>
          <div class="project-description">{project.description}</div>
        </div>
      </a>
    {/each}
  </section>
</BlurFadeImage>

<style>
  .project-card {
    @apply relative w-full sm:w-5/12 bg-white/20 backdrop-blur-lg rounded-lg overflow-hidden cursor-pointer;
  }

  .project-image {
    @apply transition-transform duration-300 ease-in-out w-full h-full object-cover;
  }

  .project-info {
    @apply absolute bottom-0 inset-x-0 p-4 text-white opacity-0 group-hover:opacity-100 transition-opacity duration-300 ease-in-out bg-gradient-to-t from-black/80 to-transparent;
  }

  .project-title {
    @apply font-bold text-xl md:text-xl lg:text-2xl;
  }

  .project-description {
    @apply opacity-70 text-sm md:text-lg lg:text-lg;
  }

  .icon-container {
    @apply absolute top-2 right-2 opacity-0 group-hover:opacity-100 transition-opacity duration-300 ease-in-out;
  }

  
  .badges-container {
    @apply absolute top-2 left-2 space-y-1 space-x-1 opacity-0 group-hover:opacity-100 transition-opacity duration-300 ease-in-out;
  }

  .badge {
    @apply inline-flex items-center justify-center rounded-full text-sm border border-neutral-800 bg-[linear-gradient(110deg,#000103,45%,#1e2631,55%,#000103)] bg-[length:200%_100%] px-3 py-1 font-medium text-neutral-400 animate-shine;
  }
</style>
