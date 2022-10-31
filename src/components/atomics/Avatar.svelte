<script lang="ts">
	export let src: string = '';
	export let alt: string = '';
	export let size: string | 'large' | 'small' = 'large';
	export let className: string = '';
</script>

<div
	class={`${
		size === 'large' ? 'h-[96px] w-[96px]' : 'h-8 w-8'
	} overflow-hidden rounded-full flex items-center justify-center ${className}`}
>
	<img class="h-full w-full object-cover" {src} {alt} />
</div>
