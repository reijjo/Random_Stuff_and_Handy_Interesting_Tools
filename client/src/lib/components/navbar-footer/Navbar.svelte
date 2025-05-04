<script>
	import Button from '../ui/Button.svelte';
</script>

<nav>
	<div class="wrapper">
		<a href="/">home</a>
		<div class="nav-buttons">
			<Button className="btn-outline">Im a OUTLINE button</Button>
			<Button className="btn-filled">Im a FILLED button</Button>
		</div>
	</div>
</nav>

<style>
	nav {
		height: auto;
		border: 1px solid red;
		display: flex;

		& > div {
			display: inherit;
			align-items: center;
			justify-content: space-between;
		}
	}

	.nav-buttons {
		display: flex;
		gap: 1rem;
	}
</style>
