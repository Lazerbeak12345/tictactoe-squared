<script>
	export let history
</script>
<ol>
	{#each history as item}
		<li>{item.player} {item.x} {item.y}</li>
	{/each}
</ol>
