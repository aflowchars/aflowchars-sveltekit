<script>
	import '../app.css';
	import Head from '$components/utilities/Head.svelte';
	import Heading from '$components/atomics/Heading.svelte';
	import Navbar from '$components/organisms/Navbar.svelte';
	import Para from '$components/atomics/Para.svelte';
	import Divider from '$components/moleculs/Divider.svelte';
	import Card from '$components/organisms/Card.svelte';
	import Button from '$components/moleculs/Button.svelte';
	import ChevronDown from '$assets/icons/chevron-down.svelte';
	import Quotes from '$components/templates/Quotes.svelte';
	import Contact from '$components/templates/Contact.svelte';

	let dividerSocials = [
		{
			type: 'left',
			href: 'https://instagram.com/aflowchars',
			label: 'Instagram'
		},
		{
			type: 'left',
			href: 'https://dribbble.com/aflowchars',
			label: 'Dribbble'
		},
		{
			type: 'right',
			href: 'https://instagram.com/aflowchars',
			label: 'Github'
		},
		{
			type: 'right',
			href: 'https://instagram.com/aflowchars',
			label: 'Youtube'
		}
	];

	let dividerBlogs = [
		{
			type: 'left',
			href: 'https://instagram.com/aflowchars',
			label: 'Videos'
		},
		{
			type: 'right',
			href: 'https://instagram.com/aflowchars',
			label: 'Check'
		}
	];
	let dividerContact = [
		{
			type: 'left',
			href: 'https://instagram.com/aflowchars',
			label: 'Contact'
		},
		{
			type: 'right',
			href: 'https://instagram.com/aflowchars',
			label: 'Check'
		}
	];
	let dividerCopyright = [
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

	let blogs = [
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

<Navbar />

<section class="hero">
	<div class="flex min-h-[calc(100vh-96px)] flex-col items-center py-24">
		<Para type="heading" className="mb-2" uppercase>Ora Ono Opo Opo</Para>
		<Heading main className="max-w-[832px] text-center">
			Cuma Murid Kehidupan Yang Belajar Berjalan Santai
		</Heading>

		<!-- Card -->
		<div class="mt-16 mb-12 w-full max-w-[256px]">
			<Card
				tag="Intro"
				type="avatar"
				title="Afochar Syabnirusmanto"
				content="a.k.a Apenk"
				cta="Frontend Developer"
			/>
		</div>

		<Button icon flow="col" full>
			<Para type="span">Lanjut</Para>
			<ChevronDown style="w-4 h-4" />
		</Button>
	</div>
</section>

<Divider props={dividerSocials} />

<Quotes />

<Divider props={dividerBlogs} />

<section class="blogs">
	<div class="flex flex-col items-center py-40">
		<Heading className="max-w-[832px] text-center">
			Suka menulis, semoga rubrik ini mampu menuangkan segala cipta, rasa dan
			karsa dalam berbagi manfaat kepada pembaca
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

		<div class="grid gap-8 md:grid-cols-6 md:gap-8 lg:gap-16 xl:grid-cols-12">
			{#each blogs as { tag, image, alt, title, content }}
				<div class="md:col-span-3 xl:col-span-4">
					<Card
						type="text"
						{tag}
						{image}
						{alt}
						{title}
						{content}
						cta="Lanjut Baca"
					/>
				</div>
			{/each}
		</div>
	</div>
</section>

<Divider props={dividerContact} />
<section class="contact">
	<Contact />
</section>
<Divider props={dividerCopyright} />
<footer class="footer">
	<div class="flex items-center justify-around py-16">
		<Para type="span" uppercase>Copywrong 2022</Para>
		<Para type="span" uppercase>Aflowchars</Para>
		<Para type="span" uppercase>Backend Soon</Para>
	</div>
</footer>
