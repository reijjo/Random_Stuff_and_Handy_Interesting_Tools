<script lang="ts">
	import '$lib/components/ui/ui-styles.css';
</script>

<nav aria-label="navigation">
	<div class="wrapper nav-links">
		<div class="nav-logo">
			<a href="/">SHIT</a>
		</div>
		<div class="nav-pages-links">
			<a href="/">To-do List</a>
			<a href="/ghibli">Ghibli</a>
			<a href="/recipes">Recipes</a>
		</div>
		<div class="nav-button-links" role="group">
			<a href="/login" class="btn btn-outline">Login</a>
			<a href="/register" class="btn btn-filled">Register</a>
		</div>
	</div>
</nav>

<style>
	nav {
		height: auto;
		border: 1px solid red;
		display: flex;

		/* & > div {
			display: inherit;
			align-items: center;
			justify-content: space-between;
		} */
	}

	.nav-logo {
		justify-self: start;
	}

	.nav-links {
		display: grid;
		grid-template-columns: 1fr auto 1fr;
		align-items: center;
	}

	.nav-pages-links {
		display: flex;
		gap: 2rem;
		text-transform: uppercase;
		letter-spacing: 0.1rem;
		font-weight: 500;

		& a {
			transition: all 0.125s ease-out;
		}

		& a:hover {
			color: var(--primary-600);
			scale: 1.125;
		}
	}

	.nav-button-links {
		display: flex;
		gap: 1rem;
		justify-self: end;
	}
</style>
