<script>
  import { onMount } from 'svelte';
  import background from '$lib/images/library-bg.webp';
  import Image from '$components/Image.svelte';
  import LeafGreenR from '$lib/images/leaf-green-r.png';
  import LeafGreenL from '$lib/images/leaf-green-l.png';
  import Pdf from '$lib/images/pdf.png';
  import OptiGrowPresentacion from '$lib/resources/Opti-Grow Presentación.pdf';
    import { Tooltip } from 'flowbite-svelte';

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

<div id="Recursos" class="snap-center snap-always bg-white justify-center items-center h-dvh w-full">
  <div class="fixed to-slide-down top-0 left-0 h-full w-full"  
    style="background-image: url({background}); background-size: cover; background-position: center;"></div>
  <div class="z-10 w-full h-full lg:px-10 px-8 pb-10 pt-10 -verflow-y-auto flex items-center justify-center">
    <div class="relative to-slide-down flex flex-col w-full lg:mx-96 justify-center items-center"> 
      <div class="bg-white lg:p-4 p-2 text-2xl lg:text-4xl font-bold rounded-t-xl w-full flex items-center justify-center box-shadow">
        Recursos
      </div>
      <div class="relative bg-black text-white p-4 rounded-b-xl w-full h-full flex flex-col items-center box-shadow">
        <img src={LeafGreenL} class="to-slide-up absolute -top-2 -left-2 md:h-16 h-8"/>
        <img src={LeafGreenR} class="to-slide-up absolute -bottom-2 -right-2 md:h-16 h-8"/>
        <a href={OptiGrowPresentacion} target="_blank" class="hover:scale-[1.02] transition-all group hover:text-black hover:bg-green-400 rounded-xl h-24 w-full p-4 flex flex-row items-center justify-center">
          <img src="/images/presentation-thumbnail.webp" class="lg:h-16 h-12 shadow-lg rounded-xl" />
          <div class="group-hover:underline mx-3 lg:text-xl text-sm font-bold">
            Presentación Opti-Grow (PDF)
          </div>
        </a>
      </div>
    </div>
  </div>
</div>

<style>
.card {
  aspect-ratio: 30 / 5;
}
</style>
