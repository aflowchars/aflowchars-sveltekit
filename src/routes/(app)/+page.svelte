<script lang="ts">
	import Head from '$components/utilities/Head.svelte';
	import Hero from '$components/templates/Hero.svelte';
	import Quotes from '$components/templates/Quotes.svelte';
	import Blogs from '$components/templates/Blogs.svelte';
	import Contact from '$components/templates/Contact.svelte';
	import Divider from '$components/moleculs/Divider.svelte';

	import Heading from '$components/atomics/Heading.svelte';
	import Card from '$components/organisms/Card.svelte';
	import Button from '$components/moleculs/Button.svelte';

	let blogs2 = [
		{
			tag: 'UI Design',
			image: 'blogs-1.png',
			alt: 'Blog 1',
			title: 'Kerning? Keren Ning Pusing',
			content:
				'Mungkin sebagian dari kita sering bertanya, kok desainnya bisa rapi begitu ya? Kok minimalis? Loh kok beda dengan yang kubuat ...'
		},
		{
			tag: 'Frontend',
			image: 'blogs-2.png',
			alt: 'Blog 2',
			title: 'Mengapa Tailwind CSS Populer?',
			content:
				'Mungkin Bootstrap masih menjadi raja, tapi jikalau raja sudah tak ada pesaingnya, kan hampa. Maka dari itu Tailwind CSS, membawa segalanya ...'
		},
		{
			tag: 'UX Design',
			image: 'blogs-3.png',
			alt: 'Blog 3',
			title: 'Warna? Kok Bisa Ya???',
			content:
				'Pengen tahu efek nyata dari warna? Coba atur HP anda jadi hitam putih pada pengaturan warna. Ada fitur dark mode? Silahkan dicoba juga ...'
		},
		{
			tag: 'UI Design',
			image: 'blogs-1.png',
			alt: 'Blog 1',
			title: 'Kerning? Keren Ning Pusing',
			content:
				'Mungkin sebagian dari kita sering bertanya, kok desainnya bisa rapi begitu ya? Kok minimalis? Loh kok beda dengan yang kubuat ...'
		},
		{
			tag: 'Frontend',
			image: 'blogs-2.png',
			alt: 'Blog 2',
			title: 'Mengapa Tailwind CSS Populer?',
			content:
				'Mungkin Bootstrap masih menjadi raja, tapi jikalau raja sudah tak ada pesaingnya, kan hampa. Maka dari itu Tailwind CSS, membawa segalanya ...'
		},
		{
			tag: 'UX Design',
			image: 'blogs-3.png',
			alt: 'Blog 3',
			title: 'Warna? Kok Bisa Ya???',
			content:
				'Pengen tahu efek nyata dari warna? Coba atur HP anda jadi hitam putih pada pengaturan warna. Ada fitur dark mode? Silahkan dicoba juga ...'
		}
	];
</script>

<Head title="Ora Ono Opo Opo" />

<section class="hero">
	<Hero />
</section>

<!-- <Divider props={socials} /> -->

<Quotes />

<!-- <Divider props={blogs} /> -->

<section class="blogs">
	<Blogs />
</section>

<!-- <Divider props={contact} /> -->

<section class="contact">
	<Contact />
</section>

<!-- <Divider props={skills} /> -->

<section class="skills">
	<div class="grid grid-cols-12 gap-16 py-16">
		<div class="col-start-2 col-end-12 flex flex-col items-center">
			<Heading className="text-center">
				Suka slicing UI yang mantap. Tembak Responsive dengan Tailwind CSS
				sebagia senjata utama. Terkadang menggunakan BEM/SMACSS. Asyik menulis
				Clean Code/Atomic. Next JS yang utama, SvelteKit yang dicinta. Hobby
				solve conflict di Git, dan sedang belajar lebih jauh State Management &
				Consume Rest API. Berikut Portfolio Saya.
			</Heading>
			<Button
				type="link"
				href="https://www.facebook.com/FK.FatwaKehidupan"
				size="base"
				border
				className="mt-6 mb-[72px]"
			>
				Lihat Semua
			</Button>
		</div>
		<div class="col-span-12 grid grid-cols-12 gap-16">
			{#each blogs2 as { tag, image, alt, title, content }}
				<div class="md:col-span-3 xl:col-span-4">
					<Card
						type="text"
						{tag}
						{image}
						{alt}
						{title}
						{content}
						cta="Kunjungi Portofolio"
					/>
				</div>
			{/each}
		</div>
	</div>
</section>
