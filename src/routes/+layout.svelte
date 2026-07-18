<script lang="ts">
	import GoogleAnalytics from '$lib/components/GoogleAnalytics.svelte';
	import './layout.css';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href="/favicon.svg" type="image/svg+xml" />
	<link rel="icon" href="/favicon-96x96.png" type="image/png" sizes="96x96" />
	<link rel="shortcut icon" href="/favicon.ico" />
	<link rel="apple-touch-icon" href="/apple-touch-icon.png" sizes="180x180" />
	<meta name="apple-mobile-web-app-title" content="ElectroNuck" />
	<meta name="theme-color" content="#03050C" />
	<link rel="manifest" href="/site.webmanifest" />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500&family=IBM+Plex+Sans:ital,wght@0,400;0,600;1,400&display=swap"
		rel="stylesheet"
	/>
</svelte:head>
<GoogleAnalytics />
{@render children()}
