<script>
	import { Button } from 'sveltestrap'

	let settings = true
</script>
{#if settings}
	<Button
		on:click={()=>settings = false}
	>
		Play Game!
	</Button>
{/if}
