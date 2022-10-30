<script lang="ts">
	import Button from './Button.svelte';

	interface Item {
		type: string;
		href: string;
		label: string;
	}

	export let props: Item[] = [];
</script>

<div class="flex w-full items-center justify-between gap-4 text-xs uppercase">
	{#each props as item}
		{#if item.type === 'left'}
			<Button type="link" size="small" href={item.href}>{item.label}</Button>
		{/if}
	{/each}
	<div class="h-px w-full bg-black" />
	{#each props as item}
		{#if item.type === 'right'}
			<Button type="link" size="small" href={item.href}>{item.label}</Button>
		{/if}
	{/each}
</div>
