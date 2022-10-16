<script>
	import { Alert } from 'sveltestrap';

	import Grid from './Grid.svelte'
	import MovesHistory from './MovesHistory.svelte'

	export let state
	export let maxMoves
	export let players

	let gameWon = false
	let movesLeft = maxMoves
	let currentPlayer = 0
	$: currentChar = players[currentPlayer]
	let history = []

	function clickHandle(event) {
		let { x, y } = event.detail
		history = [
			...history,
			{ x, y, player: currentChar }
		]
		currentPlayer = (currentPlayer + 1) % players.length
		movesLeft = movesLeft - 1
	}
</script>
<div class="card-body">
	<h4>Player {currentChar}'s turn</h4>
	{#if gameWon}
		<Alert color="success">
			Player {currentChar} won!
		</Alert>
	{/if}
	{#if movesLeft === 0}
		<Alert color="danger">
			No moves left!
		</Alert>
	{/if}
	<Grid {state} disabled={gameWon} {currentChar} on:click={clickHandle}/>
</div>
<div class="card-footer">
	<MovesHistory {history}/>
</div>
