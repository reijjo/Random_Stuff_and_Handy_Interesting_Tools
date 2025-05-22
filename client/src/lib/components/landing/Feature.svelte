<script lang="ts">
	import { fade, fly } from 'svelte/transition';

	interface Props {
		title: string;
		desc: string;
		link: string;
		linkText: string;
		imageSrc: string;
		imageAlt: string;
		reverse?: boolean;
	}

	let { title, desc, link, linkText, imageSrc, imageAlt, reverse = false }: Props = $props();
	let visible = $state(true);
</script>

{#if visible}
	<section class="feature-section" in:fly={{ y: 200, duration: 2000 }} out:fade>
		<article class="wrapper">
			<div class="feature-text {reverse ? 'reverse' : ''}">
				<h2>{title}</h2>
				<p>{desc}</p>
				<a class="btn btn-outline" href={link}>{linkText}</a>
			</div>
			<img class="feature-img" src={imageSrc} alt={imageAlt} {title} />
		</article>
	</section>
{/if}

<style>
	.feature-section {
		background-color: var(--primary-800);
		color: white;

		&:last-child {
			background-color: inherit;
			color: inherit;
		}
	}

	article {
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 2rem 0;
		max-width: 800px;
		gap: 2rem;
	}

	.feature-text {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		gap: 1rem;
		text-align: center;
		text-wrap: balance;

		& a {
			width: max-content;

			&:hover {
				color: black;
			}
		}
	}

	.reverse {
		order: 1;
	}

	.feature-img {
		width: 20rem;
	}
</style>
