<script lang="ts">
	import { resolve } from '$app/paths';
	import SiteFooter from '$lib/components/SiteFooter.svelte';
	import SiteHeader from '$lib/components/SiteHeader.svelte';

	type MediaLink = { label: string; href: string; external?: boolean };
	type Video = {
		id: string;
		url: string;
		title: string;
		date: string;
		duration: string;
		summary: string;
		links: MediaLink[];
	};

	const youtube = 'https://www.youtube.com/@ElectroNuck';
	const dsp = 'https://github.com/nathansbradshaw/synthphone_e_vocal_dsp';

	const videos: Video[] = [
		{
			id: 'MOTztv2FLxE',
			url: 'https://www.youtube.com/watch?v=MOTztv2FLxE',
			title: "POV: it's 2007 and your parents are fighting in the kitchen",
			date: 'February 27, 2026',
			duration: '12:27',
			summary:
				'Enoch rebuilds his 2007 bedroom in Unity VR, down to RuneScape, Scooby-Doo, and Linkin Park. A fight in the kitchen leaks through the walls.',
			links: [
				{
					label: 'Watch on YouTube',
					href: 'https://www.youtube.com/watch?v=MOTztv2FLxE',
					external: true
				}
			]
		},
		{
			id: '1VQUEm7suBc',
			url: 'https://www.youtube.com/watch?v=1VQUEm7suBc',
			title: 'I Made the Ultimate Hyperpop Instrument out of a Telephone',
			date: 'July 17, 2025',
			duration: '18:07',
			summary:
				'Enoch and Nathan rebuild Synthphone-E as a real-time pitch corrector, formant processor, and vocoder. They leave a circular-buffer bug in V1, fix it for V2, then play the finished instrument.',
			links: [
				{
					label: 'Watch on YouTube',
					href: 'https://www.youtube.com/watch?v=1VQUEm7suBc',
					external: true
				},
				{ label: 'Read about Synthphone-E', href: resolve('/projects/synthphone-e') },
				{ label: 'View the vocal DSP', href: dsp, external: true }
			]
		},
		{
			id: 'urLUqi2jPyE',
			url: 'https://www.youtube.com/shorts/urLUqi2jPyE',
			title: 'Turning a Thrift Store Telephone into a Synthesizer',
			date: 'February 13, 2025',
			duration: '2:01',
			summary:
				'The first Synthphone-E short. Enoch uses the handset speaker as a lo-fi microphone, then adds a synthesizer and vocal effects.',
			links: [
				{
					label: 'Watch on YouTube',
					href: 'https://www.youtube.com/shorts/urLUqi2jPyE',
					external: true
				},
				{ label: 'Read about Synthphone-E', href: resolve('/projects/synthphone-e') }
			]
		}
	];
</script>

<svelte:head>
	<title>Videos | ElectroNuck</title>
	<meta
		name="description"
		content="ElectroNuck build videos, technical talks, obsolete hardware, and the bugs found along the way."
	/>
</svelte:head>

<SiteHeader />

<main>
	<section class="video-index-hero" aria-labelledby="page-title">
		<div>
			<p class="meta text-crt">Transmission archive</p>
			<h1 id="page-title" class="signal-title mt-7">Videos</h1>
		</div>
		<div class="video-hero-copy">
			<p class="page-lead">Build videos with the bugs left in.</p>
			<a class="action mt-6 inline-block text-arc" href={youtube} target="_blank" rel="noreferrer"
				>Open the YouTube channel ↗</a
			>
		</div>
	</section>

	<!-- Data-driven links below include both confirmed external URLs and resolved internal routes. -->
	<!-- eslint-disable svelte/no-navigation-without-resolve -->
	<section class="video-index" aria-label="ElectroNuck video archive">
		{#each videos as video, index (video.id)}
			<article class="video-entry">
				<div class="video-sequence" aria-hidden="true">
					<span>{String(videos.length - index).padStart(2, '0')}</span><i></i>
				</div>
				<a
					class="video-thumbnail group"
					href={video.url}
					target="_blank"
					rel="noreferrer"
					aria-label={`Watch ${video.title}`}
				>
					<img
						src={`https://i.ytimg.com/vi/${video.id}/sddefault.jpg`}
						alt=""
						width="640"
						height="480"
						loading={index === 0 ? 'eager' : 'lazy'}
					/>
					<span class="meta">Play <b aria-hidden="true">▶</b></span>
				</a>
				<div class="video-entry-copy">
					<div class="video-meta meta"><span>{video.date}</span><span>{video.duration}</span></div>
					<h2>{video.title}</h2>
					<p>{video.summary}</p>
					<div class="video-links">
						{#each video.links as link (link.href)}
							<a
								class="text-link"
								href={link.href}
								target={link.external ? '_blank' : undefined}
								rel={link.external ? 'noreferrer' : undefined}
								>{link.label} {link.external ? '↗' : '→'}</a
							>
						{/each}
					</div>
				</div>
			</article>
		{/each}
	</section>
	<!-- eslint-enable svelte/no-navigation-without-resolve -->

	<section class="talks-section" aria-labelledby="talks-title">
		<header>
			<p class="meta text-laser">Talks and appearances</p>
			<h2 id="talks-title" class="section-title mt-4">Springfield Devs</h2>
		</header>
		<article class="talk-entry">
			<a
				class="video-thumbnail group"
				href="https://www.youtube.com/watch?v=6v_yg4s-u_g"
				target="_blank"
				rel="noreferrer"
				aria-label="Watch Learning Way Too Much About Audio Programming to Meet Mark Rober"
			>
				<img
					src="https://i.ytimg.com/vi/6v_yg4s-u_g/sddefault.jpg"
					alt=""
					width="640"
					height="480"
					loading="lazy"
				/>
				<span class="meta">Play <b aria-hidden="true">▶</b></span>
			</a>
			<div class="video-entry-copy">
				<div class="video-meta meta"><span>September 8, 2025</span><span>1:09:02</span></div>
				<h3>Learning Way Too Much About Audio Programming to Meet Mark Rober</h3>
				<p>
					At Springfield Devs, Enoch and Nathan explain Synthphone-E's origin, embedded Rust,
					real-time audio processing, Open Sauce 2025, and features still in progress. Mark Rober
					does not appear.
				</p>
				<div class="video-links">
					<a
						class="text-link"
						href="https://www.youtube.com/watch?v=6v_yg4s-u_g"
						target="_blank"
						rel="noreferrer">Watch the talk ↗</a
					>
					<a class="text-link" href={resolve('/projects/synthphone-e')}>Read about Synthphone-E →</a
					>
					<a class="text-link" href={dsp} target="_blank" rel="noreferrer">View the vocal DSP ↗</a>
				</div>
			</div>
		</article>
	</section>

	<section class="video-endcap">
		<p class="section-title">End of transmission.</p>
		<nav aria-label="Continue exploring">
			<a class="text-link" href={resolve('/projects/synthphone-e')}>Synthphone-E →</a>
			<a class="text-link" href={resolve('/projects/keyboard-keyboard')}>Keyboard² →</a>
			<a class="text-link" href={youtube} target="_blank" rel="noreferrer">YouTube channel ↗</a>
		</nav>
	</section>
</main>

<SiteFooter />
