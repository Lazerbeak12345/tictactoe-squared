<script>
	import ClickableCell from './ClickableCell.svelte'
	export let state = "..."
</script>
<div class="row">
	{#each state as cell}
		{#if cell === " "}
			<ClickableCell/>
		{:else if cell === "."}
			<ClickableCell disabled/>
		{:else}
			<ClickableCell disabled>
				{cell}
			</ClickableCell>
		{/if}
	{/each}
</div>
