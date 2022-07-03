<script>
	import CellRow from './CellRow.svelte'
	export let state = [
		"...",
		"...",
		"...",
	]
	export let disabled = false
</script>
{#each state as row}
	<CellRow state={row} {disabled}/>
{/each}
