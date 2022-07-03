<script>
	import Button from './Button.svelte'
	export let disabled = false
</script>
<Button classes="col m-1" {disabled}>
	<slot>&nbsp;</slot>
</Button>
