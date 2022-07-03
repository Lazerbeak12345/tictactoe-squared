<script>
	import SmallGrid from './SmallGrid.svelte'
	import Alert from './Alert.svelte'
	import MovesHistory from './MovesHistory.svelte'

	// TODO split this into two screens, one for making settings.

	let movesLeft = 3 * 3 // TODO make dynamic
	let currentPlayer = 'X'
	let gameWon = false
</script>
<div class="card">
	<div class="card-body">
		{#if gameWon}
			<Alert colorClass="alert-success" body="Player {currentPlayer} won!"/>
		{/if}
		{#if movesLeft === 0}
			<Alert colorClass="alert-danger" body="No moves left!"/>
		{/if}
		<span>Player {currentPlayer}'s turn</span>
		<SmallGrid/>
		<MovesHistory/>
	</div>
</div>
