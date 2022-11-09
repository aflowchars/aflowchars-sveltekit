<script lang="ts">
	import Para from '$components/atomics/Para.svelte';
	import Divider from '$components/moleculs/Divider.svelte';
	const divider = [
		{
			type: 'left',
			href: 'https://instagram.com/aflowchars',
			label: 'Copyright'
		},
		{
			type: 'right',
			href: 'https://instagram.com/aflowchars',
			label: 'Check'
		}
	];
</script>

<Divider props={divider} />

<div class="wrapper">
	<footer class="footer">
		<div class="flex items-center justify-around py-16">
			<Para type="span" uppercase>Copywrong 2022</Para>
			<Para type="span" uppercase>Aflowchars</Para>
			<Para type="span" uppercase>Backend Soon</Para>
		</div>
	</footer>
</div>
