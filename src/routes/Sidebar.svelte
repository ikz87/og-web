<script>
	import curtain_bg from '$lib/images/curtain-bg.webp';
	import { page } from '$app/stores';
	import { flip } from 'svelte/animate';
	import { quintOut } from 'svelte/easing';
	import CaretLeftFill from "svelte-bootstrap-icons/lib/CaretLeftFill.svelte";
	import CaretRightFill from "svelte-bootstrap-icons/lib/CaretRightFill.svelte";
	import github from '$lib/images/github.svg';

	let is_sidebar_open = true;

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
		const curtain = document.getElementById('curtain');
		curtain.classList.remove('curtain-open');
		curtain.classList.add('curtain-close');
		//toggleSidebar();
		// ^ Not sure if that's good 
		setTimeout(() => {
			window.location.href = section;
			curtain.classList.add('curtain-open');
			curtain.classList.remove('curtain-close');
		}, 600)
	}

	let sections = {
		"Inicio": "Inicio",
		"Sobre-nosotros": "Sobre nosotros",
		"Servicios": "Servicios",
		"Nuestro-trabajo": "Nuestro trabajo",
		"Galeria": "Galería",
		"Equipo": "Equipo",
		"Testimonios": "Testimonios",
		"Porfolio": "Porfolio",
		"Contacto": "Contacto",
	}
</script>

<sidebar>
	<div id="curtain" class="curtain-close curtain-open bg-gray-900 border-l-8 border-green-600 fixed top-0 left-0 w-full h-full z-30">
	</div>
	<div id="sidebar" class="sidebar-open sidebar-close translate-x-[-65%] flex flex-cols-2 items-center justify-center my-button h-dvh fixed left-0 min-h-0 z-40 transition hover:opacity-100 opacity-75">
		<div class="hover:blur-none h-dvh text-xs font-bold flex flex-col justify-center bg-gray-900 opacity-100 p-4 w-16 md:w-24 text-center items-center min-h-0 border-r-4 border-green-400">
			<div class="overflow-y-auto h-dvh overflow-x-hidden align-middle box-border p-3 flex flex-col justify-center items-center">
				{#each ['Inicio', 'Sobre-nosotros', 'Servicios', 'Nuestro-trabajo', 'Galeria', 'Equipo', 'Testimonios', 'Porfolio', 'Contacto'] as name}
					<button class="my-2 hover:scale-110 my-button flex-col transition hover:bg-green-400 hover:text-green-900 rounded text-gray-300 aspect-square w-12 md:w-full flex justify-center text-center items-center p-1" 
						on:click={() => goToSection(`#${name}`)}>
						<div class="scale-[0.7] md:scale-100 md:text-xs">
							{sections[name]}
						</div>
					</button>
				{/each}
			</div>
		</div>

		{#if true}
		<button on:click={toggleSidebar} class="bg-gray-900 md:px-2 w-full border-r-4 border-y-4 border-green-400 h-24 rounded-r-xl translate-x-[-4px] z-50">
			{#if is_sidebar_open}
				<CaretLeftFill fill="white" width="16"/> 
			{:else}
				<CaretRightFill fill="white" width="16"/> 
			{/if}
		</button>
		{/if}
	</div>

</sidebar>

<style>
	@keyframes opening {
		from {transform: translateX(-75%) }
		to {transform: translateX(0) }
	}
	@keyframes closing {
		from {transform: translateX(0) }
		to {transform: translateX(-75%) }
	}
	@keyframes fading {
		from {opacity: 1}
		to {opacity: 0}
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
