<script>
	import { typewriter } from '$lib/typewriter';
	import { fade } from 'svelte/transition';

	export let text;
</script>

{#key text}
	<h1
		class="text-white drop-shadow-[0px_0px_0.px#fff] duration-500 font-black text-[1.7rem] sm:text-[4rem]"
		in:typewriter={{ speed: 1.2 }}
		out:fade={{ duration: 5 }}
	>
		{text}
	</h1>
{/key}

<style>
	h1 {
		filter: drop-shadow(0px 0px 12px#fff);
	}
</style>
