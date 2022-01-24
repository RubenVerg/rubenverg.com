<script lang="ts">
	import Header from '$lib/header/Header.svelte';
	import Footer from '$lib/footer/Footer.svelte';
	import DarkMode, { store as theme } from '$lib/DarkMode.svelte';
</script>

<svelte:head>
	{#if $theme === 'light'}
		<link href='https://cdn.jsdelivr.net/npm/bootswatch@5.1.3/dist/flatly/bootstrap.min.css' rel='stylesheet' />
	{:else}
		<link href='https://cdn.jsdelivr.net/npm/bootswatch@5.1.3/dist/darkly/bootstrap.min.css' rel='stylesheet' />
	{/if}

	<link rel='stylesheet' href='https://cdn.jsdelivr.net/npm/bootstrap-icons@1.7.0/font/bootstrap-icons.css' />
</svelte:head>

<Header />

<DarkMode />

<main class='mx-5 mt-3' style='flex: 1;'>
	<slot />
</main>

<Footer />