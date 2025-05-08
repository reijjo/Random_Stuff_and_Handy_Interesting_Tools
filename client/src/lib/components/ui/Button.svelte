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
</style>
