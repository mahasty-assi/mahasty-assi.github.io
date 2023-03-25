<script>
	import { faChevronDown, faChevronUp } from '@fortawesome/free-solid-svg-icons';
	import Icon from 'fa-svelte';

	export let title, description, bonus, elementId, bgColor;
	let isOpen = false;
	function toggleOpen() {
		isOpen = !isOpen;
	}
</script>

<div class="comic-card" style="background-color: {bgColor}">
	<div on:click={() => toggleOpen('personal')} class="div-button">
		<h2>{title}</h2>
		<p>{description}</p>
		<p>{bonus}</p>
		<Icon icon={isOpen ? faChevronUp : faChevronDown} aria-hidden="true" />
	</div>
	{#if isOpen}
		<div id={elementId} class="comic-bulk">
			<img
				src="https://pbs.twimg.com/media/Ev6RC8dWEAQhsB3?format=jpg&name=large"
				alt="As a child i thought nail clippers would wake up zombies"
			/>
			<hr />
			<img
				src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/80188433-5dc8-446e-a937-65dc53d9a6bc/d4hgqb7-e41d78a4-4dc5-4bc8-a336-7ef46dbe3ab7.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzgwMTg4NDMzLTVkYzgtNDQ2ZS1hOTM3LTY1ZGM1M2Q5YTZiY1wvZDRoZ3FiNy1lNDFkNzhhNC00ZGM1LTRiYzgtYTMzNi03ZWY0NmRiZTNhYjcucG5nIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.fdWq-79qa9noQUhCI-splSdLMwmVV6g0Lr3_glsFbZQ"
				alt="turkish salad tutorial"
			/>
		</div>
	{/if}
</div>

<style>
	.comic-card {
		padding-bottom: 1em;
		width: 100%;
		text-align: center;
	}
	.comic-bulk {
		display: flex;
		justify-content: center;
		flex-direction: column;
	}
	h2 {
		font-family: 'Apple SD Gothic Neo';
	}
	img {
		width: 60%;
		align-self: center;
	}
	button {
		border: none;
		background: none;
		width: 100%;
		padding: 2em 0;
	}
	hr {
		display: block;
		margin: 1em auto;
		width: 100%;
		border-style: inset;
		border-width: 2px;
		border-color: firebrick;
	}
</style>
