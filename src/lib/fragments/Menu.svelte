<script lang="ts">
	export let menuOpen = false;

	import { fade } from 'svelte/transition';
</script>

<div class="relative w-16 h-8">
	<button
		class={`absolute z-30 flex items-center justify-between inset-0 font-bold transition-colors duration-300 ${
			menuOpen ? 'text-white' : 'text-black'
		}`}
		on:click={() => (menuOpen = !menuOpen)}
		aria-label="open the menu"
	>
		<span>menu</span>
		<div
			class={`rounded-full block w-4 h-4 z-30 transition-colors duration-300 ${
				menuOpen ? 'bg-white' : 'bg-black'
			}`}
			aria-hidden="true"
		/>
	</button>
	<div
		class={`absolute top-0 right-0 bottom-0 m-auto rounded-full bg-black z-10 w-4 h-4 transition-transform ease-in duration-500 ${
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
						class="font-black text-5xl md:text-7xl lg:text-8xl hover-gradient"
						in:fade={{ duration: 300 }}
						out:fade={{ duration: 300, delay: 200 }}>home</a
					>
				</li>
				<li class="my-4">
					<a
						href="/"
						class="text-white font-black text-5xl md:text-7xl lg:text-8xl hover-gradient"
						in:fade={{ duration: 300, delay: 100 }}
						out:fade={{ duration: 300, delay: 100 }}>work</a
					>
				</li>
				<li class="my-4">
					<a
						href="/"
						class="text-white font-black text-5xl md:text-7xl lg:text-8xl hover-gradient"
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

<style>
	.hover-gradient {
		background-color: #ffffff;
		background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	.hover-gradient:hover {
		background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
		background-size: 400% 400%;
		animation: gradient 5s ease infinite;
		background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	@keyframes gradient {
		0% {
			background-position: 0% 50%;
		}
		50% {
			background-position: 100% 50%;
		}
		100% {
			background-position: 0% 50%;
		}
	}
</style>
