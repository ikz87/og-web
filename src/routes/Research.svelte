<script>
  import { onMount } from 'svelte';
  import background from '$lib/images/graphs-bg.webp';
  import { Carousel, Button, Indicator } from 'flowbite-svelte';
  import images from './research-carousel.json';
  import LeafGreenR from '$lib/images/leaf-green-r.png';
  import LeafGreenL from '$lib/images/leaf-green-l.png';
  let index = 0;
  let forward = true;
</script>
<div id="Research" class="snap-center snap-always bg-white justify-center items-center h-dvh w-full">
  <!-- Fixed background image -->
  <div class="fixed to-slide-down top-0 left-0 h-full w-full"  
    style="background-image: url({background}); background-size: cover; background-position: center;"></div>

  <div class="z-10 w-full h-full flex lg:flex-row flex-col items-center justify-center lg:p-0 p-2">
    <div class="to-slide-down z-20 w-full lg:ml-24 lg:p-12 p-4 bg-black text-white lg:text-xl text-sm text-justify border-white box-shadow rounded-xl">
      <img src={LeafGreenL} class="absolute to-slide-up -bottom-2 -left-2 lg:h-16 h-8"/>
      <img src={LeafGreenR} class="absolute to-slide-up -top-2 -right-2 lg:h-16 h-8"/>
      En Opti-Grow nos dedicamos a brindar a nuestros clientes herramientas e información de vanguardia para optimizar la productividad agrícola. Nuestro equipo de expertos utiliza tecnologías avanzadas y modelos predictivos para evaluar variables críticas durante diferentes etapas de crecimiento. A través de la recolección y análisis de datos ayudamos a los agricultores a tomar decisiones informadas que mejoran directamente el rendimiento, la eficiencia y la sostenibilidad de los cultivos.
    </div>
    <div class="to-slide-right h-full w-full lg:p-2 pt-2 p-0 items-center justify-center">
      <div class="h-full w-full py-4 -my-4 flex justify-center">
      <Carousel {images} let:Indicators let:Controls 
        style="
        height: 100%;
        aspect-ratio: 12/16;"
        class="lg:border-8 border-4 z-20 border-black box-shadow"
        imgClass="z-20"
        >
          <Controls class="z-20 -mx-16"/>
          <Indicators let:selected let:index class="lg:translate-y-14 translate-y-16 box-shadow rounded-b-xl p-4 bg-black">
             <Indicator class="z-10 {selected ? 'scale-150' : 'scale-100 opacity-50'}">
      </Indicator>
          </Indicators>
</Carousel>
  </div>
  </div>
  </div>
  </div>

