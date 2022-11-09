<script>
	import Heading from '$components/atomics/Heading.svelte';
	import Navbar from '$components/organisms/Navbar.svelte';
	import Footer from '$components/organisms/Footer.svelte';
</script>

<Navbar />

<div class="container min-h-screen max-w-screen-xl py-8">
	<Heading type="main">Halo Ini Adalah Sandbox</Heading>

	<slot />
</div>

<Footer />
