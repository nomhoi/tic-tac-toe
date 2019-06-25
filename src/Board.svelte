<script>
	import Square from './Square.svelte';
	
	let state = {
		squares: Array(9).fill(''),
	};
	
	function handleClick(i) {
		const squares = state.squares.slice();
		squares[i] = 'X';
		state.squares = squares;
	}
</script>

<div class="status">Next player: X</div>
<div class="board">
	{#each state.squares as value, i}
		<Square {value} on:click={e => handleClick(i)}/>
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