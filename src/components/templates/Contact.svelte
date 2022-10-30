<script lang="ts">
	import Heading from '$components/atomics/Heading.svelte';
	import Button from '$components/moleculs/Button.svelte';

	let contactList = [
		{
			heading: 'Pengen Ngobrol Atau Tanya-Tanya',
			type: 'left',
			link: [
				{
					href: 'https://instagram.com/aflowchars',
					label: 'Instagram'
				},
				{
					href: 'https://youtube.com/aflowchars',
					label: 'Youtube'
				}
			]
		},
		{
			heading: 'Pengen Lihat Karya Biasa Lainnya',
			type: 'right',
			link: [
				{
					href: 'https://github.com/aflowchars',
					label: 'Github'
				},
				{
					href: 'https://dribbble.com/aflowchars',
					label: 'Dribbble'
				}
			]
		}
	];
</script>

<div class="flex flex-col items-center gap-40 py-40">
	{#each contactList as { heading, type, link }}
		<div
			class="grid w-full grid-cols-12 place-content-center md:gap-8 xl:gap-16"
		>
			<div
				class={`col-start-2 col-end-12 flex flex-wrap md:flex-nowrap ${
					type === 'left' ? 'flex-row' : 'flex-row-reverse'
				} items-center md:gap-16 xl:gap-32`}
			>
				<Heading
					type="large"
					className={`w-full md:w-full xl:w-8/12 border-b border-black pb-6 ${
						type === 'left' ? 'text-left' : 'text-right'
					}`}
				>
					{heading}
				</Heading>
				<div
					class={`mt-8 md:mt-0 flex items-center gap-4 md:gap-8 xl:gap-16 w-full`}
				>
					{#each link as { href, label }}
						<Button
							className={`w-full ${
								type === 'left' ? 'text-left' : 'text-right'
							}`}
							type="link"
							size="xtra"
							{href}
						>
							{label}
						</Button>
					{/each}
				</div>
			</div>
		</div>
	{/each}
</div>
