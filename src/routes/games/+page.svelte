<script lang="ts">
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';

	let games = [
		{
			id: 1,
			gameId: 1091500,
			name: 'Cyberpunk 2077',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/1091500/header.jpg'
		},
		{
			id: 2,
			gameId: 730,
			name: 'Counter-Strike 2',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/730/header.jpg'
		},
		{
			id: 3,
			gameId: 782330,
			name: 'Doom Eternal',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/782330/header.jpg'
		},
		{
			id: 4,
			gameId: 620,
			name: 'Portal 2',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/620/header.jpg'
		},
		{
			id: 5,
			gameId: 220,
			name: 'Half-Life 2',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/220/header.jpg'
		},
		{
			id: 6,
			gameId: 298740,
			name: 'The Witcher 3: Wild Hunt',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/489830/header.jpg'
		},
		{
			id: 7,
			gameId: 489830,
			name: 'The Elder Scrolls V: Skyrim',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/489830/header.jpg'
		},
		{
			id: 8,
			gameId: 271590,
			name: 'Grand Theft Auto V',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/271590/header.jpg'
		},
		{
			id: 9,
			gameId: 620,
			name: 'Portal 2',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/620/header.jpg'
		},
		{
			id: 10,
			gameId: 220,
			name: 'Half-Life 2',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/220/header.jpg'
		},
		{
			id: 11,
			gameId: 298740,
			name: 'The Witcher 3: Wild Hunt',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/489830/header.jpg'
		},
		{
			id: 12,
			gameId: 489830,
			name: 'The Elder Scrolls V: Skyrim',
			image: 'https://cdn.akamai.steamstatic.com/steam/apps/489830/header.jpg'
		}
	];
</script>
<div class="flex flex-row mx-2 mt-2">
	<input
	type="text"
	placeholder="Search for a game"
	class="flex-1 rounded-lg border border-neutral-600 bg-black p-1 mr-4"
/>
	<button class="text-rose-500 flex flex-row items-center gap-2">
		<svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8" viewBox="0 0 512 512"><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="32" d="M32 144h448M112 256h288M208 368h96"/></svg>
	<p>Filter</p>
	</button>
</div>

<div class="grid grid-cols-2 gap-2 p-2 md:grid-cols-3 lg:grid-cols-4">
	{#each games as game, index (game)}
		<a
			in:fade={{ delay: index * 200 }}
			href="/games/{game.gameId}"
			class="flex flex-col gap-2 transition-all duration-300 hover:scale-105"
		>
			<img src={game.image} alt={game.name} class="w-full rounded object-cover" />
			<h3 class=" font-bold">{game.name}</h3>
		</a>
	{/each}
</div>
