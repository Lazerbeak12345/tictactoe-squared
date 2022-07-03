<script>
	import ClickableCell from './ClickableCell.svelte'
	export let state = "..."
	export let disabled = false
</script>
<div class="row">
	{#each state as cell}
		{#if disabled || cell === "."}
			<ClickableCell disabled/>
		{:else if cell === " "}
			<ClickableCell/>
		{:else}
			<ClickableCell disabled>
				{cell}
			</ClickableCell>
		{/if}
	{/each}
</div>
