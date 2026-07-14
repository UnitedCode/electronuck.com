<script lang="ts">
	const youtube = 'https://www.youtube.com/@ElectroNuck';
</script>

<footer
	class="mx-auto grid w-[calc(100%-2*var(--page-gutter))] max-w-[90rem] grid-cols-[auto_1fr] items-end gap-x-12 gap-y-4 border-t border-phosphor/30 py-12 font-mono text-xs max-md:grid-cols-1"
>
	<div class="font-display text-xl font-extrabold text-crt uppercase italic">
		ElectroNuck <span class="text-laser">///</span>
	</div>
	<p class="m-0 text-phosphor">Obsolete technology. Newly introduced problems.</p>
	<nav
		class="col-span-full mt-6 flex flex-wrap gap-x-8 gap-y-4 max-md:col-span-1 max-md:flex-col"
		aria-label="Source links"
	>
		<a class="no-underline hover:text-crt" href={youtube} target="_blank" rel="noreferrer"
			>YouTube ↗</a
		>
		<a
			class="no-underline hover:text-crt"
			href="https://github.com/UnitedCode/keyboard-keyboard"
			target="_blank"
			rel="noreferrer">Keyboard² source ↗</a
		>
		<a
			class="no-underline hover:text-crt"
			href="https://github.com/nathansbradshaw/synthphone_e_vocal_dsp"
			target="_blank"
			rel="noreferrer">Vocal DSP source ↗</a
		>
	</nav>
</footer>
