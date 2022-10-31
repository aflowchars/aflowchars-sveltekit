<script lang="ts">
	export let main: boolean | false = false;
	export let type: string | 'xtra' | 'large' | 'base' = 'base';
	export let className: string = '';
	export let id: string = '';
</script>

{#if main}
	<h1
		{id}
		class={`leading-[1.6] text-4xl md:leading-[1.6] md:text-5xl font-light xl:leading-[1.6] tracking-[0.08em] ${className}`}
	>
		<slot />
	</h1>
{:else}
	<h3
		class={`leading-[1.6] tracking-[0.06em] ${
			(type === 'large' && 'text-3xl md:text-[2rem]') ||
			(type === 'base' && 'text-2xl')
		} ${className}`}
	>
		<slot />
	</h3>
{/if}
