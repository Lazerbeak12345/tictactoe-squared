<script>
	export let colorClass = "btn-primary"
	export let classes = ""
	export let disabled = ""
</script>
<button
	class="btn {colorClass} {classes}"
	{disabled}
	on:click
>
	<slot/>
</button>
