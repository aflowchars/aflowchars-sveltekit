<script lang="ts">
	import Google from '$assets/icons/google.svelte';
	import Avatar from '$components/atomics/Avatar.svelte';
	import Heading from '$components/atomics/Heading.svelte';
	import Para from '$components/atomics/Para.svelte';
	import Button from '$components/moleculs/Button.svelte';
	import Card from '$components/organisms/Card.svelte';
	import Form from '$components/organisms/Form.svelte';
	import Head from '$components/utilities/Head.svelte';
	import { supabase } from '../../../supabase';

	let loading = false;
	let email = '';
	let password = '';

	const handleLogin = async () => {
		try {
			loading = true;
			const { error } = await supabase.auth.signInWithOtp({ email });
			if (error) throw error;
			alert('Check your email for login link!');
		} catch (error) {
			if (error instanceof Error) alert(error.message);
		} finally {
			loading = false;
		}
	};

	console.log({ email, password });
</script>

<Head title="Login" />

<div
	class="grid h-full min-h-[calc(100vh-96px)] grid-cols-12 place-items-center gap-16"
>
	<div class="col-start-1 col-end-7 py-24">
		<Card
			type="image"
			tag="Login"
			image={'portfolio-nur.jpg'}
			alt="Portfolio Nur Photo"
			cta="Lihat Video Lainnya"
		/>
	</div>

	<div class="col-start-7 col-end-8 h-full place-self-center">
		<div class="h-full w-px bg-black" />
	</div>

	<div class="col-start-8 col-end-13 w-full py-24" aria-live="polite">
		<Heading type="large">Sign in Aflowchars</Heading>

		<Button
			type="button"
			className="mt-4 mb-8 border border-black gap-2"
			flow="row"
		>
			<Avatar
				size="small"
				src="afochar-s-photo-hero.png"
				alt="Profile Avatar User"
				className="ml-3"
			/>

			<div class="flex flex-col items-start">
				<Para type="span" className="text-base font-medium">
					Sign In as Afochar
				</Para>
				<Para type="span" className="text-xs font-regular">
					aflowcharsss@gmail.com
				</Para>
			</div>

			<div class="border-l border-black p-4">
				<Google className="w-4 h-4" />
			</div>
		</Button>

		<Form {loading} {email} onSubmit={handleLogin} {password} />
	</div>
</div>
