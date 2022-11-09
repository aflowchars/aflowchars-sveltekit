<script lang="ts">
	import Aflowchars from '$assets/icons/aflowchars.svelte';
	import Close from '$assets/icons/close.svelte';
	import Button from '$components/moleculs/Button.svelte';

	import { blur } from 'svelte/transition';
	import { quadInOut, quartInOut } from 'svelte/easing';

	let menuRef: boolean = false;
	let searchRef: boolean = false;
</script>

<header class="header wrapper relative">
	<nav class="flex items-center justify-between py-8">
		<Button onClick={() => (menuRef = !menuRef)} type="button" uppercase>
			Menu
		</Button>
		<Button type="link" href="/">
			<Aflowchars />
		</Button>
		<Button type="button" uppercase onClick={() => (searchRef = !searchRef)}>
			Search
		</Button>
	</nav>
	<div class="h-[0.5px] w-full bg-black" />

	<!-- Click Menu -->
	{#if menuRef}
		<nav
			transition:blur={{ duration: 500, easing: quadInOut, amount: 2 }}
			class={`navbar-menu justify-betweens absolute inset-0 ${
				menuRef ? 'flex' : 'hidden'
			} h-full items-center border-b border-black bg-white`}
		>
			<ul class="flex h-full w-full items-center justify-between">
				<Button
					type="button"
					onClick={() => (menuRef = !menuRef)}
					className="py-4"
				>
					<Close className="w-4 h-4" />
				</Button>
				<li>
					<Button
						uppercase
						size="small"
						type="link"
						href="https://instagram.com/aflowchars"
					>
						Home
					</Button>
				</li>
				<li>
					<Button
						uppercase
						size="small"
						type="link"
						href="https://instagram.com/aflowchars"
					>
						Blogs
					</Button>
				</li>

				<li>
					<Button
						uppercase
						size="small"
						type="link"
						href="https://instagram.com/aflowchars"
					>
						Video
					</Button>
				</li>
				<li>
					<Button
						uppercase
						size="small"
						type="link"
						href="https://instagram.com/aflowchars"
					>
						Docs
					</Button>
				</li>
				<li>
					<a href="/">
						<Aflowchars />
					</a>
				</li>
			</ul>
		</nav>
	{/if}

	<!-- Search Menu -->
	{#if searchRef}
		<nav
			transition:blur={{ duration: 500, easing: quadInOut, amount: 2 }}
			class={`navbar-menu justify-betweens absolute inset-0 flex h-full items-center border-b border-black bg-white`}
		>
			<ul
				class="flex h-full w-full flex-row-reverse items-center justify-between"
			>
				<Button
					type="button"
					onClick={() => (searchRef = !searchRef)}
					className="py-4"
				>
					<Close className="w-4 h-4" />
				</Button>

				<form action="#" class="h-full w-full px-16">
					<input
						type="text"
						class="h-full w-full bg-white text-right outline-none placeholder:text-black"
						placeholder="Ketikkan yang anda cari, jangan lupa pencet enter kalo selesai"
					/>
				</form>

				<li>
					<a href="/">
						<Aflowchars />
					</a>
				</li>
			</ul>
		</nav>
	{/if}
</header>
