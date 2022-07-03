<script>
	import SmallGrid from './SmallGrid.svelte'
	import MovesHistory from './MovesHistory.svelte'

	export let state
	export let players

	let gameWon = false
	let movesLeft = 3 * 3 // TODO make dynamic
	let currentPlayer = 0
	let currentChar = players[currentPlayer]
</script>
<div class="card-body">
	<h4>Player {currentChar}'s turn</h4>
	{#if gameWon}
		<Alert colorClass="alert-success">
			Player {currentChar} won!
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
