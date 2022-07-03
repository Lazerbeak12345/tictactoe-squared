<script>
	import ClickableCell from './ClickableCell.svelte'
	export let state
	export let disabled = false
</script>
{#each state as row}
	<div class="row">
		{#each row as cell}
			{#if typeof cell === "string"}
				{#if cell === " "}
					<ClickableCell {disabled}/>
				{:else}
					<ClickableCell disabled>
						{cell}
					</ClickableCell>
				{/if}
			{:else}
				<div class="col border">
					<svelte:self state={cell} {disabled}/>
				</div>
			{/if}
		{/each}
	</div>
{/each}
