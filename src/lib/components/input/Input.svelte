<script lang="ts">
	interface Props {
		value: string;
		className?: string;
		placeholder?: string;
		label?: string;
		type?: 'text' | 'email';
		isRequired?: boolean;
	}

	let { value = $bindable(), placeholder = 'Type here', label, type, isRequired }: Props = $props();
</script>

<fieldset class="fieldset">
	{#if label}
		<legend class="fieldset-legend">{label}</legend>
	{/if}
	<input
		type={type || 'text'}
		class="focus:bg-base-200 w-full rounded-md border-2 border-black p-2.5 focus:shadow-[2px_2px_0px_rgba(0,0,0,1)] focus:outline-none active:shadow-[2px_2px_0px_rgba(0,0,0,1)]"
		{placeholder}
		required={isRequired}
		bind:value
	/>
</fieldset>
