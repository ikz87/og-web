<script>
	import logo from '$lib/images/logo.jpeg';
    import { onMount } from 'svelte';
    import { Tooltip } from 'flowbite-svelte';

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
  const contacts = {
    "name": {
      "ricardo": "Ricardo Navarro",
      "leonel": "Leonel Espinoza",
      "icon": "/images/person-icon.png",
    },
    "email": {
      "ricardo": "ricardon@optigrowinvest.com",
      "leonel": "leonele@optigrowinvest.com",
      "icon": "/images/email-icon.png",
    },
    "phone": {
      "ricardo": "+ (505) 5807-1062",
      "leonel": "+ 1 (501) 837-8693",
      "icon": "/images/phone-icon.png",
    }
  }
</script>

<div id="Contacto" class="snap-center snap-always bg-white h-dvh flex-col flex justify-center items-center" style="">
  <div class="flex flex-col justify-center items-center w-full h-full">
    <div class="fixed to-slide-down top-16 text-center font-bold md:text-4xl text-2xl">
      ¡Contáctanos!
    </div>
    <div class="flex md:scale-100 scale-[0.85] flex-col justify-center items-center h-full">
      <div class="flex flex-row items-center justify-center gap-10">
        <img src="/images/ricardo.webp" class="to-slide-right md:h-48 h-24 aspect-square surrounding-shadow rounded-full"/>
        <div class="md:h-64 md:w-20 h-32 w-10 bg-black rounded-t-full to-slide-down surrounding-shadow">
        </div>
        <img src="/images/leonel.webp" class="to-slide-right md:h-48 h-24 aspect-square surrounding-shadow rounded-full"/>
      </div>
      {#each Object.entries(contacts) as [contact, entries]}
        <div class="flex flex-row items-center font-semibold justify-center">
          <div role="button" class="bg-white to-slide-left active:bg-gray-200 md:border-4 md:border-r-0 border-2 border-black border-r-0 text-center md:w-[17rem] w-48 md:text-base text-xs md:p-2 p-[2px] rounded-l-full"
            on:click={() => {navigator.clipboard.writeText(entries["ricardo"])}}
          >
            {entries["ricardo"]}
          </div>
          <Tooltip>Clic para copiar</Tooltip>
          <div class="z-10 h-full to-slide-down md:p-4 p-2 md:w-20 w-10 bg-black surrounding-shadow flex items-center justify-center">
            <img src={entries.icon} class="md:w-12 w-6 aspect-square"/>
          </div>
          <div role="button" class="bg-white to-slide-right active:bg-gray-200 md:border-4 md:border-l-0 border-2 border-black border-l-0 text-center md:w-[17rem] w-48 md:text-base text-xs md:p-2 p-[2px] rounded-r-full"
            on:click={() => {navigator.clipboard.writeText(entries["leonel"])}}
          >
            {entries["leonel"]}
          </div>
          <Tooltip>Clic para copiar</Tooltip>
        </div>
      {/each}
          <div class="z-10 h-20 p-4 md:w-20 w-10 bg-black to-slide-down surrounding-shadow flex items-center justify-center rounded-b-full">
          </div>
    </div>
  </div>
</div>

<style>
  .surrounding-shadow {
    -webkit-box-shadow: 0px 0px 24px 0px rgba(0,0,0,0.75);
    -moz-box-shadow: 0px 0px 24px 0px rgba(0,0,0,0.75);
    box-shadow: 0px 0px 24px 0px rgba(0,0,0,0.75);
  }
  </style>
