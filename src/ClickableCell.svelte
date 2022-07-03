<!-- TODO
- States
 - Disabled
-->
<script>
	let number // TODO this needs to be an input
</script>
<button class="btn col btn-primary m-1">
	{#if number === 1}
		X
	{:else if number === 2}
		O
	{:else}
		&nbsp;
	{/if}
</button>
