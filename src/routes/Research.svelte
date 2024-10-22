<script>
  import { onMount } from 'svelte';
  import background from '$lib/images/graphs-bg.webp';
  import { Carousel, Thumbnails, Button, Indicator } from 'flowbite-svelte';
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

  <div class="z-10 w-full h-full flex flex-row items-center justify-center">
    <div class="to-slide-left z-20 w-full ml-24 mr-0 p-12 bg-black text-white text-xl text-justify border-white box-shadow rounded-xl">
      <img src={LeafGreenL} class="absolute to-slide-up -bottom-2 -left-2 h-16"/>
      <img src={LeafGreenR} class="absolute to-slide-up -top-2 -right-2 h-16"/>
      En Opti-Grow nos dedicamos a brindar a nuestros clientes herramientas e información de vanguardia para optimizar la productividad agrícola. Nuestro equipo de expertos utiliza tecnologías avanzadas y modelos predictivos para evaluar variables críticas durante diferentes etapas de crecimiento. A través de la recolección y análisis de datos ayudamos a los agricultores a tomar decisiones informadas que mejoran directamente el rendimiento, la eficiencia y la sostenibilidad de los cultivos.
    </div>
    <div class="to-slide-right h-full w-full p-2 items-center justify-center">
      <div class="h-full w-full py-4 -my-4 flex justify-center">
      <Carousel {images} let:Indicators let:Controls 
        style="
        height: 100%;
        aspect-ratio: 12/16;"
        class="border-8 z-20 border-black box-shadow"
        imgClass="z-20"
        >
          <Controls class="z-20 -mx-16"/>
          <Indicators let:selected let:index class="translate-y-14 box-shadow rounded-b-xl p-4 bg-black">
             <Indicator class="z-10 {selected ? 'scale-150' : 'scale-100 opacity-50'}">
      </Indicator>
          </Indicators>
</Carousel>
  </div>
  </div>
  </div>
  </div>

