<script lang="ts">
	export let menuOpen = false;
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

<nav class={`absolute z-20 inset-0 mt-20 ml-8 ${menuOpen ? 'block' : 'hidden'}`}>
	<ul>
		<li>
			<a href="/" class="text-white font-black text-5xl">home</a>
		</li>
		<li>
			<a href="/" class="text-white font-black text-5xl">work</a>
		</li>
		<li>
			<a href="/" class="text-white font-black text-5xl">get in touch</a>
		</li>
	</ul>
</nav>
