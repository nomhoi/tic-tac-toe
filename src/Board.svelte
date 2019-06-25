<script>
	import Square from './Square.svelte';
	import { calculateWinner } from './helpers.js';
	
	let state = {
		squares: Array(9).fill(''),
		xIsNext: true,
	};
	
	$: winner = calculateWinner(state.squares);

	function handleClick(i) {
		if (winner || state.squares[i]) 
			return;
		
		const squares = state.squares.slice();
		squares[i] = state.xIsNext ? 'X' : 'O';
		state.squares = squares;
		state.xIsNext = !state.xIsNext;
	}	
</script>

<div class="status">
	{#if winner}
		<b>Winner: {winner}</b>
	{:else}
		Next player: {state.xIsNext ? 'X' : 'O'}
	{/if}
</div>
<div class="board">
	{#each state.squares as value, i}
		<Square {value} on:click={e => handleClick(i)} />
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