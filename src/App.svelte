<script>
  import Navbar from './components/floating.svelte';
  import Hero from './components/hero.svelte';
  import Spotlight from './components/spotlight.svelte';
  import ProjectCard from './components/projectCard.svelte';
  import MobileNav from './components/mobileNav.svelte';
  

  const navItems = [
    { name: 'Home', link: '#' },
    { name: 'Projects', link: '#' },
    { name: 'About me', link: '#' },
  ];
</script>

<main class="bg-[#01010D] text-white h-full flex flex-col items-center justify-center  w-full bg-slate-950  bottom-0 left-0 right-0 top-0 bg-[linear-gradient(to_right,#4f4f4f2e_1px,transparent_1px),linear-gradient(to_bottom,#4f4f4f2e_1px,transparent_1px)] bg-[size:5px_5px]">
   
  <Spotlight className="-top-40 left-0 md:left-60 md:-top-20" fill="#62E0FF" />

  
  <Navbar {navItems} />
  <MobileNav {navItems} />

  <div>
    <Hero />
  </div>

  <div>
    <ProjectCard />
  </div>


</main>






