<script>
	import Game from './Game.svelte'
	import Button from './Button.svelte'

	let settings = true
	let w = 3
	let h = 3
	let win = 3
	$: state = new Array(h)
		.fill(0)
		.map(() => new Array(w)
			.fill(0)
			.map(() => " "))
	$: maxMoves = w * h
	let players = "XO"
</script>
<div class="card">
	{#if settings}
		<div class="card-body">
			<label class="form-label">
				Size
			</label>
			<div class="input-group">
				<span class="input-group-text" id="w">Width</span>
				<input
					type="number"
					step="1"
					class="form-control"
					aria-describedby="w"
					value="3"
					on:change={e => w = parseInt(e.target.value)}>
				<span class="input-group-text" id="h">Height</span>
				<input
					type="number"
					step="1"
					class="form-control"
					aria-describedby="h"
					value="3"
					on:change={e => h = parseInt(e.target.value)}>
			</div>
			<label class="form-label">
				Number in a row to win
			</label>
			<input
				type="number"
				step="1"
				class="form-control"
				aria-describedby="h"
				value="3"
				on:change={e => win = parseInt(e.target.value)}>
			<ul>
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
