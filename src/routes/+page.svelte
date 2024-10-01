<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import Home from './Home.svelte';
	import About from './About.svelte';
</script>

<svelte:head>
	<title>Optigrow</title>
	<meta name="description" content="Optigrow consultorias" />
</svelte:head>

<section>
	<Home/>
	<About/>
</section>

<style>
</style>
