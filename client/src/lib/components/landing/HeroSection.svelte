<script lang="ts">
	import { onMount } from 'svelte';
	import { fly } from 'svelte/transition';
	let show = $state(false);

	onMount(() => {
		show = true;
	});
</script>

{#if show}
	<section class="hero-section wrapper" transition:fly={{ x: -1000, duration: 2000 }}>
		<div class="hero-text">
			<h1>Random Stuff and Handy Interesting Tools!</h1>
			<p>
				Check for the <a href="/recipes">recipes</a>, <a href="/todo">to-do list</a> or learn
				something about
				<a href="/ghibli">Ghibli movies</a>.
			</p>
		</div>
		<picture>
			<img src="/images/minitotoro2.png" alt="herototo" title="mini-totoro" draggable="false" />
		</picture>
	</section>
{/if}

<style>
	.hero-section {
		/* border: 1px solid red; */
		display: grid;
		/* height: 60dvh; */
		grid-template-columns: 60% 40%;
		place-items: center;
	}

	.hero-text {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 1rem;
		padding: 0 1rem;
		text-wrap: balance;
		text-align: center;
		& h1 {
			font-size: 2.5rem;
			font-weight: 700;
		}

		& p {
			font-size: 1.125rem;
		}

		& a {
			color: var(--primary-800);
			font-weight: 500;

			&:hover {
				cursor: pointer;
				font-weight: 600;
			}
		}
	}

	img {
		height: 20rem;
		will-change: transform;

		&:hover {
			animation: shake 0.4s ease-in-out;
		}
	}

	@keyframes shake {
		0% {
			transform: translate(0, 0);
		}
		20% {
			transform: translate(-2px, 2px);
		}
		40% {
			transform: translate(2px, -2px);
		}
		60% {
			transform: translate(-2px, 2px);
		}
		80% {
			transform: translate(2px, -2px);
		}
		100% {
			transform: translate(0, 0);
		}
	}
</style>
