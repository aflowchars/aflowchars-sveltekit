<script lang="ts">
	import Heading from '$components/atomics/Heading.svelte';
	import Button from '$components/moleculs/Button.svelte';
	import Card from '$components/organisms/Card.svelte';

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
