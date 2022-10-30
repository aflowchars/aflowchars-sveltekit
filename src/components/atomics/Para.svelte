<script lang="ts">
	interface Para {
		className?: string;
		type?: string | 'heading' | 'span' | 'para';
		uppercase?: boolean;
	}
	// export let className: string = '';
	// export let type: string | 'heading' | 'span' | 'para' = 'para';
	// export let uppercase: boolean = false;
	export let { className, type, uppercase }: Para = {};
</script>

{#if type === 'heading'}
	<h5 class={`text-base font-normal ${className}`}><slot /></h5>
{:else if type === 'span'}
	<span class={`text-xs font-light ${uppercase && 'uppercase'} ${className}`}>
		<slot />
	</span>
{:else}
	<p />
{/if}
