<script context="module">
	import img from './ImgComponent.svelte';
	export { img };
</script>

<script>
	import EmojiSelector from './EmojiSelector.svelte';
	import { filename } from '$lib/filename';

	// https://github.com/pngwn/MDsveX/issues/485

	/** @type {string} */
	export let title;

	/** @type {string} */
	export let description;

	/** @type {string} */
	export let emojis;

	/** @type {string} */
	export let slug;

	$filename = `/src/routes/article/${slug}/+page.md`;
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content={description} />

	<!-- Meta Tags -->
	<meta name="description" content={description} />
	<link rel="canonical" href="https://leodog896.com/article/{slug}" />
	<meta name="keywords" content="blog, tech, programming, coding, programming article, article, post, LeoDog896" /> -->

	<!-- Open Graph Meta Tags -->
	<meta property="og:type" content="article" />
	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />
	<meta property="og:url" content="https://leodog896.com/article/{slug}" />
	<meta property="og:site_name" content="leodog896.com" />
	<meta property="og:locale" content="en_US" />
	<meta property="article:author" content="Tristan F." />

	<!-- Twitter Meta Tags -->
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={description} />
	<meta name="twitter:url" content="https://leodog896.com/article/{slug}" />
</svelte:head>

<h1>{title} <EmojiSelector emojis={emojis.split(' ')} /></h1>

<slot />
