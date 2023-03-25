<script>
	import Page from '$lib/Page.svelte';
	import ComicCard from '$lib/ComicCard.svelte';

	// comic page structured like...
	// each comic needs to have its own lane
	// with a preview image and a description
	// clicking on one displays the comic
	// maybe in the beginning have cubari or imgur embeds?
</script>

<Page />
<div class="comic-container">
	<ComicCard
		title="Personal comics"
		description="Comics in loose format written drawn from my own experiences."
		bonus="(not to be taken too seriously)"
		elementId="personal"
		bgColor="#ffc282"
	/>
	<hr />
	<ComicCard
		title="War for Rayuba comics"
		description="In 2020 I joined an Original Character Tournament called War for Rayuba and made some comics for it."
		bonus="My character was named Atte and my first opponent was a warrior named Tarpan by artist Lew Ro(@lewroh on twitter)"
		elementId="w4r"
		bgColor="#6495ED"
	/>
	<hr />
	<ComicCard
		title="Humans and Horrors comics"
		description="In 2022 I joined an Original Character Tournament called Humans and horrors and made some comics for it."
		bonus="My character was named Anklebiter"
		elementId="hnh"
		bgColor="#DDA0DD"
	/>
</div>

<style>
	.comic-container {
		padding: 0 10em;
		display: flex;
		justify-content: center;
		flex-direction: column;
	}
	hr {
		height: 1em;
		border: none;
	}
</style>
