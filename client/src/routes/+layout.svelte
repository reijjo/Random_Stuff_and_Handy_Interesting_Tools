<script lang="ts">
	import { Navbar, Footer } from '$lib';

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
		grid-template-rows: 8dvh 1fr 8dvh;
		min-height: 100dvh;
		height: 100%;
		position: relative;
	}

	.content {
		height: 100%;
	}
</style>
