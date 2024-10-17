<script>
	import curtain_bg from '$lib/images/curtain-bg.webp';
	import icon_white from '$lib/images/icon-white.png';
	import icon_green from '$lib/images/icon-green.png';
	import icon_black from '$lib/images/icon-black.png';
	import { page } from '$app/stores';
	import { flip } from 'svelte/animate';
	import { quintOut } from 'svelte/easing';
	import CaretLeftFill from "svelte-bootstrap-icons/lib/CaretLeftFill.svelte";
	import CaretRightFill from "svelte-bootstrap-icons/lib/CaretRightFill.svelte";
	import github from '$lib/images/github.svg';

	export let hideModal;
	export let showModal;

	let is_sidebar_open = true;
	let curr_section = "Inicio";

	function toggleSidebar() {
		is_sidebar_open = is_sidebar_open? false : true 
		const sidebar = document.getElementById('sidebar');
		if (is_sidebar_open) {
			sidebar.classList.add('sidebar-open');
			sidebar.classList.remove('sidebar-close');
		} else {
			sidebar.classList.remove('sidebar-open');
			sidebar.classList.add('sidebar-close');
		}
	}

	function goToSection(section) {
		if (section === curr_section) { return };
		resetAnims(document.getElementById(curr_section));
		hideModal(curr_section);
		curr_section = section;
		const curtain = document.getElementById('curtain');
		const section_div = document.getElementById(section);
		curtain.classList.remove('curtain-open');
		curtain.classList.add('curtain-close');
		//toggleSidebar();
		// ^ Not sure if that's good 
		setTimeout(() => {
			hideUnfocusedSections();
			document.getElementById(section).classList.remove('hidden');
			window.location.href = "#"+section;
			triggerAnims(section_div);
			curtain.classList.add('curtain-open');
			curtain.classList.remove('curtain-close');
		}, 500)
	}

	function triggerAnims(div) {
		div.classList.forEach(className => {
			if (className.startsWith('to-slide-')) {
				// Get the direction (left, right, up, down)
				const direction = className.split('to-slide-')[1];

				// Replace 'to-slide-' with 'slide-' and update the class
				div.classList.add(className, `slide-${direction}`);
			}
            else if (className.startsWith('to-fade-')) {
				div.classList.add(className, `fade-in`);
			}
		});
      [...div.children].forEach((child, index) => {
        setTimeout(() => {
          triggerAnims(child);
        }, 200 * index); // Delay increases with each child (100ms * index)
      });
	}

	function resetAnims() {
       // Select all elements in the document
  const allElements = document.querySelectorAll('*'); // Selects all elements

  // Iterate over each element
  allElements.forEach(element => {
    // Create an array from the classList and filter for classes starting with 'slide-' or 'fade-'
    const classesToRemove = Array.from(element.classList).filter(className => 
      className.startsWith('slide-') || className.startsWith('fade-')
    );
    
    // Remove each filtered class from the element
    classesToRemove.forEach(className => {
      element.classList.remove(className);
    });
  });
}

	let sections = {
		"Inicio": "Inicio",
		"Sobre-nosotros": "Sobre nosotros",
		"Servicios": "Servicios",
		"Research": "Research",
		"Galeria": "Galería",
		"Equipo": "Equipo",
		"Testimonios": "Testimonios",
		"Porfolio": "Porfolio",
		"Contacto": "Contacto",
	}

	function hideUnfocusedSections () {
		for (const section in sections) {
			const section_div = document.getElementById(section);
			if (!section_div) { continue };
			if (!section_div.classList.contains('hidden')) {
				section_div.classList.add('hidden');
			}
		}
	}
</script>

<sidebar>
	<div id="curtain" class="hidden curtain-close curtain-open bg-black border-l-8 border-green-400 fixed top-0 left-0 w-full h-full z-30">
	</div>
	<div id="sidebar" class="sidebar-open sidebar-close translate-x-[-65%] flex flex-cols-2 items-center justify-center my-button h-dvh fixed left-0 min-h-0 z-40 transition duration-200 hover:opacity-100 opacity-40">
		<div class="hover:blur-none h-dvh text-xs font-bold flex flex-col justify-center bg-black opacity-100 p-4 w-16 md:w-24 text-center items-center min-h-0 border-r-4 border-green-400">
			<div class="overflow-y-auto h-dvh overflow-x-hidden align-middle box-border p-3 flex flex-col justify-center items-center">
				{#each ['Inicio', 'Sobre-nosotros', 'Servicios', 'Research', 'Galeria', 'Equipo', 'Testimonios', 'Porfolio', 'Contacto'] as name}
					<button class="my-2 hover:scale-110 my-button flex-col transition hover:bg-green-400 hover:text-black rounded text-white aspect-square w-12 md:w-full flex justify-center text-center items-center p-1" 
						on:click={() => goToSection(`${name}`)}>
						{#if name != "Inicio"}
							{#if name === curr_section}
								<div class="h-full w-full flex items-center justify-center text-green-400 hover:text-black">
									<div class="scale-[0.7] md:scale-100 md:text-xs">
										{sections[name]}
									</div>
								</div>
							{:else}
								<div class="scale-[0.7] md:scale-100 md:text-xs">
									{sections[name]}
								</div>
							{/if}
						{:else}
							{#if name === curr_section}
								<img src={icon_black} class="transition"/>
								<img src={icon_green} class="mt-[-95%] hover:opacity-0 transition"/>
							{:else}
								<img src={icon_black} class="transition"/>
								<img src={icon_white} class="mt-[-95%] hover:opacity-0 transition"/>
							{/if}
						{/if}
					</button>
				{/each}
			</div>
		</div>

		{#if true}
		<button on:click={toggleSidebar} class="bg-black md:px-2 w-full border-r-4 border-y-4 border-green-400 h-48 rounded-r-xl translate-x-[-4px] z-50">
			{#if is_sidebar_open}
				<CaretLeftFill fill="white" width="24"/> 
			{:else}
				<CaretRightFill fill="white" width="24"/> 
			{/if}
		</button>
		{/if}
	</div>

</sidebar>

<style>
	@keyframes opening {
		from {transform: translateX(-70%) }
		to {transform: translateX(0) }
	}
	@keyframes closing {
		from {transform: translateX(0) }
		to {transform: translateX(-70%) }
	}
	@keyframes curtain-opening {
		from {transform: translateX(0) }
		to {transform: translateX(100%) }
	}
	@keyframes curtain-closing {
		from {transform: translateX(100%) }
		to {transform: translateX(0) }
	}

	.sidebar-close {
		animation: closing 0.3s alternate ease-in-out forwards;
	}
	.sidebar-open {
		animation: opening 0.3s alternate ease-in-out forwards;
	}
	.curtain-close {
		animation: curtain-closing 0.5s alternate ease-in-out forwards;
	}
	.curtain-open {
		animation: curtain-opening 0.5s alternate ease-in-out forwards;
	}
</style>
