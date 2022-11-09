<script lang="ts">
	export let src: string = '';
	export let alt: string = '';
	export let size: string | 'large' | 'small' = 'large';
	export let className: string = '';
	export let baseAvatar =
		'flex items-center justify-center overflow-hidden rounded-full';
	export let baseAvatarImg = 'h-full w-full object-cover';
</script>

<div
	class="{size === 'large'
		? 'h-[96px] w-[96px]'
		: 'h-8 w-8'} {baseAvatar} {className}"
>
	<img class={baseAvatarImg} {src} {alt} />
</div>
