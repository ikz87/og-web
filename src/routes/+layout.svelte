<script>
	import Sidebar from "./Sidebar.svelte"
	import '../app.css';

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

<div class="app">
	<Sidebar {hideModal} {showModal}/>
	<main class="snap-y snap-mandatory h-dvh overflow-hidden">
		<slot {hideModal} {showModal}/>
	</main>
</div>

<style>
</style>
