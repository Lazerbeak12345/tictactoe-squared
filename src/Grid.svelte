<script>
	import ClickableCell from './ClickableCell.svelte'
	export let state = [
		"   ",
		"   ",
		"   ",
	]
	export let disabled = false
</script>
{#each state as row}
	<div class="row">
		{#each row as cell}
			{#if cell === " "}
				<ClickableCell {disabled}/>
			{:else}
				<ClickableCell disabled>
					{cell}
				</ClickableCell>
			{/if}
		{/each}
	</div>
{/each}
