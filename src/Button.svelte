<script>
	import { Button } from 'sveltestrap'

	export let colorClass = "btn-primary"
	export let classes = ""
	export let disabled = ""
</script>
<Button
	color = "primary"
	class="btn {colorClass} {classes}"
	{disabled}
	on:click
>
	<slot/>
</Button>
