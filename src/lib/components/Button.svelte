<script lang="ts">
	type ButtonType =
		| 'primary'
		| 'secondary'
		| 'default'
		| 'success'
		| 'danger'
		| 'warning'
		| 'info'
		| 'light'
		| 'dark';

	const buttonType: Record<ButtonType, string> = {
		primary: 'btn-primary hover:text-primary',
		secondary: 'btn-secondary hover:text-secondary',
		success: 'btn-success hover:text-success',
		danger: 'btn-danger hover:text-danger',
		warning: 'btn-warning hover:text-warning',
		info: 'btn-info hover:text-info',
		light: 'btn-light hover:text-light',
		dark: 'btn-dark hover:text-dark',
		default: 'btn-default hover:text-gray-100'
	};

	interface Props {
		isSubmit?: boolean;
		type?: ButtonType;
		disabled?: boolean;
		loading?: boolean;
		children: import('svelte').Snippet;
		onclick?: () => void;
		className?: string;
	}

	let {
		type = 'default',
		disabled = false,
		loading = false,
		onclick,
		children,
		isSubmit,
		className
	}: Props = $props();
</script>

<button
	{onclick}
	class={`btn
    h-12 rounded-md border-2 border-black p-2.5
    shadow-[4px_4px_0px_rgba(0,0,0,1)]
    ${buttonType[type] || buttonType.default} hover:bg-neutral ${className || ''}`}
	disabled={disabled || loading}
	type={isSubmit ? 'submit' : 'button'}
>
	{#if loading}
		<span class="loader"></span>
	{:else}
		{@render children()}
	{/if}
</button>
