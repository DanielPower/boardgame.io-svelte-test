<script lang="ts">
	import type { SquidChessUserView } from '$lib/games/squid_chess';
	import type { Writable } from 'svelte/store';
	import Board from './Board.svelte';
	import Chat from '../Chat.svelte';
	import Hand from './Hand.svelte';
	import Join from './Join.svelte';

	export let gameState: Writable<SquidChessUserView>;
</script>

<div class="flex h-full">
	<div class="flex flex-grow flex-col items-center justify-center gap-12">
		<Hand {gameState} player="white" />
		<Board {gameState} />
		<Hand {gameState} player="black" />
		<Join {gameState} />
	</div>
	<Chat {gameState} />
</div>
