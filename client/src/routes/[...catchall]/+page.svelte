<script lang="ts">
	import { page } from '$app/state';
</script>

<main>
	<h1 class="not-found-header">Ooops... I think that you're lost!</h1>
	<div class="not-found-container">
		<figure>
			<picture>
				<img src="/images/lost.jpg" alt="lost" title="lost" />
			</picture>
			<figcaption>Page <span>{page.url.pathname.slice(1)}</span> not found.</figcaption>
		</figure>
		<a href="/" class="btn btn-outline">Back to Homepage</a>
	</div>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%;
		gap: 2rem;
	}

	.not-found-container {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		width: 20rem;
	}

	figure {
		width: 100%;
		margin: 0;
		text-align: center;

		& span {
			font-weight: 600;
		}
	}

	img {
		width: 100%;
		object-fit: cover;
		border-radius: 0.5rem;
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.25);
	}
</style>
