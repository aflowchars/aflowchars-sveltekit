<script>
	import ChevronDown from '$assets/icons/chevron-down.svelte';
	import Heading from '$components/atomics/Heading.svelte';

	import Para from '$components/atomics/Para.svelte';
	import Button from '$components/moleculs/Button.svelte';
	import Card from '$components/organisms/Card.svelte';

	import { animate } from 'motion';
	import { onMount } from 'svelte';

	onMount(() => {
		animate(
			'#headingHero',

			{ y: 90 },

			{
				duration: 0.5,
				easing: 'ease-in-out',
				direction: 'alternate'
			}
		).finished.then(() => {
			animate('#headingHero', { y: 0 });
		});
	});
</script>

<div class="flex min-h-[calc(100vh-96px)] flex-col items-center py-24">
	<Para type="heading" className="mb-2" uppercase>Ora Ono Opo Opo</Para>
	<Heading id="headingHero" main className="max-w-[832px] text-center">
		Cuma Murid Kehidupan Yang Belajar Berjalan Santai
	</Heading>

	<!-- Card -->
	<div class="mt-16 mb-12 w-full max-w-[256px]">
		<Card
			tag="Intro"
			type="avatar"
			title="Afochar Syabnirusmanto"
			content="a.k.a Apenk"
			cta="Frontend Developer"
		/>
	</div>

	<Button icon flow="col" full>
		<Para type="span">Lanjut</Para>
		<ChevronDown style="w-4 h-4" />
	</Button>
</div>
