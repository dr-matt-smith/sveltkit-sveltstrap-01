<script>
	import { Styles } from '@sveltestrap/sveltestrap';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<Styles />
</svelte:head>


{@render children()}
