<script lang="ts">
	import { resolve } from '$app/paths';
	import SiteFooter from '$lib/components/SiteFooter.svelte';
	import SiteHeader from '$lib/components/SiteHeader.svelte';

	const youtube = 'https://www.youtube.com/@ElectroNuck';
	const openSauce =
		'https://www.opensauce.com/exhibits/the-cubical-collection-musical-instruments-disguised-as-office-equipment';
</script>

<svelte:head>
	<title>ElectroNuck | Obsolete technology, unnecessary instruments</title>
	<meta
		name="description"
		content="ElectroNuck is Enoch and Nathan Bradshaw, two brothers resurrecting obsolete technology as musical instruments and other technical mistakes."
	/>
</svelte:head>

<SiteHeader />

<main>
	<section
		class="hero relative isolate min-h-[calc(100svh-5rem)] overflow-hidden px-[var(--page-gutter)] pt-[clamp(2.5rem,6vw,6rem)] max-md:min-h-0 max-md:pt-12"
		aria-labelledby="hero-title"
	>
		<img
			class="wordmark mx-auto -mt-14 -mb-10 h-auto w-[clamp(18rem,38vw,36rem)] drop-shadow-[0_0_18px_rgba(110,220,242,0.18)] max-md:-mt-8 max-md:mb-0 max-md:w-[min(22rem,92vw)]"
			src="/images/brand/electronuck-logo.png"
			alt="ElectroNuck"
			width="1280"
			height="720"
		/>

		<div class="relative z-2 mx-auto w-full max-w-[90rem]">
			<div class="hero-glint" aria-hidden="true"></div>
			<h1
				id="hero-title"
				class="y2k-title relative m-0 w-[min(12ch,100%)] font-display text-[clamp(3rem,7.2vw,7.5rem)] leading-[0.86] font-extrabold tracking-[-0.055em] text-balance uppercase italic max-md:text-[clamp(2.65rem,11.5vw,4.5rem)] max-md:leading-[0.92]"
			>
				<span class="block">We resurrect old tech</span>
				<span class="block">and force it to perform.</span>
			</h1>
			<p class="mt-8 w-full max-w-2xl text-[clamp(1rem,1.4vw,1.25rem)] leading-[1.55] max-md:mt-6">
				ElectroNuck is Enoch and Nathan Bradshaw, software-engineer brothers who turn obsolete
				hardware into overbuilt instruments and document the mess on YouTube. Sometimes they build
				other things too.
			</p>
			<div class="mt-7 flex flex-wrap gap-x-8 gap-y-4 max-xs:flex-col max-xs:items-start">
				<a class="action text-crt" href={youtube} target="_blank" rel="noreferrer">
					Watch on YouTube <span aria-hidden="true">↗</span>
				</a>
				<a class="action text-paper" href="#projects"
					>Explore the projects <span aria-hidden="true">↓</span></a
				>
			</div>
		</div>

		<div
			class="relative mx-auto mt-[clamp(3rem,7vw,7rem)] grid w-full max-w-[90rem] grid-cols-[minmax(15rem,0.75fr)_minmax(5rem,0.2fr)_minmax(20rem,1.2fr)] items-end max-md:mt-16 max-md:grid-cols-1 max-md:gap-14"
			aria-label="The Cubical Collection instruments"
		>
			<figure class="artifact z-2 translate-y-6 -rotate-[1.4deg] border-crt max-md:transform-none">
				<img
					class="aspect-4/3 w-full object-cover contrast-105 saturate-[0.88]"
					src="/images/projects/synthphone-e.jpg"
					alt="A burgundy push-button telephone modified with an OLED and exposed electronics"
					width="1280"
					height="960"
				/>
			</figure>
			<div class="signal-path relative z-0 h-full min-h-32 max-md:hidden" aria-hidden="true">
				<span></span>
			</div>
			<figure
				class="artifact z-2 -translate-y-4 rotate-[0.8deg] border-laser max-md:transform-none"
			>
				<img
					class="aspect-4/3 w-full object-cover contrast-105 saturate-[0.88]"
					src="/images/projects/keyboard-keyboard.jpg"
					alt="A beige computer keyboard rebuilt with colored musical keys, knobs, and an OLED"
					width="1280"
					height="960"
				/>
			</figure>
		</div>
	</section>

	<section
		class="collection-section relative isolate mx-auto grid w-[calc(100%-2*var(--page-gutter))] max-w-[90rem] grid-cols-[minmax(18rem,0.75fr)_minmax(25rem,1fr)] items-center gap-[clamp(3rem,8vw,9rem)] py-[clamp(7rem,12vw,12rem)] text-paper max-md:grid-cols-1 max-md:gap-16"
		aria-labelledby="collection-title"
	>
		<div
			class="collection-mark relative mx-auto flex w-full max-w-xl -rotate-3 flex-col justify-center py-12 text-center"
		>
			<span class="meta">The</span>
			<strong
				class="font-display text-[clamp(2rem,5vw,5rem)] leading-[0.84] text-crt uppercase italic"
				>Cubical</strong
			>
			<strong
				class="font-display text-[clamp(2rem,5vw,5rem)] leading-[0.84] text-arc uppercase italic"
				>Collection</strong
			>
			<small class="meta mt-6 text-phosphor">Office equipment / musical consequences</small>
		</div>
		<div>
			<h2 id="collection-title" class="section-title">
				Musical instruments disguised as office equipment.
			</h2>
			<p class="mt-4 max-w-[62ch] text-[clamp(1rem,1.4vw,1.2rem)] leading-relaxed">
				The Cubical Collection combines a telephone that processes vocals with a computer keyboard
				that sends velocity-sensitive MIDI. Enoch and Nathan are bringing both instruments to Open
				Sauce 2026.
			</p>
			<div class="my-8 grid grid-cols-[0.7fr_1.3fr] border-y border-phosphor/30 max-md:grid-cols-1">
				<div class="flex flex-col gap-2 py-4">
					<span class="meta text-phosphor">Dates</span><strong class="text-sm"
						>July 17–19, 2026</strong
					>
				</div>
				<div class="flex flex-col gap-2 py-4 max-md:border-t max-md:border-phosphor/25">
					<span class="meta text-phosphor">Location</span><strong class="text-sm"
						>San Mateo County Event Center</strong
					>
				</div>
			</div>
			<a class="text-link" href={openSauce} target="_blank" rel="noreferrer"
				>View the official listing ↗</a
			>
		</div>
	</section>

	<section
		class="projects-section relative isolate mx-auto w-[calc(100%-2*var(--page-gutter))] max-w-[90rem] py-[clamp(6rem,10vw,10rem)]"
		id="projects"
		aria-labelledby="projects-title"
	>
		<header class="mb-[clamp(4rem,8vw,8rem)] flex justify-end">
			<h2 id="projects-title" class="section-title max-w-[18ch]">
				Bad ideas with working firmware.
			</h2>
		</header>

		<article
			class="project-panel project-phone grid grid-cols-[minmax(20rem,1.15fr)_minmax(20rem,0.85fr)] items-center gap-[clamp(3rem,7vw,8rem)] max-md:grid-cols-1"
		>
			<div class="project-image phone-image relative">
				<img
					class="aspect-4/3 w-full object-cover contrast-105 saturate-[0.88]"
					src="/images/projects/synthphone-e.jpg"
					alt="Synthphone-E on a workshop table"
					width="1280"
					height="960"
					loading="lazy"
				/>
			</div>
			<div class="project-console phone-console">
				<h3 class="project-title project-title-long">Synthphone-E</h3>
				<p class="mt-7 mb-4 text-[clamp(1.15rem,1.7vw,1.45rem)] leading-snug font-semibold">
					A real-time vocal processor and synthesizer built inside an old push-button telephone.
				</p>
				<p class="max-w-[58ch] leading-relaxed">
					The handset speaker acts as a deliberately lo-fi microphone while embedded hardware
					performs pitch correction, formant processing, vocoding, harmony, and percussion.
				</p>
				<div class="mt-7 flex flex-wrap gap-x-8 gap-y-4 max-xs:flex-col max-xs:items-start">
					<a class="text-link" href={resolve('/projects/synthphone-e')}>Read about Synthphone-E →</a
					>
					<a
						class="text-link text-paper"
						href="https://www.youtube.com/watch?v=1VQUEm7suBc"
						target="_blank"
						rel="noreferrer">Watch the build ↗</a
					>
				</div>
			</div>
		</article>

		<article
			class="project-panel project-keyboard mt-[clamp(7rem,13vw,14rem)] grid grid-cols-[minmax(20rem,0.75fr)_minmax(25rem,1.25fr)] items-center gap-[clamp(3rem,7vw,8rem)] max-md:grid-cols-1"
		>
			<div class="project-console keyboard-console max-md:order-2">
				<h3 class="project-title project-title-keyboard" aria-label="Keyboard squared">
					Keyboard<span class="keyboard-square" aria-hidden="true">2</span>
				</h3>
				<p class="mt-7 mb-4 text-[clamp(1.15rem,1.7vw,1.45rem)] leading-snug font-semibold">
					A velocity-sensitive MIDI instrument disguised as a full-size beige computer keyboard.
				</p>
				<p class="max-w-[58ch] leading-relaxed">
					Its 100 Hall-effect sensors turn an isomorphic Wicki-Hayden layout, control keys, and drum
					keys into an expressive surface for Synthphone-E and other MIDI hardware.
				</p>
				<div class="mt-7 flex flex-wrap gap-x-8 gap-y-4 max-xs:flex-col max-xs:items-start">
					<a class="text-link" href={resolve('/projects/keyboard-keyboard')}
						>Read about Keyboard² →</a
					>
					<a
						class="text-link text-paper"
						href="https://github.com/UnitedCode/keyboard-keyboard"
						target="_blank"
						rel="noreferrer">View the source ↗</a
					>
				</div>
			</div>
			<div class="project-image keyboard-image relative max-md:order-1">
				<img
					class="aspect-4/3 w-full object-cover contrast-105 saturate-[0.88]"
					src="/images/projects/keyboard-keyboard.jpg"
					alt="Keyboard² on a workshop table"
					width="1280"
					height="960"
					loading="lazy"
				/>
			</div>
		</article>
	</section>

	<section
		class="latest-section relative isolate mx-auto grid w-[calc(100%-2*var(--page-gutter))] max-w-[90rem] grid-cols-[minmax(25rem,1.2fr)_minmax(20rem,0.8fr)] items-center gap-[clamp(3rem,7vw,8rem)] py-[clamp(6rem,10vw,10rem)] max-md:grid-cols-1 max-md:gap-12"
		aria-labelledby="latest-title"
	>
		<div>
			<a
				class="media-window group relative block overflow-hidden border border-paper/40 border-b-3 border-b-arc"
				href="https://www.youtube.com/watch?v=MOTztv2FLxE"
				target="_blank"
				rel="noreferrer"
				aria-label="Watch POV: it's 2007 and your parents are fighting in the kitchen"
			>
				<img
					class="aspect-video w-full object-cover contrast-110 saturate-[0.78] transition duration-300 group-hover:scale-[1.015] group-hover:contrast-100 group-hover:saturate-100"
					src="https://i.ytimg.com/vi/MOTztv2FLxE/sddefault.jpg"
					alt=""
					width="640"
					height="480"
					loading="lazy"
				/>
				<span
					class="meta absolute right-0 bottom-0 flex items-center gap-3 bg-arc px-4 py-3 text-void"
					>Play <b aria-hidden="true">▶</b></span
				>
			</a>
		</div>
		<div>
			<h2 id="latest-title" class="section-title">
				POV: it's 2007 and your parents are fighting in the kitchen
			</h2>
			<p class="meta mt-5 text-phosphor">12:27 / February 27, 2026</p>
			<p class="mt-4 max-w-[62ch] text-[clamp(1rem,1.4vw,1.2rem)] leading-relaxed">
				A Unity VR bedroom where RuneScape, Scooby-Doo, and Linkin Park help drown out an argument
				in the kitchen. This time, the phone gets the day off.
			</p>
			<div class="mt-7 flex flex-wrap gap-x-8 gap-y-4 max-xs:flex-col max-xs:items-start">
				<a
					class="text-link"
					href="https://www.youtube.com/watch?v=MOTztv2FLxE"
					target="_blank"
					rel="noreferrer">Watch the video ↗</a
				>
				<a class="text-link text-paper" href={resolve('/videos')}>View all videos →</a>
			</div>
		</div>
	</section>

	<section
		class="about-section relative isolate mx-auto grid w-[calc(100%-2*var(--page-gutter))] max-w-[90rem] grid-cols-[1.1fr_0.9fr_0.9fr] gap-[clamp(2rem,5vw,6rem)] py-[clamp(6rem,10vw,10rem)] max-md:grid-cols-1 max-md:gap-14"
		id="about"
		aria-labelledby="about-title"
	>
		<div>
			<h2 id="about-title" class="section-title">Two brothers. No reasonable stopping point.</h2>
		</div>
		<div class="pt-2">
			<figure class="portrait portrait-enoch relative mb-9 border-b-2 border-crt">
				<img
					class="aspect-square w-full object-cover contrast-110 saturate-75"
					src="/images/people/enoch.jpg"
					alt="Enoch Bradshaw hanging upside down and making a face"
					width="800"
					height="800"
					loading="lazy"
				/>
			</figure>
			<h3 class="mb-3 text-xl font-semibold">Enoch Bradshaw</h3>
			<p class="leading-relaxed">
				Enoch comes up with the projects, writes software, builds vocal effects, makes the music,
				and performs. The telephone-microphone idea was his, along with most of the scope that
				followed.
			</p>
		</div>
		<div class="pt-2">
			<figure class="portrait portrait-nathan relative mb-9 border-b-2 border-arc">
				<img
					class="aspect-square w-full object-cover contrast-110 saturate-75"
					src="/images/people/nathan.jpg"
					alt="Nathan Bradshaw in front of the Golden Gate Bridge"
					width="800"
					height="800"
					loading="lazy"
				/>
			</figure>
			<h3 class="mb-3 text-xl font-semibold">Nathan Bradshaw</h3>
			<p class="leading-relaxed">
				Nathan handles the embedded systems, hardware, PCB design, Rust firmware, MIDI, and DSP
				architecture. He usually gets the part that sounded simple in the pitch.
			</p>
		</div>
	</section>
</main>

<SiteFooter />
