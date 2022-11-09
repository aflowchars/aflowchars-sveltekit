<script lang="ts">
	import Button from '$components/moleculs/Button.svelte';
	import Input from '$components/moleculs/Input.svelte';

	export let onSubmit: VoidFunction;
	export let email: any;
	export let password: any;
	export let loading: any;
</script>

<form
	class="flex w-full flex-col items-center gap-16"
	on:submit|preventDefault={onSubmit}
>
	<div class="flex w-full flex-col items-start">
		<Input
			label="Email"
			id="email"
			type="email"
			placeholder="Your Email"
			value={email}
		/>
	</div>

	<div class="flex w-full flex-col items-start">
		<Input
			label="Password"
			id="password"
			type="password"
			placeholder="Your password"
			value={password}
		/>
	</div>
	<div class="-mt-8 flex w-full items-center justify-between">
		<Button
			ariaLive="polite"
			disabled={loading}
			type="button"
			background
			weight="medium"
			className="text-sm px-12"
		>
			<span>{loading ? 'Loading' : 'Sign In'}</span>
		</Button>

		<Button
			ariaLive="polite"
			disabled={loading}
			type="button"
			background
			border
			weight="medium"
			className="text-sm bg-white text-black text-right"
		>
			Forgot your password?
		</Button>
	</div>
</form>
