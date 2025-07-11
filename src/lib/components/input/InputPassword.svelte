<script lang="ts">
	import { Eye, EyeOff } from '@lucide/svelte';

	interface Props {
		value: string;
		placeholder?: string;
		label?: string;
	}

	let { value = $bindable(), placeholder = 'Type here', label }: Props = $props();
	let visible = $state(false);
</script>

<fieldset class="fieldset">
	{#if label}
		<legend class="fieldset-legend">{label}</legend>
	{/if}
	<div class="relative">
		<input
			type={visible ? 'text' : 'password'}
			class="focus:bg-base-200 w-full rounded-md border-2 border-black p-2.5 focus:shadow-[2px_2px_0px_rgba(0,0,0,1)] focus:outline-none active:shadow-[2px_2px_0px_rgba(0,0,0,1)]"
			{placeholder}
			bind:value
			required
		/>
		<button
			type="button"
			class="absolute top-1/2 right-3 -translate-y-1/2"
			onclick={() => (visible = !visible)}
			aria-label={visible ? 'Hide password' : 'Show password'}
		>
			{#if visible}
				<Eye />
			{:else}
				<EyeOff />
			{/if}
		</button>
	</div>
</fieldset>
