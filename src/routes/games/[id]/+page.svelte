<script lang="ts">
	import { fly, slide } from 'svelte/transition';
	import type { PageData } from './$types';

	let { data }: { data: PageData } = $props();

	console.log(data.gameInfo);

	let showing = $state(true);
</script>

{#if showing}
	<div
		in:fly={{ y: 40, duration: 300 }}
		out:fly={{ y: 40, duration: 300 }}
		class="fixed bottom-16 right-0 z-20 m-2 flex flex-row gap-2 overflow-hidden rounded border-t border-rose-500 bg-black bg-opacity-30 p-4 backdrop-blur"
	>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="currentColor"
			class="h-6 w-6"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12Z"
			/>
		</svg>
		Game Added to Wishlist

		<button onclick={() => (showing = false)}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="h-6 w-6"
			>
				<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
			</svg>
		</button>
	</div>
{/if}

<div class="relative mt-[-14px] h-44 w-full">
	<img
		src={data.gameInfo.header_image}
		alt={data.gameInfo.name}
		class="h-full w-full object-cover"
	/>
	<div class="absolute inset-x-0 bottom-0 h-1/2 bg-gradient-to-t from-black to-transparent"></div>
	<h3 class="absolute bottom-4 left-4 text-3xl font-bold text-white">{data.gameInfo.name}</h3>
</div>

<div class="relative ">
	<a href="/games/2" class="flex flex-row items-center gap-2 m-2" aria-label="Home">
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="currentColor"
			class="h-6 w-6 transition-all duration-300 hover:opacity-50 active:opacity-30"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12Z"
			/>
		</svg>

		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="currentColor"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="currentColor"
			class="h-6 w-6 text-rose-600 transition-all duration-300 hover:opacity-50 active:opacity-30"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12Z"
			/>
		</svg>
	</a>

	<p class="w-fit rounded-lg border border-white px-2 py-1 text-sm text-gray-300 m-2">Owned</p>

	<div class="m-2 flex w-fit flex-col rounded-lg border border-white p-3">
		<h2 class="text-2xl font-bold">2h 32m</h2>
		<p class="text-sm text-gray-300">How Long To Beat?</p>
	</div>

	<div class="flex flex-row gap-2 m-2">
	<div class="flex flex-row gap-2 rounded-lg border border-white p-2 items-center w-fit">
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="currentColor"
			class="h-6 w-6 text-white bg-green-500 rounded-full"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				d="M4.5 12.75l6 6 9-13.5"
			/>
		</svg>
		Verified
	</div>
	<div class="flex flex-row gap-2 rounded-lg border border-white p-2 items-center w-fit">
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="currentColor"
			class="h-6 w-6 text-white bg-yellow-500 rounded-full"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				d="M4.5 12.75l6 6 9-13.5"
			/>
		</svg>
		Playable
	</div>
	<div class="flex flex-row gap-2 rounded-lg border border-white p-2 items-center w-fit">
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="currentColor"
			class="h-6 w-6 text-white bg-gray-500 rounded-full"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9 5.25h.008v.008H12v-.008z"
			/>
		</svg>
		Untested
	</div>
	</div>
	<div class="relative m-2 flex h-24 w-24 items-center justify-center">
		<svg class="h-full w-full -rotate-90">
			<circle
				cx="48"
				cy="48"
				r="36"
				stroke="rgb(100 100 100)"
				stroke-width="8"
				fill="transparent"
				class="opacity-25"
			/>
			<circle
				cx="48"
				cy="48"
				r="36"
				stroke="#22c55e"
				stroke-width="8"
				fill="transparent"
				stroke-dasharray="226"
				stroke-dashoffset="56"
				class="transition-all duration-1000"
			/>
		</svg>
		<div class="absolute flex flex-col items-center">
			<span class="text-2xl font-bold">75</span>
			<span class="text-xs text-gray-400">Score</span>
		</div>
	</div>

	<div
		class="flex flex-row gap-4 overflow-x-auto pb-4 snap-x snap-mandatory [&::-webkit-scrollbar-thumb]:rounded-full [&::-webkit-scrollbar-thumb]:bg-gray-300 dark:[&::-webkit-scrollbar-thumb]:bg-gray-600 [&::-webkit-scrollbar-track]:rounded-full [&::-webkit-scrollbar-track]:bg-gray-100 dark:[&::-webkit-scrollbar-track]:bg-gray-800 [&::-webkit-scrollbar]:h-2"
	>
		{#each data.gameInfo.screenshots as screenshot}
			<div class="relative h-[200px] min-w-[350px] cursor-pointer snap-center">
				<img
					src={screenshot.path_full}
					alt="Game screenshot"
					class="h-full w-full rounded-lg object-cover"
				/>
			</div>
		{/each}
	</div>
</div>
<div class="flex flex-row gap-2 p-4">
	<button
		onclick={() => (showing = true)}
		class="w-fit rounded-lg bg-gradient-to-br from-green-500 to-green-700 p-2 text-green-200 shadow-lg transition-all duration-300 hover:shadow-[#22c55e88]"
	>
		23,00€
		<p class="text-xs">AllKeyShop</p>
	</button>

	<button class="w-fit rounded-lg bg-gradient-to-br from-blue-500 to-blue-700 p-2 text-blue-200">
		32,00€
		<p class="text-xs">Playstation</p>
	</button>

	<button
		class="w-fit rounded-lg bg-gradient-to-br from-purple-500 to-purple-700 p-2 text-blue-200"
	>
		32,00€
		<p class="text-xs">Steam</p>
	</button>
</div>
<div class=" p-4">
	<h2 class="text-2xl font-bold">Description</h2>
	<p class="">{@html data.gameInfo.about_the_game}</p>
</div>
