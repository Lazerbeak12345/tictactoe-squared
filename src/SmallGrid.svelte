<script>
	import CellRow from './CellRow.svelte'
	export let state = [
		"...",
		"...",
		"...",
	]
</script>
{#each state as row}
	<CellRow state={row}/>
{/each}
