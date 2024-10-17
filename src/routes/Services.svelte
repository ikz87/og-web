<script>
	import logo from '$lib/images/logo.jpeg';
	import background from '$lib/images/leaves-bg.webp';
	import X from '$lib/images/x.png';
    import Image from '$components/Image.svelte';

  export let hideModal;
  export let showModal;
</script>
<div id="Servicios" class="snap-center snap-always bg-white flex-col flex justify-center items-center h-dvh w-full">
  <!-- Fixed background image -->
  <div class="fixed top-0 grid grid-cols-3 bg-black to-fade-in left-0 h-full w-full">
    <div class="col-span-1"/>
    <img src={background} class="to-slide-right h-full w-full object-cover col-span-2 scale-110"/>
  </div>

  <!-- Modal -->
  <div id="Modal-Servicios" class="hidden">
    <div class="fixed top-0 left-0 w-full h-full z-20">
    <!-- Modal backdrop (transparent background) -->
    <div class=" w-full h-full bg-black opacity-50" on:click={() => { hideModal("Servicios") } }>
    </div>

    <!-- Modal content -->
    <div class="fixed top-1/2 left-1/2 z-30 flex -translate-x-1/2 -translate-y-1/2 items-center justify-center">
      <div id="Modal-Servicios-card" class="modal-to-slide-up p-2 w-full rounded-lg shadow-lg bg-white">
        <div class="mb-2 flex items-end justify-end">
          <button on:click={() => { hideModal("Servicios") } } class="bg-green-500 text-white p-2 rounded-full hover:bg-green-600">
            <img src={X} class="h-6 aspect-square p-1 right-0"/>
          </button>
        </div>
        <div class="text-xl gap-16 grid grid-rows-2 m-10 mt-2">
          <div class="w-full h-full">
            <p class="font-bold text-center pb-2"> Asesoramiento en agricultura sostenible y prácticas amigables con el medio ambiente </p>
            <p class="text-justify">
              El asesoramiento en agricultura sostenible y prácticas amigables con el medio ambiente es un servicio especializado que busca promover un uso responsable y consciente de los recursos naturales en el sector agrícola. Este tipo de asesoría se enfoca en implementar técnicas y métodos de cultivo que sean respetuosos con el medio ambiente, reduciendo al mínimo el impacto negativo en los ecosistemas y fomentando...
            </p>
          </div>
          <div class="w-full h-full">
            <p class="font-bold text-center pb-2">
              Planificación y diseño de sistemas de riego eficientes y sostenibles
            </p>
            <p class="text-justify">
              La planificación y diseño de sistemas de riego eficientes y sostenibles es un proceso esencial en la agricultura moderna, ya que permite optimizar el uso del agua y garantizar su disponibilidad a largo plazo. Este proceso implica la evaluación de las necesidades hídricas de los cultivos, la elección adecuada de los métodos y tecnologías de riego, y la implementación de medidas de conservación y gestión del...
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
  </div>
  
  <!-- Scrollable content -->
  <div class="relative h-dvh w-dvh overflow-y-auto z-10">
    <div class="h-full w-full grid grid-cols-3">
      <div class="flex flex-col space-y-4 items-center justify-center to-slide-right h-full w-full bg-black border-r-8 border-green-400 overflow-y-auto">
        <div class="text-4xl font-bold text-green-400 to-slide-right pb-16">
          ¿Qué ofrecemos?
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Diseño de muestreo de suelos y follar
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Diagnóstico nutricional
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Desarrollo de programa de fertilidad
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Monitoreo nutricional de cultivo
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Agricultura de precisión
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Programación de riego
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Desarrollo de productos (performance
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Uso de bioestimulantes y fertilización follar mediante la tecnología I-DRIS
        </div>
        <div class="text-xl text-white w-full px-32 text-left to-slide-right">
          • Entrenamiento a equipos con mentalidad ágil
        </div>
        <div role="button" class="text-xl hover:text-green-400 underline text-white w-full px-32 text-left to-slide-right"
          on:click={() => { showModal("Servicios") } }
        >
          Más información
        </div>
      </div>
      <div class="p-2 gap-2 col-span-2 grid w-dvh h-dvh grid-cols-6 grid-rows-6">
        <Image class="to-fade-in col-span-2 row-span-3" src="/images/services-2.webp"/>
        <Image class="to-fade-in col-span-2 row-span-3" src="/images/services-3.webp"/>
        <Image class="to-fade-in col-span-2 row-span-2" src="/images/services-4.webp"/>
        <Image class="to-fade-in col-span-2 row-span-2" src="/images/services-5.webp"/>
        <Image class="to-fade-in col-span-4 row-span-3" src="/images/services-1.webp"/>
        <Image class="to-fade-in col-span-2 row-span-2" src="/images/services-6.webp"/>
      </div>
    </div>
  </div>
</div>

<style>
  .image-shadows {
    -webkit-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
    -moz-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
    box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
  }
</style>
