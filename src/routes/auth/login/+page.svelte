<script lang="ts">
	import Button from '$lib/components/Button.svelte';
	import Card from '$lib/components/Card.svelte';
	import Input from '$lib/components/input/Input.svelte';
	import InputPassword from '$lib/components/input/InputPassword.svelte';
	import PlayfulBackground from '$lib/components/PlayfulBackground.svelte';
	let loginData = $state({
		email: '',
		password: ''
	});
	const handleLogin = () => {
		console.log('Login data:', loginData);
		// Implement login logic here
	};
</script>

<PlayfulBackground />
<img src="/coinly-logo.png" alt="logo" class="w-32 mx-auto mb-4" />
<h1>{loginData.email}</h1>
<Card className="w-full md:w-96">
	<form action="" onsubmit={handleLogin}>
		<Input
			placeholder={'contoh: jokowi@gmail.com'}
			type={'email'}
			label={'Email'}
			isRequired
			bind:value={loginData.email}
		/>
		<InputPassword bind:value={loginData.password} label="Password" placeholder={''} />
		<Button type="primary" isSubmit className="w-full mt-4">Login</Button>
	</form>
</Card>
