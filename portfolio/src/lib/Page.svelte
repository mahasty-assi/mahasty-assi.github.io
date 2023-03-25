<script>
	import Header from '$lib/Header.svelte';
	export let description;
</script>

<div class="full-width">
	<Header />
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
</style>
