<script lang="ts">
	import Head from '$components/utilities/Head.svelte';
	import Hero from '$components/templates/Hero.svelte';
	import Quotes from '$components/templates/Quotes.svelte';
	import Blogs from '$components/templates/Blogs.svelte';
	import Contact from '$components/templates/Contact.svelte';
	import Divider from '$components/moleculs/Divider.svelte';

	import { divider } from '../data/divider';

	const { socials, blogs, contact, copyright } = divider;
</script>

<Head title="Ora Ono Opo Opo" />

<section class="hero">
	<Hero />
</section>

<Divider props={socials} />

<Quotes />

<Divider props={blogs} />

<section class="blogs">
	<Blogs />
</section>

<Divider props={contact} />

<section class="contact">
	<Contact />
</section>

<Divider props={copyright} />
