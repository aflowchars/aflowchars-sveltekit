<script lang="ts">
	export let className: string = '';
	export let type: string | 'heading' | 'span' | 'para' = 'para';
	export let uppercase: boolean = false;
</script>

{#if type === 'heading'}
	<h5 class={`text-base font-normal ${uppercase && 'uppercase'} ${className}`}>
		<slot />
	</h5>
{:else if type === 'span'}
	<span class={`text-xs font-light ${uppercase && 'uppercase'} ${className}`}>
		<slot />
	</span>
{:else}
	<p />
{/if}
