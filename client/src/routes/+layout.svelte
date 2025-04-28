<script lang="ts">
	import Footer from '$lib/components/navbar-footer/Footer.svelte';
	import Navbar from '$lib/components/navbar-footer/Navbar.svelte';

	let { children } = $props();
</script>

<div class="layout">
	<Navbar />
	<div class="content">
		{@render children()}
	</div>
	<Footer />
</div>

<style>
	.layout {
		display: grid;
		grid-template-rows: 10dvh 1fr 10dvh;
		height: 100dvh;
	}

	.content {
		height: 100%;
	}
</style>
