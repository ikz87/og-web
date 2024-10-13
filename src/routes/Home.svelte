<script>
	import logo from '$lib/images/logo.jpeg';
    import { onMount } from 'svelte';

  onMount(() => {
    console.log("mounted");
    const home_div = document.getElementById("Inicio");

	function triggerAnims(div) {
		div.classList.forEach(className => {
			if (className.startsWith('to-slide-')) {
				// Get the direction (left, right, up, down)
				const direction = className.split('to-slide-')[1];

				// Replace 'to-slide-' with 'slide-' and update the class
				div.classList.add(className, `slide-${direction}`);
			}
		});
		[...div.children].forEach(child => {
			triggerAnims(child)
		});
	}
    triggerAnims(home_div)
  });
</script>

<div id="Inicio" class="snap-center snap-always bg-white h-dvh flex-col flex justify-center items-center md:pb-40 pb-32" style="">
  <div class="justify-center z-10">
    <div class="relative h-full w-full to-slide-down max-w-xl">
      <img class="w-full" src={logo} style="aspect-ratio: 6 / 5;" />
    </div>
    <div class="text-black to-slide-down text-center md:mt-[-9%] mt-[-10%] md:text-2xl text-lg">
      Innovación Disruptiva
    </div>
    <div class="grid grid-cols-2 mt-10 md:text-base text-sm">
    <p class="text-center w-full to-slide-right">Ricardo Navarro. MsC</p> 
    <p class="text-center w-full to-slide-left">Leonel Espinoza. Ph.D</p> 
    <p class="text-center w-full to-slide-right md:inline hidden">ricardon@optigrowinvest.com</p> 
    <p class="text-center w-full to-slide-left md:inline hidden">leonele@optigrowinvest.com</p> 
    </div>
  </div>
</div>
