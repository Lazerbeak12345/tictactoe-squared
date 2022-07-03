<script>
	import Game from './Game.svelte'
	import Button from './Button.svelte'

	let settings = true
	let state = [
		"   ",
		"   ",
		"   "
	]
	let maxMoves = 9
	let players = "XO"
</script>
<div class="card">
	{#if settings}
		<div class="card-body">
			<ul>
				<li>3 x 3 grid</li>
				<li>2 Player, X and O</li>
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
		<Game {state} {players} {maxMoves}/>
	{/if}
</div>
