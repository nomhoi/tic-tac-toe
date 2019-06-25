<script>
	import Board from './Board.svelte';
</script>

<div class="game">
	<div class="game-board">
		<Board />
	</div>
	<div class="game-info">
		<div></div>
		<ol></ol>
	</div>
</div>

<style>
	.game {
		font: 14px "Century Gothic", Futura, sans-serif;
		margin: 20px;
		display: flex;
		flex-direction: row;
	}

	.game-info {
		margin-left: 20px;
	}

	ol {
		padding-left: 30px;
	}
</style>