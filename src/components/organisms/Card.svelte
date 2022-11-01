<script lang="ts">
	import Para from '$components/atomics/Para.svelte';
	import Avatar from '$components/atomics/Avatar.svelte';
	import Close from '$assets/icons/close.svelte';
	import Button from '$components/moleculs/Button.svelte';

	interface Card {
		type?: string | 'images' | 'text' | 'avatar';
		tag?: string;
		title?: string;
		content?: string;
		image?: string;
		alt?: string;
		cta?: string;
	}

	export let { type, tag, title, content, image, alt, cta }: Card = {};
</script>

<div
	class={`${
		type === 'image' ? 'h-fit' : ' h-full'
	} flex min-h-[350px] w-full flex-col items-center justify-between border-[0.5px] border-black`}
>
	<div
		class={`flex w-full items-center justify-between border-b border-black ${
			type === 'avatar' ? 'px-4 py-2' : 'px-6 py-4'
		}`}
	>
		<Para type="span">{tag}</Para>
		<Close />
	</div>

	<div
		class={`flex flex-col py-8 ${
			(type === 'avatar' && 'items-center') || 'items-start p-6 pb-10 gap-y-6'
		}`}
	>
		{#if type === 'avatar'}
			<Avatar className="mb-4" src="afochar-s-photo-hero.png" alt="Afochar S" />
		{:else if type === 'text'}
			<div class="h-full max-h-[196px] w-full">
				<img class="h-full w-full object-cover" src={image} {alt} />
			</div>
		{:else}
			<div class="h-full max-h-[280px] w-full">
				<img class="h-full w-full object-cover" src={image} {alt} />
			</div>
		{/if}

		{#if type !== 'image'}
			<div class={`${type === 'avatar' ? 'text-center' : 'text-left'}`}>
				<Button type="link">
					<h5
						class={`${
							type === 'avatar'
								? 'font-medium text-lg'
								: 'mb-4 font-medium text-xl'
						}`}
					>
						{title}
					</h5>
				</Button>
				<p
					class={`${
						type === 'avatar' ? 'text-sm' : 'text-base leading-[1.6] font-light'
					}`}
				>
					{content}
				</p>
			</div>
		{/if}
	</div>

	<div class="w-full justify-end">
		<Button
			type="button"
			background
			full={true}
			weight="medium"
			className="text-center"
		>
			{cta}
		</Button>
	</div>
</div>
