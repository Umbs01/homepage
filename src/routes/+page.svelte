<script>
	import Typed from 'typed.js';
	import { onMount } from 'svelte';

	export let strings = ['send noods'];
	export let typeSpeed = 100;
	export let backSpeed = 75;

	/**
	 * @type {Typed}
	 */
	let typed;

	onMount(() => {
		// Initialize Typed.js after DOM is ready
		typed = new Typed('.auto-type', {
			strings: strings,
			typeSpeed: typeSpeed,
			backSpeed: backSpeed,
			loop: true,
			showCursor: true,
			cursorChar: '█'
		});

		// Cleanup Typed.js on component unmount
		return () => {
			typed.destroy();
		};
	});
</script>

<svelte:head>
	<title>send noods</title>
</svelte:head>

<main>
	<div class="flex h-screen flex-col items-center justify-center space-y-4">
		<h1 class="text-7xl font-bold">
			<div>
				<b>&#36;</b>&#62;
				<p class="auto-type inline align-baseline font-mono leading-none"></p>
			</div>
		</h1>
	</div>
</main>
