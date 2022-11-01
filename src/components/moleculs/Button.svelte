<script lang="ts">
	interface Button {
		type?: string | 'link' | 'button';
		uppercase?: boolean;
		href?: string;
		icon?: boolean;
		flow?: string | 'col' | 'row';
		size?: string | 'xtra' | 'large' | 'base' | 'small';
		border?: boolean;
		className?: string;
		background?: boolean;
		full?: boolean;
		ariaLive?: string;
		disabled?: boolean;
		weight?: string | 'semibold' | 'medium' | 'regular';
		onClick?: VoidFunction;
		isBlank?: boolean;
	}

	export let {
		type,
		uppercase,
		href,
		icon,
		flow,
		size,
		border,
		className,
		background,
		full,
		ariaLive,
		disabled,
		weight,
		onClick,
		isBlank
	}: Button = {};
</script>

{#if type === 'button'}
	<button
		on:click={onClick}
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
		target={isBlank ? '_blank' : ''}
		rel="noreferrer"
		class={`${full && 'w-full'} ${uppercase && 'uppercase'} ${
			border && 'py-4 border-b border-black'
		} ${
			(size === 'xtra' && 'text-2xl') ||
			(size === 'large' && 'text-lg px-2.5') ||
			(size === 'base' && 'text-sm tracking-[0.08em]') ||
			(size === 'small' && 'text-xs')
		} ${className}`}
	>
		<slot />
	</a>
{/if}
