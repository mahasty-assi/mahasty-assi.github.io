<script>
	let menuItems = ['About', 'Comics', 'Illustrations', 'Other'];
</script>

<ul>
	{#each menuItems as item}
		<li><a href="/{item.toLowerCase()}">{item}</a></li>
	{/each}
</ul>

<style>
	ul {
		list-style-type: none;
		margin: 0;
		padding: 0;
		overflow: hidden;
		position: sticky;
		background: burlywood;
		display: flex;
		justify-content: space-evenly;
	}
	li {
		float: left;
		width: 30%;
	}
	li:hover {
		background-color: chocolate;
	}
	li > a {
		display: block;
		color: white;
		text-align: center;
		text-decoration: none;
		padding: 1em;
		font-family: sans-serif;
	}
</style>
