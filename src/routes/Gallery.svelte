<script>
  import { onMount } from 'svelte';
  import background from '$lib/images/gallery-bg.webp';
  import { Gallery } from 'flowbite-svelte';
  import Image from '$components/Image.svelte';
  import LeafGreenR from '$lib/images/leaf-green-r.png';
  import LeafGreenL from '$lib/images/leaf-green-l.png';

  const images1 = [
    {src: "/images/gallery-1.webp"},
    {src: "/images/gallery-2.webp"},
    {src: "/images/gallery-3.webp"},
    {src: "/images/gallery-4.webp"},
    {src: "/images/gallery-7.webp"},
    {src: "/images/gallery-5.webp"},
  ];
  const padding = [
    {src: "/images/gallery-6.webp"},
  ];
</script>

<div id="Galeria" class="snap-center snap-always bg-white justify-center items-center h-dvh w-full">
  <!-- Fixed background image -->
  <div class="fixed to-slide-down top-0 left-0 h-full w-full"  
    style="background-image: url({background}); background-size: cover; background-position: center;"></div>

  <div class="fixed top-0 z-20 px-10 w-full">
  <div class="to-slide-down z-20 bg-black md:border-8 md:border-t-0 border-4 border-t-0 rounded-b-xl text-white border-green-400 w-full text-center flex flex-col items-center justify-center">
    <div class="flex flex-row items-center justify-center">
      <img src={ LeafGreenL } class="h-10"/>
      <div class="font-bold p-4 md:text-2xl text-xl">Galería Opti-Grow</div>
      <img src={ LeafGreenR } class="h-10"/>
    </div>
  </div>
</div>

  <div class="z-10 w-full to-slide-up h-full md:px-10 px-4 pb-10 pt-24 overflow-y-auto">

    <Gallery items={ images1 } class="gap-2 md:grid-cols-2 grid-cols-1" let:item>
        <Image src={item.src} class="" />
    </Gallery>
    <div class="w-full flex flex-col items-center justify-center">
      <Gallery items={ padding } class="gap-2 grid-cols-1" let:item>
          <Image src={item.src} class="" />
      </Gallery>
    </div>
  </div>
</div>
