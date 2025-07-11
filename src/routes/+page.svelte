<script>
	import Button from '$lib/components/Button.svelte';
	import Card from '$lib/components/Card.svelte';
	import Input from '$lib/components/input/Input.svelte';
	import PlayfulBackground from '$lib/components/PlayfulBackground.svelte';
	let value = $state('');
</script>

<PlayfulBackground />
<h1>Belajar Svelte Kit</h1>
<Card>
	<Input {value} />
	<Button type="primary">Custom Hover Button</Button>
</Card>
