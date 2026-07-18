<script lang="ts">
	import { resolve } from '$app/paths';
	import SiteFooter from '$lib/components/SiteFooter.svelte';
	import SiteHeader from '$lib/components/SiteHeader.svelte';

	const video = 'https://www.youtube.com/watch?v=1VQUEm7suBc';
	const short = 'https://www.youtube.com/shorts/urLUqi2jPyE';
	const talk = 'https://www.youtube.com/watch?v=6v_yg4s-u_g';
	const dsp = 'https://github.com/nathansbradshaw/synthphone_e_vocal_dsp';
	const openSauce =
		'https://www.opensauce.com/exhibits/the-cubical-collection-musical-instruments-disguised-as-office-equipment';

	const capabilities = [
		['Pitch', 'Correction and shifting toward selected musical notes'],
		['Formant', 'Preservation and deliberate vocal-character changes'],
		['Vocoder', 'Voice-shaped synthesis from a harmonically rich carrier'],
		['Harmony', 'Multiple MIDI-controlled target frequencies'],
		['Texture', 'Bit-depth and sample-rate reduction'],
		['Instrument', 'MIDI synthesis, percussion, keypad controls, and OLED menus']
	];
</script>

<svelte:head>
	<title>Synthphone-E | ElectroNuck</title>
	<meta
		name="description"
		content="A real-time vocal processor, synthesizer, and MIDI instrument built inside an old telephone."
	/>
</svelte:head>

<SiteHeader />

<main>
	<section class="page-hero page-hero-phone" aria-labelledby="page-title">
		<div class="page-hero-copy">
			<a class="meta text-link" href={resolve('/#projects')}>← All projects</a>
			<h1 id="page-title" class="signal-title mt-10">Synthphone-E</h1>
			<p class="page-lead">
				A real-time vocal-effects processor, synthesizer, and MIDI instrument built inside an old
				telephone.
			</p>
			<p class="max-w-[62ch] leading-relaxed text-paper/80">
				The handset's original speaker is used in reverse as a deliberately lo-fi microphone. A
				Daisy Seed inside the phone handles the audio processing, synthesis, controls, and display.
			</p>
			<div class="mt-8 flex flex-wrap gap-x-8 gap-y-4">
				<a class="action text-crt" href={video} target="_blank" rel="noreferrer"
					>Watch the build ↗</a
				>
				<a class="action text-paper" href={dsp} target="_blank" rel="noreferrer"
					>Inspect the vocal DSP ↗</a
				>
			</div>
		</div>
		<figure class="page-artifact phone-artifact">
			<img
				src="/images/projects/synthphone-e.jpg"
				alt="Synthphone-E, a burgundy push-button telephone with an OLED and exposed electronics"
				width="1280"
				height="960"
			/>
			<figcaption class="artifact-caption">
				<span>Artifact / active prototype</span><span>Daisy Seed / embedded Rust</span>
			</figcaption>
		</figure>
	</section>

	<section class="content-section content-split" aria-labelledby="origin-title">
		<div>
			<p class="meta text-crt">The original request</p>
			<h2 id="origin-title" class="section-title mt-4">How a microphone became Synthphone-E.</h2>
		</div>
		<div class="scope-chain" aria-label="How the project grew in scope">
			<div><b>01</b><span>Speak into a telephone handset speaker</span></div>
			<div><b>02</b><span>Use a thrift-store phone as the enclosure</span></div>
			<div><b>03</b><span>Give the unused buttons a synthesizer</span></div>
			<div><b>04</b><span>Add real-time vocal processing</span></div>
			<div><b>05</b><span>Keep adding modes instead of stopping</span></div>
		</div>
	</section>

	<section class="content-section" aria-labelledby="capabilities-title">
		<header class="content-heading">
			<p class="meta text-phosphor">Current capabilities</p>
			<h2 id="capabilities-title" class="section-title mt-4">The phone has profiles now.</h2>
			<p>
				The firmware has grown since the 2025 build video. These are the modes running on the
				current prototype.
			</p>
		</header>
		<div class="capability-grid mt-14">
			{#each capabilities as capability, index (capability[0])}
				<article>
					<span class="meta">0{index + 1}</span>
					<h3>{capability[0]}</h3>
					<p>{capability[1]}</p>
				</article>
			{/each}
		</div>
	</section>

	<section class="signal-lab" aria-labelledby="signal-title">
		<div class="content-heading">
			<p class="meta text-crt">Embedded signal path</p>
			<h2 id="signal-title" class="section-title mt-4">The voice goes in. Math happens.</h2>
			<p>
				Audio moves through overlapping windows so frequency-domain effects can run continuously
				without stopping the real-time input and output path.
			</p>
		</div>
		<div class="signal-chain" aria-label="Synthphone-E audio processing signal chain">
			<div>
				<span class="meta">Input</span><strong>Handset</strong><small
					>Lo-fi speaker transducer</small
				>
			</div>
			<i aria-hidden="true">→</i>
			<div>
				<span class="meta">Capture</span><strong>48 kHz</strong><small>Continuous ring buffer</small
				>
			</div>
			<i aria-hidden="true">→</i>
			<div>
				<span class="meta">Analyze</span><strong>FFT</strong><small>Overlapping audio windows</small
				>
			</div>
			<i aria-hidden="true">→</i>
			<div>
				<span class="meta">Transform</span><strong>DSP</strong><small
					>Pitch / formant / vocode</small
				>
			</div>
			<i aria-hidden="true">→</i>
			<div>
				<span class="meta">Output</span><strong>Audio</strong><small
					>Reconstructed in real time</small
				>
			</div>
		</div>
		<div class="definition-grid">
			<article>
				<h3>Pitch correction</h3>
				<p>Moves the detected voice toward a musical note without changing playback speed.</p>
			</article>
			<article>
				<h3>Formants</h3>
				<p>Preserve or alter the resonant character of the voice separately from pitch.</p>
			</article>
			<article>
				<h3>Vocoding</h3>
				<p>Applies the changing spectral shape of the voice to a synthesized carrier.</p>
			</article>
		</div>
	</section>

	<section class="link-deck" aria-labelledby="links-title">
		<div>
			<p class="meta text-phosphor">External records</p>
			<h2 id="links-title" class="section-title mt-4">Build logs and source.</h2>
		</div>
		<nav aria-label="Synthphone-E links">
			<a href={video} target="_blank" rel="noreferrer"
				><span>Main build video</span><b>18:07 ↗</b></a
			>
			<a href={short} target="_blank" rel="noreferrer"
				><span>Original introduction</span><b>Short ↗</b></a
			>
			<a href={talk} target="_blank" rel="noreferrer"
				><span>Springfield Devs talk</span><b>Recording ↗</b></a
			>
			<a href={dsp} target="_blank" rel="noreferrer"
				><span>Vocal DSP repository</span><b>Source ↗</b></a
			>
			<a href={openSauce} target="_blank" rel="noreferrer"
				><span>The Cubical Collection</span><b>Open Sauce ↗</b></a
			>
		</nav>
	</section>

	<nav class="project-switcher" aria-label="Other projects">
		<a href={resolve('/')}><span class="meta">Return</span><strong>ElectroNuck home</strong></a>
		<a class="text-right" href={resolve('/projects/keyboard-keyboard')}
			><span class="meta">Next project</span><strong>Keyboard² →</strong></a
		>
	</nav>
</main>

<SiteFooter />
