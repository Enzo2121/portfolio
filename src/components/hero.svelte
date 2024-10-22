<script>
    import Particles from './Particles.svelte';
    import BlurFade from './BlurFade.svelte'; 
    import Footer from './footer.svelte';

  </script>

  <!-- hero -->
  
  <section class="relative overflow-hidden py-36 lg:py-56 px-4 md:px-8">
    <Particles 
      className="absolute inset-0" 
      quantity={100} 
      size={0.5} 
      color="#E3F9FF" 
      refresh={true} 
    />
  
    <div class="w-full h-full rounded-full -top-12 -right-14 blur-2xl opacity-10"></div>
  
    <div class="max-w-6xl mx-auto md:text-center lg:text-center relative">
      <div class="py-4">
        <BlurFade delay={0.2}>
          <h3 class="text-[28px] text-[#EFFCFF] font-semibold md:text-6xl">
            Hey, I’m Enzo, a creative developer that enjoys building cool stuff
          </h3>
        </BlurFade>
  
        <BlurFade delay={0.3}>
          <p class="text-[#EFFCFF] lg:text-lg leading-relaxed mt-6">
            Currently a student, I love blending my passion for design with my 
            programming skills to turn my ideas into real web projects.
          </p>
        </BlurFade>
      </div>
  
      <div class="mt-5 items-center text-center justify-center gap-3 sm:flex">
        <BlurFade delay={0.5}>
          <a 
            href="" 
            class="block w-full mt-2 py-3 px-12 text-gray-700 text-lg bg-[#EFFCFF] rounded-md 
                   duration-150 hover:bg-gray-100 sm:w-auto"
          >
            My work
          </a>
        </BlurFade>
  
        <BlurFade delay={0.6}>
          <a 
            href="" 
            class="block w-full mt-2 py-3 px-12 text-gray-300 text-lg bg-gray-700 rounded-md 
                   duration-150 hover:bg-gray-800 sm:w-auto"
          >
            Contact
          </a>
        </BlurFade>

      </div>

    </div>
  </section>
  


