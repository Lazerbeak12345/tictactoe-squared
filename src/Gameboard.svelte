<script>
	import Game from './Game.svelte'
	import Button from './Button.svelte'

	let settings = true
	let w = 3
	let h = 3
	let state = new Array(h)
		.fill(0)
		.map(() => new Array(w)
			.fill(0)
			.map(() => " "))
	console.log(state)
	let maxMoves = w * h
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
