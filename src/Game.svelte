<script>
	import SmallGrid from './SmallGrid.svelte'
	import MovesHistory from './MovesHistory.svelte'

	export let state

	let gameWon = false
	let movesLeft = 3 * 3 // TODO make dynamic
	let currentPlayer = 'X'
</script>
<div class="card-body">
	<h4>Player {currentPlayer}'s turn</h4>
	{#if gameWon}
		<Alert colorClass="alert-success">
			Player {currentPlayer} won!
		</Alert>
	{/if}
	{#if movesLeft === 0}
		<Alert colorClass="alert-danger">
			No moves left!
		</Alert>
	{/if}
	<SmallGrid {state}/>
</div>
<div class="card-footer">
	<MovesHistory/>
</div>
