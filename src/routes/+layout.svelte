<script>
	import Sidebar from "./Sidebar.svelte"
	import '../app.css';
</script>

<div class="app">
	<Sidebar/>
	<main class="snap-y snap-mandatory h-dvh overflow-auto">
		<slot />
	</main>
</div>

<style>
</style>
