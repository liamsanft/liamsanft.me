<script lang="ts">
	import { Header } from '$lib/fragments';
	import '../app.css';
</script>

<div class="w-full h-full flex flex-col items-center">
	<Header />
	<div class="max-w-[1536px] w-full px-3 h-full">
		<slot />
	</div>
</div>
