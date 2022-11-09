<script>
	import Aflowchars from '$assets/icons/aflowchars.svelte';
	import Button from '$components/moleculs/Button.svelte';
</script>

<div class="relative grid min-h-screen grid-cols-12 gap-16">
	<!-- Navbar Docs -->
	<div class="sticky top-0 left-0 col-span-2 h-screen bg-white py-24">
		<ul class="relative z-10 flex flex-col items-start gap-8 px-8">
			<li><a href="/"> Definisi </a></li>
			<li><a href="/"> Praktik </a></li>
			<li><a href="/"> Praktik </a></li>
			<li><a href="/"> Sejarah </a></li>
		</ul>

		<div class="absolute -right-4 top-0 z-0 flex h-full w-max">
			<div class="flex h-full w-full flex-col items-center justify-between">
				<Button type="link" size="small" uppercase className="my-2">Back</Button
				>
				<div class="h-full w-px bg-black" />
				<div class="my-4 h-max w-max">
					<Aflowchars />
				</div>
				<div class="h-full w-px bg-black" />
			</div>
		</div>
	</div>

	<!-- Content Docs -->
	<div class="relative col-span-10 py-24">
		<div class="container relative">
			<slot />
		</div>
	</div>
</div>
