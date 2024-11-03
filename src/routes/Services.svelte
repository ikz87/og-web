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
    <img src={background} class="to-slide-right h-full w-full object-cover col-span-3 scale-110"/>
  </div>

  <!-- Modal -->
  <div id="Modal-Servicios" class="hidden">
    <div class="fixed top-0 left-0 w-full h-full z-20">
    <!-- Modal backdrop (transparent background) -->
    <div class=" w-full h-full bg-black opacity-50" on:click={() => { hideModal("Servicios") } }>
    </div>

    <!-- Modal content -->
    <div class="fixed top-1/2 left-1/2 z-30 flex -translate-x-1/2 -translate-y-1/2 items-center justify-center">
      <div id="Modal-Servicios-card" class="modal-to-slide-up md:p-2 md:w-full w-64 rounded-lg shadow-lg bg-white">
        <div class="m-1 flex items-end justify-end">
          <button on:click={() => { hideModal("Servicios") } } class="bg-green-400 text-white p-2 rounded-full hover:bg-green-600">
            <img src={X} class="md:h-6 h-2 aspect-square md:p-1 p-0 right-0"/>
          </button>
        </div>
        <div class="md:text-xl text-xs md:gap-10 gap-4 flex flex-col items-center justify-center md:m-10 md:mt-2 m-2 mt-2">
          <div class="w-full h-full">
            <p class="font-bold text-center pb-2"> Asesoramiento en agricultura sostenible y prácticas amigables con el medio ambiente </p>
            <p class="text-justify">
              El asesoramiento en agricultura sostenible y prácticas amigables con el medio ambiente es un servicio especializado que busca promover un uso responsable y consciente de los recursos naturales en el sector agrícola. Este tipo de asesoría se enfoca en implementar técnicas y métodos de cultivo que sean respetuosos con el medio ambiente, reduciendo al mínimo el impacto negativo en los ecosistemas y fomentando una producción más equilibrada y eficiente a largo plazo.
            </p>
          </div>
          <div class="w-full h-full">
            <p class="font-bold text-center pb-2">
              Planificación y diseño de sistemas de riego eficientes y sostenibles
            </p>
            <p class="text-justify">
              La planificación y diseño de sistemas de riego eficientes y sostenibles es un proceso esencial en la agricultura moderna, ya que permite optimizar el uso del agua y garantizar su disponibilidad a largo plazo. Este proceso implica la evaluación de las necesidades hídricas de los cultivos, la elección adecuada de los métodos y tecnologías de riego, y la implementación de medidas de conservación y gestión del agua que promuevan una mayor productividad. Con un enfoque en la sostenibilidad, estos sistemas permiten a los agricultores adaptarse mejor a los desafíos climáticos y mejorar la resiliencia de sus cosechas.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
  </div>
  
  <!-- Scrollable content -->
  <div class="relative h-screen w-dvh overflow-y-auto z-10">
    <div class="h-full w-full flex lg:flex-row flex-col">
      <div class="flex flex-col space-y-4 items-center justify-center to-slide-right h-full w-full bg-black lg:border-r-8 border-b-4 border-green-400 lg:row-span-3 lg:col-span-1 col-span-3 row-span-1 box-shadow">
        <div class="pt-4 md:text-4xl text-2xl font-bold text-green-400 to-slide-right md:pb-16 pb-2">
          ¿Qué ofrecemos?
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Diseño de muestreo de suelos y follar
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Diagnóstico nutricional
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Desarrollo de programa de fertilidad
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Monitoreo nutricional de cultivo
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Agricultura de precisión
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Programación de riego
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Desarrollo de productos (performance)
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Uso de bioestimulantes y fertilización follar mediante la tecnología I-DRIS
        </div>
        <div class="md:text-xl text-base text-white w-full md:px-32 px-6 text-left to-slide-right">
          • Entrenamiento a equipos con mentalidad ágil
        </div>
        <div role="button" class="md:text-xl py-6 text-base hover:text-green-400 underline text-white w-full md:px-32 px-6 text-left to-slide-right"
          on:click={() => { showModal("Servicios") } }
        >
          Más información
        </div>
      </div>
      <div class="lg:p-2 lg:gap-2 lg:col-span-2 lg:row-span-3 row-span-2 col-span-3 grid w-full lg:h-dvh h-full grid-cols-6 grid-rows-6">
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
