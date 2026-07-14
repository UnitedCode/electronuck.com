<script lang="ts">
	import { resolve } from '$app/paths';
	import { page } from '$app/state';

	const home = resolve('/');
	const youtube = 'https://www.youtube.com/@ElectroNuck';
</script>

<header
	class="site-header relative z-20 mx-auto grid min-h-20 w-[calc(100%-2*var(--page-gutter))] max-w-[90rem] grid-cols-[1fr_auto_1fr] items-center border-b border-phosphor/30 font-mono text-xs tracking-[0.08em] uppercase after:absolute after:bottom-[-1px] after:left-0 after:h-0.5 after:w-32 after:bg-laser max-md:min-h-17 max-md:grid-cols-[1fr_auto]"
>
	<a
		class="w-max font-display text-sm font-extrabold tracking-normal text-crt no-underline italic"
		href={home}
		aria-label="ElectroNuck home">ElectroNuck <span class="text-laser">///</span></a
	>
	<nav class="flex gap-[clamp(1.5rem,3vw,3.5rem)] max-md:hidden" aria-label="Primary navigation">
		<a class="nav-link" href={resolve('/#projects')}>Projects</a>
		<a class:active={page.url.pathname === '/videos'} class="nav-link" href={resolve('/videos')}
			>Videos</a
		>
		<a class="nav-link" href={resolve('/#about')}>About</a>
	</nav>
	<a
		class="justify-self-end text-arc no-underline max-md:hidden"
		href={youtube}
		target="_blank"
		rel="noreferrer"
	>
		YouTube <span aria-hidden="true">↗</span>
	</a>
	<details class="relative hidden justify-self-end max-md:block">
		<summary
			class="cursor-pointer list-none py-3 before:mr-2 before:text-laser before:content-['//']"
			>Menu</summary
		>
		<div
			class="absolute top-[calc(100%+1rem)] right-0 flex w-[min(16rem,calc(100vw-2*var(--page-gutter)))] flex-col border border-crt bg-void shadow-[0_0_30px_rgba(110,220,242,0.13)] [&>a]:p-4 [&>a]:no-underline [&>a+a]:border-t [&>a+a]:border-phosphor/25"
		>
			<a href={resolve('/#projects')}>Projects</a>
			<a href={resolve('/videos')}>Videos</a>
			<a href={resolve('/#about')}>About</a>
			<a href={youtube} target="_blank" rel="noreferrer">YouTube ↗</a>
		</div>
	</details>
</header>
