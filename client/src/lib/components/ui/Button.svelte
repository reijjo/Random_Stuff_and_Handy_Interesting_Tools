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

	.btn-filled {
		padding: 0.5rem 1rem;
		border: 1px solid transparent;
		border-radius: 0.5rem;
		background-color: var(--accent);
		color: white;
	}
</style>
