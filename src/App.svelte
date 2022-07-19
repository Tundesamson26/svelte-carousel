<script>
	import Carousel from './carousels/SvelteCarousel.svelte'
	import SvelteTransition from './carousels/SvelteTransition.svelte'
	import SvelteSiema from './carousels/SvelteSiema.svelte'

</script>

<main>
	<h1>Svelte-carousel</h1>
	<Carousel />
	<h1>Svelte Transition</h1>
	<SvelteTransition />
	<h1>Siema Carousel</h1>
	<SvelteSiema />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>