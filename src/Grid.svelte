<script>
	import ClickableCell from './ClickableCell.svelte'
	export let state
	export let disabled = false
</script>
{#each state as row, y}
	<div class="row">
		{#each row as cell, x }
			{#if typeof cell === "string"}
				{#if cell === " "}
					<ClickableCell {disabled}/>
				{:else}
					<ClickableCell disabled>
						{cell}
					</ClickableCell>
				{/if}
			{:else}
				<div
					class="col{
						y < state.length - 1
						? " border-bottom"
						: " mb-1"
					}{
						y === 0
						? " mt-1"
						: ""
					}{
						x < row.length - 1
						? " border-end"
						: " me-1"
					}{
						x === 0
						? " ms-1"
						: ""
					}"
				>
					<svelte:self state={cell} {disabled}/>
				</div>
			{/if}
		{/each}
	</div>
{/each}
