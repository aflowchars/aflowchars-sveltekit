<script lang="ts">
	export let src: string = '';
	export let alt: string = '';
</script>

<div class="mb-4 max-h-[96px] max-w-[96px] overflow-hidden rounded-full">
	<img class="h-full w-full object-cover" {src} {alt} />
</div>
