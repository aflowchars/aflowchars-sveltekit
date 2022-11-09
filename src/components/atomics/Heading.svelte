<script lang="ts">
	import Button from '$components/moleculs/Button.svelte';

	export let main: boolean | false = false;
	export let type: string | 'xtra' | 'large' | 'base' = 'base';
	export let className: string = '';
	export let id: string = '';

	interface Heading {
		variant: 'primary' | 'secondary';
	}
</script>

{#if main}
	<h1
		{id}
		class="text-4xl font-light leading-[1.6] tracking-[0.08em] md:text-5xl md:leading-[1.6] xl:leading-[1.6] {className}"
	>
		<slot />
	</h1>
{:else}
	<h3
		class="leading-[1.6] tracking-[0.06em] {(type === 'large' &&
			'text-3xl md:text-[2rem]') ||
			(type === 'base' && 'text-2xl')} {className}"
	>
		<slot />
	</h3>
{/if}
