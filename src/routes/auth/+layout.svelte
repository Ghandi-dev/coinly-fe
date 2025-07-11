<script lang="ts">
	let { children } = $props();
</script>

<div class="bg-base-200 flex min-h-screen flex-col items-center justify-center p-4 md:p-0">
	{@render children()}
</div>
