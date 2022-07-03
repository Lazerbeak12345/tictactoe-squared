<script>
	import Game from './Game.svelte'
	import Alert from './Alert.svelte'
	import MovesHistory from './MovesHistory.svelte'
	import Button from './Button.svelte'

	let settings = true
	let currentPlayer = 'X'
	let state = [
		"   ",
		"   ",
		"   "
	]
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
		<Game {state}/>
	{/if}
</div>
