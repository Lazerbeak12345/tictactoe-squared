<script>
	import Grid from './Grid.svelte'
	import MovesHistory from './MovesHistory.svelte'

	export let state
	export let players

	let gameWon = false
	let movesLeft = 3 * 3 // TODO make dynamic
	let currentPlayer = 0
	let currentChar = players[currentPlayer]
	let history = []

	function clickHandle(event) {
		let { x, y } = event.detail
		history = [
			...history,
			{ x, y, player: currentChar }
		]
	}
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
	<Grid {state} disabled={gameWon} {currentChar} on:click={clickHandle}/>
</div>
<div class="card-footer">
	<MovesHistory {history}/>
</div>
