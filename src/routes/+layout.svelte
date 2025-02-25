<script>
	import '../app.css';

	import Header from '$lib/layout/Header.svelte';
	import Footer from '$lib/layout/Footer.svelte';
	let { children } = $props();
</script>

<main class="overflow-x-hidden">
	<Header />
	{@render children()}
	<Footer />
</main>
