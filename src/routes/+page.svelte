<script>
	import Home from './Home.svelte';
	import About from './About.svelte';
	import Services from './Services.svelte';
	import Research from './Research.svelte';
	import Gallery from './Gallery.svelte';
	import Testimonies from './Testimonies.svelte';
	import Contact from './Contact.svelte';

	function showModal(section) {
		const modal = document.getElementById("Modal-"+section);
		if (!modal) { return };
		modal.classList.remove("hidden");
		setTimeout(() =>{
			document.getElementById("Modal-"+section+"-card").classList.add("slide-up");

    }, 0)
	}

	function hideModal(section) {
		const modal = document.getElementById("Modal-"+section);
		if (!modal) { return };
		document.getElementById("Modal-"+section+"-card").classList.remove("slide-up");
		setTimeout(() =>{
			modal.classList.add("hidden"); 
		}, 500)
	}
</script>

<svelte:head>
	<title>Opti-Grow</title>
	<meta name="description" content="Optigrow consultorias" />
</svelte:head>

<section>
	<Home/>
	<About/>
	<Services {hideModal} {showModal}/>
	<Research/>
	<Gallery/>
	<Testimonies/>
	<Contact/>
</section>
