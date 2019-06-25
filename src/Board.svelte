<script>
  import Square from './Square.svelte';
</script>

<div class="status">Next player: X</div>
<div class="board">
	{#each Array(9) as square}
		<Square />
	{/each}
</div>

<style>
	.board {
		width: 102px;
	}
	
	.status {
		margin-bottom: 10px;
	}	
</style>