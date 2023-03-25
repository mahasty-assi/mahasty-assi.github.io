<script>
	import Menu from '$lib/Menu.svelte';
	let pageHeader = 'Garden of Things';
</script>

<div class="header-class"><h1>{pageHeader}</h1></div>
<div>
	<Menu />
</div>

<style>
	.header-class {
		height: 8em;
		display: flex;
		justify-content: center;
	}
	h1 {
		align-self: center;
	}
</style>
