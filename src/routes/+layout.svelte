<script lang="ts">
	import '../app.css';

	import Navbar from '$components/organisms/Navbar.svelte';
	import Footer from '$components/organisms/Footer.svelte';
</script>

<Navbar />

<slot />

<Footer />
