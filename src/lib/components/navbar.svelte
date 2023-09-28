<script lang="ts">
	import MenuButton from '$lib/components/menubutton.svelte';
	import MenuIconButton from '$lib/components/menuiconbutton.svelte';
	import { MessageCircle, Menu } from 'lucide-svelte';
</script>

<div class="mix-blend-difference fixed w-[96%] z-[1000]">
	<div class="w-full">
		<nav class="p-4 pt-8 flex justify-between items-center">
			<div class="flex items-center gap-x-2">
				<span class="text-3xl text-white font-bold">Car.</span>
				<div class="flex flex-col text-white font-xl leading-none font-medium">
					<span>Car Sell</span>
					<span>Center</span>
				</div>
			</div>
			<div class="flex gap-1">
				<MenuButton path="/">Home</MenuButton>
				<MenuButton path="/cars">Cars</MenuButton>
				<MenuButton path="/about-us">About Us</MenuButton>
				<MenuButton path="mailto:chanakan5591@chanakancloud.net">Contact Us</MenuButton>
				<MenuButton path="login">Login</MenuButton>
				<div class="ml-2" />
				<MenuIconButton><MessageCircle /></MenuIconButton>
				<MenuIconButton><Menu /></MenuIconButton>
			</div>
		</nav>
	</div>
</div>
