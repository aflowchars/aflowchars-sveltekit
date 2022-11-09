<script lang="ts">
	import Navbar from '$components/organisms/Navbar.svelte';
	import Footer from '$components/organisms/Footer.svelte';
</script>

<Navbar />

<div class="wrapper">
	<slot />
</div>

<Footer />
