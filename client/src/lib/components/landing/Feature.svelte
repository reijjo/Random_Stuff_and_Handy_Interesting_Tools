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
		<article class="wrapper feature-article {reverse ? 'reverse' : ''}">
			<div class="feature-text">
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
		width: 100%;
		height: 50dvh;

		&:nth-child(odd) {
			background-color: inherit;
			color: inherit;
		}
	}

	.feature-article {
		display: grid;
		grid-template-areas: 'text image';
		grid-template-columns: 1fr 2fr;
		padding-block: 2rem;
		height: 100%;
		gap: 2rem;

		&.reverse {
			grid-template-areas: 'image text';
			grid-template-columns: 2fr 1fr;
		}
	}

	.feature-text {
		grid-area: text;
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

	.feature-img {
		grid-area: image;
		width: 100%;
		height: 100%;
		object-fit: fill;
		overflow: hidden;
	}
</style>
