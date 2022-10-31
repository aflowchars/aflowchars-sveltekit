<script lang="ts">
	export let type: string | 'link' | 'button' = 'button';
	export let uppercase: boolean = false;
	export let href: string = '';
	export let icon: boolean = false;
	export let flow: string | 'col' | 'row' = 'row';
	export let size: string | 'xtra' | 'large' | 'base' | 'small' = 'small';
	export let border: boolean = false;
	export let className: string = '';
	export let background: boolean = false;
	export let full: boolean = false;
	export let ariaLive: string = 'polite';
	export let disabled: boolean = true;
	export let weight: string | 'semibold' | 'medium' | 'regular' = 'semibold';
</script>

{#if type === 'button'}
	<button
		aria-live={`off` || ariaLive}
		{disabled}
		class={`${full && 'w-full'} ${
			background &&
			`bg-black text-white py-3.5 text-xs font-${
				weight === 'medium' ? 'medium' : 'semibold'
			}`
		} ${icon && 'flex items-center'} ${flow === 'col' && 'flex-col'} ${
			uppercase && 'uppercase'
		} ${className && className} ${
			border && 'py-4 border-b border-black'
		} text-xs whitespace-nowrap flex items-center justify-center cursor-pointer`}
	>
		<slot />
	</button>
{:else}
	<a
		{href}
		target="_blank"
		rel="noreferrer"
		class={`${full && 'w-full'}
			${uppercase && 'uppercase'}
			${border && 'py-4 border-b border-black'}
			${
				(size === 'xtra' && 'text-2xl') ||
				(size === 'large' && 'text-lg px-2.5') ||
				(size === 'base' && 'text-sm tracking-[0.08em]') ||
				(size === 'small' && 'text-xs')
			} ${className}`}
	>
		<slot />
	</a>
{/if}
