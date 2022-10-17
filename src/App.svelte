<script>
	import { Button } from 'sveltestrap'

	import Navbar from './Navbar.svelte'
	import Gameboard from './Gameboard.svelte'

	let settings = true
</script>
<Navbar/>
<div class="container-sm">
	<div class="row justify-content-center">
		<div class="col">
			{#if settings}
				<Button
					on:click={()=>settings = false}
				>
					Play Game!
				</Button>
			{/if}
		</div>
	</div>
</div>
<div>scoreboard</div>
