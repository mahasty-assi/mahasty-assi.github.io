<script>
	import Menu from '$lib/Menu.svelte';
	export let description;
	let pageHeader = 'Garden of Things';
</script>

<div class="full-width">
	<div class="header-class"><a href="/"><h1>{pageHeader}</h1></a></div>
	<div>
		<Menu />
	</div>
	{#if description !== undefined}
		<div class="content">
			<p>{description}</p>
		</div>
	{:else}
		<div style=" padding: 2em"></div>
	{/if}
</div>

<style>
	* {
		box-sizing: border-box;
	}
	.full-width {
		width: 100%;
		text-align: center;
	}
	.content {
		padding-top: 2em;
	}
	.header-class {
		display: flex;
		justify-content: center;
		border: none;
		background: none;
		height: 8em;
	}
	h1 {
		align-self: center;
	}
	a {
		color: cornflowerblue;
		text-decoration: none;
		padding: 0;
		display: flex;
	}
	h1:hover {
		color: royalblue;
	}
</style>
