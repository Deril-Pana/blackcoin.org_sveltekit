<script>
	import Hero from '$lib/components/home/hero.svelte';
	import About from '$lib/components/home/about.svelte';
	import Exchange from '$lib/components/home/exchange.svelte';
	import Downloads from '$lib/components/home/downloads.svelte';
	import SocialMedia from '$lib/components/home/social.svelte';
	import Donations from '$lib/components/home/donations.svelte';
	let lang = 'en';

	export let width;
	export let height;
  </script>

<svelte:window bind:innerWidth={width} bind:innerHeight={height} />

<svelte:head>
	<title>BlackcoinOrg</title>
	<meta name="description" content="BlackcoinOrg" />
	<meta name="lang" content={lang} />
</svelte:head>

<div id="home" />
<Hero {lang}  bind:width bind:height />
<About {lang} />
<Exchange {lang} />
<Downloads {lang} />
<SocialMedia {lang} />
<Donations {lang} bind:width />
