<script lang="ts">
	export let menuOpen = false;

	import { fade } from 'svelte/transition';
</script>

<div class="relative w-4 h-4">
	<button
		class={`rounded-full w-4 h-4 absolute z-30 transition-colors duration-300 ${
			menuOpen ? 'bg-white' : 'bg-black'
		}`}
		on:click={() => (menuOpen = !menuOpen)}
	>
		<span class="sr-only">Menu</span>
	</button>
	<div
		class={`absolute inset-0 rounded-full bg-black z-10 w-4 h-4  transition-transform ease-in duration-500 ${
			menuOpen ? 'scale-[400]' : ''
		}`}
	/>
</div>

{#if menuOpen}
	<nav class={`absolute z-20 inset-0 mt-32 ml-8 flex flex-col`}>
		<ul>
			<li class="my-4">
				<a
					href="/"
					class="text-white font-black text-5xl"
					in:fade={{ duration: 300 }}
					out:fade={{ duration: 300, delay: 200 }}>home</a
				>
			</li>
			<li class="my-4">
				<a
					href="/"
					class="text-white font-black text-5xl"
					in:fade={{ duration: 300, delay: 100 }}
					out:fade={{ duration: 300, delay: 100 }}>work</a
				>
			</li>
			<li class="my-4">
				<a
					href="/"
					class="text-white font-black text-5xl"
					in:fade={{ duration: 300, delay: 200 }}
					out:fade={{ duration: 300 }}>get in touch</a
				>
			</li>
		</ul>
		<a href="/" class="text-white mt-auto mb-8 text-lg" transition:fade={{ duration: 300 }}
			>imprint</a
		>
	</nav>
{/if}
