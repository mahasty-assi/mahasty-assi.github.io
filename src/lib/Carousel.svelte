<script>
	import Icon from 'fa-svelte';

	import { faChevronLeft } from '@fortawesome/free-solid-svg-icons/faChevronLeft';
	import { faChevronRight } from '@fortawesome/free-solid-svg-icons/faChevronRight';

	import t1 from '$lib/illustrations/klaevn.jpg';
	import t2 from '$lib/illustrations/QueenOrfWorms_June_2021.jpg';
	import t3 from '$lib/illustrations/Godijustlovethispiece.jpg';

	let images = [
		{ alt: 'Klovn', path: t1, id: 1 },
		{ alt: 'Gog aGog', path: t2, id: 2 },
		{ alt: 'Sword', path: t3, id: 3 },
		{ alt: 'Klovn', path: t1, id: 4 },
		{ alt: 'Gog aGog', path: t2, id: 5 },
		{ alt: 'Sword', path: t3, id: 6 },
		{ alt: 'Klovn', path: t1, id: 7 },
		{ alt: 'Gog aGog', path: t2, id: 8 },
		{ alt: 'Sword', path: t3, id: 9 }
	];

	function goToImg(index) {
		console.log(index)
	}
</script>

<section class="carousel" aria-label="carousel">
	<p class="sr-only">
		Carousel with three slides shown at a time. Use the Previous and Next buttons to navigate, or
		the slide dot buttons at the end to jump to slides.
	</p>

	<button class="previous">
		<Icon icon={faChevronLeft} aria-hidden="true" />
		<span class="sr-only">Previous slides</span>
	</button>

	<div class="slides">
		{#each images as image, idx}
			<div class="slide" role="group" aria-label={`slide ${image.id} of 9}`}>
				<img alt={image.alt} src={image.path} id={image.id} />
			</div>
		{/each}
	</div>

	<button class="next">
		<Icon icon={faChevronRight} aria-hidden="true" />
		<span class="sr-only">Next slides</span>
	</button>

	<ul class="navigation">
		{#each images as image, idx}
			<li>
				<button aria-current="true" on:click={goToImg()}>
					<span class="sr-only">Go to slide {idx}</span>
				</button>
			</li>
		{/each}
	</ul>
</section>

<style>
	:root {
		--carousel-height: 300px;
		--slide-width: calc(100% / 3);
	}
	/** Wrapper **********************/
	.carousel {
		position: relative;
		width: calc(100% - 40px);
		max-width: 900px;
		height: var(--carousel-height);
		margin: 0 auto;
		padding: 0 20px;
	}

	/** Previous/next buttons ********/
	.previous,
	.next {
		display: flex;
		justify-content: center;
		align-items: center;

		padding: 5px 10px;
		position: absolute;
		top: calc(50% - 16px);
		cursor: pointer;
		font-size: 32px;
		color: black;
		border: 0;
		background: none;
	}

	.previous {
		left: -30px;
	}
	.next {
		right: -30px;
	}

	/** Slides track ***************/
	.slides {
		list-style: none;
		padding: 0;
		margin: 0;

		display: flex;
		width: 100%;
		overflow: hidden;
	}

	/** Individual slides ***********/
	.slide > img {
		flex: 0 0 calc(100% / 3 - 10px);

		margin: 0 5px;
		padding: 20px;
		height: var(--carousel-height);
		display: flex;
		align-items: center;

		font-size: 18px;
		line-height: 26px;
		background: none;
	}

	@media screen and (max-width: 768px) {
		.slide {
			font-size: 14px;
			line-height: 18px;
			align-items: flex-start;
		}
	}

	.slide a {
		color: black;
		font-weight: bold;
	}

	/** Slide dots ******************/
	.navigation {
		position: absolute;
		left: 0;
		bottom: -40px;

		list-style: none;
		padding: 0;
		margin: 0;
		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
	}

	.navigation li {
		display: inline-block;
	}

	.navigation li button {
		display: block;
		width: 10px;
		height: 10px;
		margin: 0 5px;
		border: 0;
		border-radius: 100px;
		background-color: rgba(0, 0, 0, 0.2);
		cursor: pointer;
	}

	.navigation li button:focus {
		outline-offset: 4px;
	}

	/** Active slide dot */
	.navigation li button[aria-current='true'] {
		background-color: black;
		width: 15px;
		height: 15px;
	}
	.sr-only {
		position: absolute;
		left: -10000px;
		top: auto;
		width: 1px;
		height: 1px;
		overflow: hidden;
	}
</style>
