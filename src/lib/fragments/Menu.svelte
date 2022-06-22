<script lang="ts">
	export let menuOpen = false;

	import { fade } from 'svelte/transition';
</script>

<div class="relative w-16 h-4">
	<button
		class={`absolute z-30 flex items-center justify-between inset-0 font-bold transition-colors duration-300 ${
			menuOpen ? 'text-white' : 'text-black'
		}`}
		on:click={() => (menuOpen = !menuOpen)}
	>
		<span>menu</span>
		<div
			class={`rounded-full block w-4 h-4 z-30 transition-colors duration-300 ${
				menuOpen ? 'bg-white' : 'bg-black'
			}`}
		/>
	</button>
	<div
		class={`absolute top-0 right-0 rounded-full bg-black z-10 w-4 h-4 transition-transform ease-in duration-500 ${
			menuOpen ? 'scale-[400]' : ''
		}`}
	/>
</div>

{#if menuOpen}
	<nav class={`absolute z-20 inset-0 flex justify-center`}>
		<div class="flex flex-col w-[1536px] mx-4 mt-32 ml-10">
			<ul>
				<li class="my-4">
					<a
						href="/"
						class="text-white font-black text-5xl md:text-7xl lg:text-8xl"
						in:fade={{ duration: 300 }}
						out:fade={{ duration: 300, delay: 200 }}>home</a
					>
				</li>
				<li class="my-4">
					<a
						href="/"
						class="text-white font-black text-5xl md:text-7xl lg:text-8xl"
						in:fade={{ duration: 300, delay: 100 }}
						out:fade={{ duration: 300, delay: 100 }}>work</a
					>
				</li>
				<li class="my-4">
					<a
						href="/"
						class="text-white font-black text-5xl md:text-7xl lg:text-8xl"
						in:fade={{ duration: 300, delay: 200 }}
						out:fade={{ duration: 300 }}>get in touch</a
					>
				</li>
			</ul>
			<a href="/" class="text-white mt-auto mb-8 text-lg" transition:fade={{ duration: 300 }}
				>imprint</a
			>
		</div>
	</nav>
{/if}
