<script>
  import Square from './Square.svelte';

	let state = {
		squares: Array(9).fill(''),
		xIsNext: true,
	};

	function handleClick(i) {
		const squares = state.squares.slice();
		squares[i] = state.xIsNext ? 'X' : 'O';
		state.squares = squares;
		state.xIsNext = !state.xIsNext;
	}	
</script>

<div class="status">Next player: {state.xIsNext ? 'X' : 'O'}</div>
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