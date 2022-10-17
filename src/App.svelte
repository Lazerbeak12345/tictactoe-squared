<script>
	import { Button } from 'sveltestrap'

	let a = true
</script>
{#if a}
	<Button
		on:click={()=>a = false}
	>
		Click me!
	</Button>
{/if}
