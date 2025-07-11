<script lang="ts">
	interface Props {
		children: import('svelte').Snippet;
		className?: string;
	}

	let { children, className }: Props = $props();
</script>

<div
	class={`card card-border bg-base-100 rounded-md border-2 border-black shadow-[8px_8px_0px_rgba(0,0,0,1)] ${className || ''} overflow-hidden`}
>
	<!-- <div
		class="bg-primary absolute -top-2 -right-2 h-12 w-12 rotate-6 transform rounded-bl-2xl border-b-3 border-l-3 border-black transition-colors duration-300"
	>
		<div
			class="text-primary-content absolute bottom-1 left-1 text-xs font-bold transition-colors duration-300"
		>
			hello
		</div>
	</div> -->
	<div class="card-body">
		{@render children()}
	</div>
</div>
