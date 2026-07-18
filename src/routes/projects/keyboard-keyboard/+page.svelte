<script lang="ts">
	import { resolve } from '$app/paths';
	import SiteFooter from '$lib/components/SiteFooter.svelte';
	import SiteHeader from '$lib/components/SiteHeader.svelte';

	const source = 'https://github.com/UnitedCode/keyboard-keyboard';
	const openSauce =
		'https://www.opensauce.com/exhibits/the-cubical-collection-musical-instruments-disguised-as-office-equipment';
	const keys = Array.from({ length: 100 }, (_, index) => {
		const number = index + 1;
		return { number, group: number <= 70 ? 'melody' : number <= 80 ? 'control' : 'drum' };
	});
</script>

<svelte:head>
	<title>Keyboard² | ElectroNuck</title>
	<meta
		name="description"
		content="A velocity-sensitive MIDI instrument disguised as a full-size beige computer keyboard."
	/>
</svelte:head>

<SiteHeader />

<main>
	<section class="page-hero page-hero-keyboard" aria-labelledby="page-title">
		<div class="page-hero-copy">
			<a class="meta text-link" href={resolve('/#projects')}>← All projects</a>
			<h1 id="page-title" class="signal-title mt-10" aria-label="Keyboard squared">
				Keyboard<span class="keyboard-square" aria-hidden="true">2</span>
			</h1>
			<p class="page-lead">
				A 100-key, velocity-sensitive MIDI instrument disguised as a full-size beige computer
				keyboard.
			</p>
			<p class="max-w-[62ch] leading-relaxed text-paper/80">
				It extends Synthphone-E's office-equipment disguise into a second instrument, replacing
				QWERTY with an isomorphic musical surface, drum keys, controls, and twelve knobs.
			</p>
			<div class="mt-8 flex flex-wrap gap-x-8 gap-y-4">
				<a class="action text-crt" href={source} target="_blank" rel="noreferrer"
					>View the source ↗</a
				>
				<a class="action text-paper" href={resolve('/projects/keyboard-keyboard#key-map')}
					>Inspect the key map ↓</a
				>
			</div>
		</div>
		<figure class="page-artifact keyboard-artifact">
			<img
				src="/images/projects/keyboard-keyboard.jpg"
				alt="Keyboard², a beige computer keyboard rebuilt with colored musical keys, knobs, and an OLED"
				width="1280"
				height="960"
			/>
			<figcaption class="artifact-caption">
				<span>Artifact / active prototype</span><span>100 sensors / 12 knobs</span>
			</figcaption>
		</figure>
	</section>

	<section class="content-section content-split" aria-labelledby="idea-title">
		<div>
			<p class="meta text-laser">The disguise</p>
			<h2 id="idea-title" class="section-title mt-4">A Model M that never learned to type.</h2>
		</div>
		<div class="prose-stack">
			<p>
				Keyboard² uses the shell and proportions of a full-size IBM Model M-style office keyboard.
				The alphanumeric field plays notes, the function area changes settings, and the right side
				triggers drums.
			</p>
			<p>
				The beige shell still reads as office equipment until the colored keys and twelve knobs give
				it away.
			</p>
		</div>
	</section>

	<section id="key-map" class="key-map-section" aria-labelledby="map-title">
		<header class="content-heading">
			<p class="meta text-phosphor">Physical control map</p>
			<h2 id="map-title" class="section-title mt-4">One hundred reasons not to use QWERTY.</h2>
			<p>The key groups follow the firmware ranges, and the colors mark what each group does.</p>
		</header>
		<div
			class="keyboard-map"
			role="img"
			aria-label="100-key map: 70 melody keys, 10 control keys, and 20 drum keys"
		>
			{#each keys as key (key.number)}
				<span class={key.group} aria-hidden="true">{key.number}</span>
			{/each}
		</div>
		<div class="map-legend">
			<div>
				<i class="bg-crt"></i><strong>70 melody keys</strong><span>Wicki-Hayden layout</span>
			</div>
			<div>
				<i class="bg-arc"></i><strong>10 control keys</strong><span>Settings and performance</span>
			</div>
			<div>
				<i class="bg-laser"></i><strong>20 drum keys</strong><span>General MIDI percussion</span>
			</div>
			<div>
				<i class="knob-symbol"></i><strong>12 knobs</strong><span>MIDI Control Change</span>
			</div>
		</div>
	</section>

	<section class="content-section isomorphic-section" aria-labelledby="wicki-title">
		<div>
			<p class="meta text-crt">Wicki-Hayden geometry</p>
			<h2 id="wicki-title" class="section-title mt-4">Move the shape. Keep the chord.</h2>
			<p class="mt-6 max-w-[62ch] leading-relaxed">
				The melody area is isomorphic: every interval has the same spatial relationship everywhere
				on the board. Move a scale or chord to another starting note and the fingering geometry
				stays the same.
			</p>
		</div>
		<div
			class="note-geometry"
			role="img"
			aria-label="Repeated Wicki-Hayden chord shape on offset rows"
		>
			<div><i></i><i class="active"></i><i></i><i></i><i></i><i></i></div>
			<div><i></i><i></i><i class="active"></i><i></i><i class="active"></i><i></i></div>
			<div><i></i><i></i><i></i><i class="active"></i><i></i><i></i></div>
			<span class="meta">Same interval geometry / any root</span>
		</div>
	</section>

	<section class="velocity-section" aria-labelledby="velocity-title">
		<div
			class="velocity-graphic"
			role="img"
			aria-label="Key travel crossing two sensor thresholds over time"
		>
			<span class="threshold threshold-a">Threshold A</span>
			<span class="threshold threshold-b">Threshold B</span>
			<svg viewBox="0 0 600 260" aria-hidden="true">
				<path d="M20 35 C180 35 210 35 255 90 S310 220 570 220" />
				<line x1="0" y1="90" x2="600" y2="90" />
				<line x1="0" y1="185" x2="600" y2="185" />
				<circle cx="255" cy="90" r="7" />
				<circle cx="300" cy="185" r="7" />
			</svg>
			<b class="meta">Elapsed time → MIDI velocity</b>
		</div>
		<div>
			<p class="meta text-arc">Hall-effect velocity</p>
			<h2 id="velocity-title" class="section-title mt-4">Speed becomes velocity.</h2>
			<p class="mt-6 max-w-[62ch] leading-relaxed">
				Each key uses an analog magnetic sensor. The firmware measures how quickly the key moves
				between two actuation thresholds and converts that elapsed time into MIDI velocity. Faster
				travel produces a harder note.
			</p>
		</div>
	</section>

	<section class="signal-lab" aria-labelledby="firmware-title">
		<div class="content-heading">
			<p class="meta text-laser">Embedded Rust / RTIC</p>
			<h2 id="firmware-title" class="section-title mt-4">A thousand scans every second.</h2>
			<p>
				A Daisy Seed reads 100 sensors through analog multiplexers, filters their values, tracks
				each key state, calculates velocity, scans the knobs, and queues MIDI messages.
			</p>
		</div>
		<div class="firmware-strip">
			<div><strong>13</strong><span>analog multiplexers</span></div>
			<div><strong>1 kHz</strong><span>sensor scan task</span></div>
			<div><strong>100</strong><span>key state machines</span></div>
			<div><strong>12</strong><span>continuous controls</span></div>
			<div><strong>MIDI</strong><span>notes, drums, bend, CC</span></div>
		</div>
		<p class="state-machine meta">Idle → First actuated → Fully actuated → Released → Idle</p>
	</section>

	<section class="content-section connection-grid" aria-labelledby="connection-title">
		<div>
			<p class="meta text-crt">The collection connection</p>
			<h2 id="connection-title" class="section-title mt-4">Built to control the phone.</h2>
			<p class="mt-6 leading-relaxed">
				Keyboard² can send melody notes, chords, drum notes, pitch bend, and controller values to
				MIDI devices such as Synthphone-E. The two instruments share the office disguise and enough
				of the MIDI language to perform together.
			</p>
		</div>
		<div class="midi-connection" aria-hidden="true">
			<span>Keyboard²</span><i>MIDI OUT ········· MIDI IN</i><span>Synthphone-E</span>
		</div>
	</section>

	<section class="link-deck" aria-labelledby="links-title">
		<div>
			<p class="meta text-phosphor">Project records</p>
			<h2 id="links-title" class="section-title mt-4">Firmware, schematics, and exhibit notes.</h2>
		</div>
		<nav aria-label="Keyboard² links">
			<a href={source} target="_blank" rel="noreferrer"
				><span>Firmware and hardware source</span><b>GitHub ↗</b></a
			>
			<a href={openSauce} target="_blank" rel="noreferrer"
				><span>The Cubical Collection</span><b>Open Sauce ↗</b></a
			>
			<a href={resolve('/projects/synthphone-e')}
				><span>Synthphone-E</span><b>Related project →</b></a
			>
		</nav>
	</section>

	<nav class="project-switcher" aria-label="Other projects">
		<a href={resolve('/projects/synthphone-e')}
			><span class="meta">Previous project</span><strong>← Synthphone-E</strong></a
		>
		<a class="text-right" href={resolve('/videos')}
			><span class="meta">Keep watching</span><strong>Videos →</strong></a
		>
	</nav>
</main>

<SiteFooter />
