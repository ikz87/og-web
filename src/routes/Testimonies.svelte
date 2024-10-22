<script>
  import { onMount } from 'svelte';
  import background from '$lib/images/leaves-words-bg.webp';
  import Injiboa from '$lib/images/injiboa.webp';
  import { Card, Button, Toggle } from 'flowbite-svelte';
  import Image from '$components/Image.svelte';
  import PlaceholderPerson from '$lib/images/placeholder-person.png'
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

<div id="Testimonios" class="snap-center snap-always bg-white justify-center items-center h-dvh w-full">
  <!-- Fixed background image -->
  <div class="fixed to-slide-down top-0 left-0 h-full w-full"  
    style="background-image: url({background}); background-size: cover; background-position: center;"></div>


  <div class="z-10 w-full h-full md:px-10 px-4 pb-10 pt-10 -verflow-y-auto">
    <div class="w-full to-slide-down text-4xl font-bold text-white text-center">
      ¿Qué opinan nuestros clientes?
    </div>
    <div class="flex flex-col gap-10 w-full h-full justify-center items-center"> 
      <div class="-ml-40 flex flex-row items-center h-44 rounded-xl card">
        <img src={ PlaceholderPerson } class="z-20 object-cover bg-white to-fade-in rounded-xl h-52 aspect-square box-shadow border-black border-8"/>
        <div class="text-white border-4 border-l-0 rounded-r-xl to-slide-right bg-black box-shadow border-green-400 p-4">
          <div class="grid grid-rows-2 w-full h-full">
            <p class="mt-3 leading-tight italic font-normal text-center">
              "Invertir en Opti-Grow ha sido la mejor decisión que he tomado en mi carrera como agricultor. Su enfoque en la sostenibilidad y la innovación ha mejorado significativamente mi rendimiento y rentabilidad. ¡Recomiendo altamente a Opti-Grow para cualquier persona que busque mejorar su producción agrícola!"
            </p>
            <div class="flex flex-row h-full items-end justify-center">
              <img src={LeafGreenL} class="to-slide-up pr-4 h-12"/>
              <div class="">
              <p class="mt-4 text-center text-2xl font-bold">Leonel Ochoa</p>
              <p class=" text-center text-base">Nicaragua</p>
              </div>
              <img src={LeafGreenR} class="to-slide-up pl-4 h-12"/>
            </div>
          </div>
        </div>
      </div>
      <div class="flex flex-row items-center h-44 rounded-xl card">
        <img src={ PlaceholderPerson } class="z-20 object-cover bg-white to-fade-in rounded-xl h-52 aspect-square box-shadow border-black border-8"/>
        <div class="text-white border-4 border-l-0 rounded-r-xl to-slide-right bg-black box-shadow border-green-400 p-4">
          <div class="grid grid-rows-2 w-full h-full">
            <p class="mt-3 leading-tight italic font-normal text-center">
              ”Como accionista de Opti-Grow, he sido testigo del increíble crecimiento y éxito de la empresa a lo largo de los años. Su dedicación a la agricultura sostenible y su enfoque en la eficiencia han atraído a muchos inversores y han hecho de Opti-Grow una de las empresas líderes en el sector."
            </p>
            <div class="flex flex-row h-full items-end justify-center">
              <img src={LeafGreenL} class="to-slide-up pr-4 h-12"/>
              <div class="">
              <p class="mt-4 text-center text-2xl font-bold">Ana Meléndez</p>
              <p class=" text-center text-base">EEUU</p>
              </div>
              <img src={LeafGreenR} class="to-slide-up pl-4 h-12"/>
            </div>
          </div>
        </div>
      </div>
      <div class="-mr-40 flex flex-row items-center h-44 rounded-xl card">
        <img src={ Injiboa } class="z-20 object-cover bg-white to-fade-in rounded-xl h-52 aspect-square box-shadow border-black border-8"/>
        <div class="text-white border-4 border-l-0 rounded-r-xl to-slide-right bg-black box-shadow border-green-400 p-4">
          <div class="grid grid-rows-2 w-full h-full">
            <p class="mt-3 leading-tight italic font-normal text-center">
              ”Opti-Grow ha sido mi socio de confianza en la agricultura durante más de 3 años. Su equipo de expertos en consultoría siempre ha proporcionado soluciones innovadoras y rentables para mejorar mi producción y reducir mi huella ambiental. No puedo imaginar mi negocio sin Opti-Grow.“
            </p>
            <div class="flex flex-row h-full items-end justify-center">
              <img src={LeafGreenL} class="to-slide-up pr-4 h-12"/>
              <div class="">
                <p class="mt-4 text-center text-2xl font-bold">Ingenio Jiboa</p>
                <p class=" text-center text-base">El Salvador</p>
              </div>
              <img src={LeafGreenR} class="to-slide-up pl-4 h-12"/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
.card {
  aspect-ratio: 30 / 5;
}
</style>
