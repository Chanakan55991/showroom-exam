<script lang="ts">
	import Navbar from '$lib/components/navbar.svelte';
	import '../style.pcss';
	import { Toaster } from 'svelte-french-toast';
</script>

<main class="w-[96%] mx-auto flex h-screen">
	<Toaster />
	<Navbar />
	<div class="pt-24 h-full flex w-screen">
		<slot />
	</div>
</main>

