<script>
	import logo from '$lib/images/logo.jpeg';
	import background from '$lib/images/crops-bg.png';
</script>
<div id="Sobre-nosotros" class="snap-center snap-always bg-white flex-col flex justify-center items-center h-dvh w-full">
  <!-- Fixed background image -->
  <div class="fixed to-slide-down top-0 left-0 h-full w-full"  
    style="background-image: url({background}); background-size: cover; background-position: center;"></div>
  
  <!-- Scrollable content -->
  <div class="z-10 relative h-full w-full overflow-y-auto">
    <div class="flex justify-center items-center w-full">
      <div class="flex flex-col w-full items-center justify-center mt-20">
        <!-- Content Block: "¿Quiénes somos?" -->
        <div class="flex flex-row items-center justify-center">
          <div class="flex flex-col items-center justify-center to-slide-down">
            <div class="text-green-400 pb-10 font-bold flex items-center justify-center text-justify md:text-4xl text-2xl mb-[-10px]"
              style="text-shadow: black 1px 1px 6px;"
            >
              ¿Quiénes somos?
            </div>
            <div class="hidden text-black font-bold flex items-center justify-center text-justify md:text-2xl text-base mb-[-10px]">
              —————————————
            </div>
            <div class="hidden text-black font-bold flex items-center justify-center text-justify md:text-2xl text-base mb-[-10px]">
              —————————
            </div>
            <div class="hidden text-black font-bold flex items-center justify-center text-justify md:text-2xl text-base mb-[-10px]">
              —————
            </div>
          </div>
        </div>
        
        <!-- Main Paragraph -->
        <div class="flex flex-row items-center w-full justify-center pb-4 place-items-center">
          <div class="flex flex-col pr-4 items-center justify-center">
            <img src="images/ricardo.webp" class="box-shadow border-green-400 border-8 to-slide-left mt-4 md:h-64 h-32 aspect-square rounded-xl border-black "/>
            <div class="to-slide-left md:text-base text-xs md:p-4 p-2 rounded-b-xl box-shadow bg-green-400 text-center justify-center text-justify font-semibold">
              Ricardo Navarro
            </div>
          </div>
          <div class="flex flex-col pl-4 items-center justify-center">
            <img src="/images/leonel.webp" class="box-shadow border-green-400 border-8 to-slide-right mt-4 md:h-64 h-32 aspect-square rounded-xl border-black"/>
            <div class="to-slide-right md:text-base text-xs md:p-4 p-2 rounded-b-xl box-shadow bg-green-400 text-center justify-center text-justify font-semibold">
              Leonel Espinoza
            </div>
          </div>
        </div>
        
      </div>
    </div>
    
    <div class="box-shadow md:p-10 md:px-16 rounded-xl md:mx-32 md:mt-4 p-4 font-semibold mb-0 m-4 bg-black text-white md:text-xl text-sm text-justify to-slide-up">
      <p>
        Con más de cinco décadas dedicadas a la agricultura sostenible, lideramos Opti-Grow Consulting Group 
        con un enfoque firme en la innovación disruptiva y la eficiencia agrícola.
      </p>
      <br/>
      <p>
      En Opti-Grow nos dedicamos a brindar soluciones de inversión agrícola sostenibles y rentables. Con un enfoque en la tecnología y la investigación, trabajamos para maximizar los rendimientos y minimizar los riesgos en todas nuestras operaciones. Nuestro compromiso con la sostenibilidad nos impulsa a implementar prácticas agrícolas responsables y éticas para proteger el medio ambiente y garantizar un futuro próspero para las generaciones venideras.
      </p>
      <br/>
      <p>
      Nuestro equipo trabaja con el compromiso de implementar soluciones tecnológicas que se enfrentan a los retos actuales de la agricultura moderna.
      </p>
    </div>
    <div class="to-fade-in box-shadow bg-white rounded-b-xl md:p-6 p-4 md:mx-48 mx-8 mb-16">
        <!-- Additional Paragraphs -->
        <div class="to-slide-left font-semibold flex items-center justify-center text-justify md:text-xl text-sm pb-2">
          Nuestra misión es transferir conocimiento y tecnología avanzada para fortalecer la productividad agrícola y promover la sostenibilidad ambiental.
        </div>
        <div class="to-slide-right font-semibold flex items-center justify-center text-justify md:text-xl text-sm">
          Nuestra visión es llegar a posicionarnos para el 2034 dentro de las 10 empresas consultoras agrícolas de alto prestigio en el continente americano.
        </div>
      </div>
  </div>
</div>

