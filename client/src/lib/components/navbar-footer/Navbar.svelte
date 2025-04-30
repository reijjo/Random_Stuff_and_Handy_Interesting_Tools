<script>
	import Button from '../ui/Button.svelte';
</script>

<nav>
	<div class="wrapper">
		<a href="/">home</a>
		<Button className="btn-filled">Im a button</Button>
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
</style>
