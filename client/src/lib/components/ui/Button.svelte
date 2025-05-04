<script lang="ts">
	type ButtonProps = {
		type?: 'button' | 'submit' | 'reset';
		className?: string;
		style?: string;
		disabled?: boolean;
		children: any;
	};

	let { type = 'button', className, style, disabled = false, children }: ButtonProps = $props();
</script>

<button class={`btn ${className}`} {type} {style} {disabled}>{@render children()}</button>

<style>
	button {
		all: unset;
	}

	.btn {
		cursor: pointer;
		text-align: center;
	}

	.btn-filled,
	.btn-outline {
		padding: 0.5rem 1rem;
		border-radius: 0.5rem;

		&:active {
			scale: 0.975;
		}
	}

	.btn-filled {
		border: 1px solid transparent;

		background-color: var(--accent);
		color: white;
		box-shadow: var(--btn-shadow);

		&:hover {
			background-color: var(--accent-700);
		}
	}

	.btn-outline {
		border: 1px solid var(--accent);

		&:hover {
			background-color: var(--accent-50);
		}
	}
</style>
