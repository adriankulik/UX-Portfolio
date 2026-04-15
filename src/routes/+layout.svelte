<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import '../app.css';
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<!-- Global Fonts & CSS Imports (Derived from DESIGN.md) -->
	<link
		href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;500;700;800&family=Newsreader:ital,opsz,wght@0,6..72,400;0,6..72,500;1,6..72,400&display=swap"
		rel="stylesheet"
	/>
	<link
		href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<!-- Background/Container wrapper for global styles -->
<div
	class="min-h-screen bg-surface text-on-surface selection:bg-primary-container selection:text-on-primary-container"
>
	<!-- TopAppBar / Header Component -->
	<Header />

	<main class="pt-24 pb-24 relative">
		<!-- Slot for page specific content -->
		<div class="max-w-7xl mx-auto px-6 lg:px-12 pt-12">
			<slot />
		</div>
	</main>

	<!-- Footer Component -->
	<Footer />
</div>
