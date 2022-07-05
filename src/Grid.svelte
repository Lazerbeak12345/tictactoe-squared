<script>
	import { createEventDispatcher } from 'svelte';
	import ClickableCell from './ClickableCell.svelte'

	const dispatch = createEventDispatcher();

	export let state
	export let disabled = false
	export let currentChar

	function handleClick(x,y) {
		dispatch('click', { x, y })
		console.group("click", x, y, currentChar)
		console.log("before",state)
		state = [
			...state.slice(0, y),
			[
				...state[y].slice(0, x),
				currentChar,
				...state[y].slice(x+1)
			],
			...state.slice(y+1)
		]
		console.log("after",state)
		console.groupEnd("click")
	}
</script>
{#each state as row, y}
	<div class="row">
		{#each row as cell, x }
			{#if typeof cell === "string"}
				{#if cell === " "}
					<ClickableCell
						{disabled}
						on:click={()=>handleClick(x,y)}
					/>
				{:else}
					<ClickableCell disabled>
						{cell}
					</ClickableCell>
				{/if}
			{:else}
				<div
					class="col{
						y < state.length - 1
						? " border-bottom"
						: " mb-1"
					}{
						y === 0
						? " mt-1"
						: ""
					}{
						x < row.length - 1
						? " border-end"
						: " me-1"
					}{
						x === 0
						? " ms-1"
						: ""
					}"
				>
					<svelte:self state={cell} {disabled} on:click {currentChar}/>
				</div>
			{/if}
		{/each}
	</div>
{/each}
