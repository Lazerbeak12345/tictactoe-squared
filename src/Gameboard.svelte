<script>
	import SmallGrid from './SmallGrid.svelte'
	import Alert from './Alert.svelte'
	import MovesHistory from './MovesHistory.svelte'
	import Button from './Button.svelte'

	let settings = true

	let currentPlayer = 'X'
	let gameWon = false
	let state = [
		"   ",
		"   ",
		"   "
	]
	let movesLeft = 3 * 3 // TODO make dynamic
</script>
<div class="card">
	{#if settings}
		<div class="card-body">
			<ul>
				<li>3 x 3 grid</li>
				<li>2 Player</li>
				<li>X goes first</li>
			</ul>
		</div>
		<div class="card-footer text-end">
			<Button
				colorClass="btn-success"
				on:click={()=>settings = false}
			>
				Play Game!
			</Button>
		</div>
	{:else}
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
	{/if}
</div>
