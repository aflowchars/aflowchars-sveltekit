<script lang="ts">
	// export let className: string = '';
	// export let type: string | 'heading' | 'span' | 'para' = 'para';
	// export let uppercase: boolean = false;

	interface Para {
		className?: string;
		type?: string | 'heading' | 'span' | 'para';
		uppercase?: boolean;
	}

	export let { className, type, uppercase }: Para = {};

	let base = {
		heading: 'text-base font-normal'
	};
</script>

{#if type === 'heading'}
	<h5 class="{base.heading} {uppercase && 'uppercase'} {className}">
		<slot />
	</h5>
{:else if type === 'span'}
	<span class="text-xs font-light {uppercase && 'uppercase'} {className}">
		<slot />
	</span>
{:else}
	<p />
{/if}
