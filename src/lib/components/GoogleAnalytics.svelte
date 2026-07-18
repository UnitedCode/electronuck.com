<script lang="ts">
	import { PUBLIC_GA_MEASUREMENT_ID } from '$env/static/public';
	import { onMount } from 'svelte';

	const measurementId = PUBLIC_GA_MEASUREMENT_ID;

	onMount(() => {
		if (!measurementId || window.gtagMeasurementIds?.has(measurementId)) return;

		window.dataLayer ??= [];
		window.gtag ??= function gtag() {
			window.dataLayer.push(arguments);
		};
		window.gtagMeasurementIds ??= new Set();
		window.gtagMeasurementIds.add(measurementId);

		window.gtag('js', new Date());
		window.gtag('config', measurementId, {
			allow_google_signals: false,
			allow_ad_personalization_signals: false,
			send_page_view: true
		});

		const script = document.createElement('script');
		script.async = true;
		script.src = `https://www.googletagmanager.com/gtag/js?id=${measurementId}`;
		document.head.append(script);
	});
</script>
