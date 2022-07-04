<script>
	// TODO TBH I need to do a bit more aria stuff
	export let ariaDescribedby
	export let value
</script>
<input
	type="number"
	step="1"
	class="form-control"
	aria-describedby={ariaDescribedby}
	{value}
	on:change>
