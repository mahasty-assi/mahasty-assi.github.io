<script>
	import { faChevronDown, faChevronUp } from '@fortawesome/free-solid-svg-icons';
	import Icon from 'fa-svelte';
	import t1 from '$lib/illustrations/klaevn.jpg';
	import t2 from '$lib/illustrations/QueenOrfWorms_June_2021.jpg';
	import t3 from '$lib/illustrations/Godijustlovethispiece.jpg';

	export let year, description, bonus, elementId;

	let images = [
		{ alt: 'Klovn', path: t1, id: 1 },
		{ alt: 'Gog aGog', path: t2, id: 2 },
		{ alt: 'Sword', path: t3, id: 3 }
	];

	let isOpen = false;
	function toggleOpen() {
		isOpen = !isOpen;
	}
</script>

<div>
	<div on:click={toggleOpen} class="div-button">
		<h2>{year} <Icon icon={isOpen ? faChevronUp : faChevronDown} aria-hidden="true" /></h2>
	</div>
	{#if isOpen}
		<div class="inside-card">
			<div>
				<p>{description} | Mediums: {bonus}</p>
			</div>
			{#each images as image}
				<img src={image.path} alt={image.alt} />
			{/each}
		</div>
	{/if}
</div>

<style>
	img {
		height: 20em;
		margin: 0 2em;
	}
	p {
		padding: 1em;
		background-color: rgba(181, 202, 243, 0.98);
	}
	.div-button {
		display: flex;
		justify-content: left;
		background-color:#fff3e6;
		padding: 1em;
		margin: 1%;
		background-image: linear-gradient(
				to right,
				rgba(255, 243, 230, 100),
				rgba(255, 255, 255, 0.1)
		), url("$lib/illustrations/Banner.png");
	}
	.inside-card {
		margin: 1%;
	}
</style>
