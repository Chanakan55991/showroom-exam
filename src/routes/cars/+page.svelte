<script lang="ts">
	import MenuIconButton from '$lib/components/menuiconbutton.svelte';
	import Button from '$lib/components/button.svelte';
	import { Info } from 'lucide-svelte';
	import CarSelector from '$lib/car-selector.svelte';

	let color: string = 'blue';

	const setColor = (setcolor) => {
		color = setcolor;
		console.log(color);
	};
</script>

<div class="pt-8 h-full w-full flex flex-col">
	<div class="flex gap-x-4 items-center">
		<span class="text-4xl font-bold">Mercedes-Benz</span>
		<MenuIconButton><Info /></MenuIconButton>
	</div>
	<span class="text-xl text-gray-500">AMG C63 Coupe - 2023</span>
	<div class="mx-auto mt-4 flex items-center justify-between h-[70%] w-[90%]">
		<div class="flex flex-col gap-y-4">
			<Button>Performance</Button>
			<Button active={true}>Design</Button>
			<Button>Safety</Button>
			<Button>Luxury</Button>
			<Button>Multimedia</Button>
		</div>
		<CarSelector selectedColor={color} />
	</div>
	<div class="flex mt-[-4rem] justify-between">
		<div class="flex items-center gap-4">
			<span class="text-3xl ml-16 font-bold">Featured Highlights</span>
			<MenuIconButton><Info /></MenuIconButton>
		</div>
		<div class="flex items-center justify-center">
			<span class="text-3xl">Colors</span>
			<div class="flex ml-4 items-center justify-center">
				<div
					class:invisible={color != 'grey'}
					class="rounded-full w-9 h-9 flex border-gray-500 border-solid border-2 items-center justify-center"
				>
					<div
						on:click={() => setColor('grey')}
						class="visible cursor-pointer rounded-full bg-gray-400 h-6 w-6"
					/>
				</div>
				<div
					class:invisible={color != 'blue'}
					class="rounded-full w-9 h-9 flex border-gray-500 border-solid border-2 items-center justify-center"
				>
					<div
						on:click={() => setColor('blue')}
						class="visible cursor-pointer rounded-full bg-blue-600 w-6 h-6"
					/>
				</div>
				<div
					class:invisible={color != 'black'}
					class="rounded-full w-9 h-9 flex border-gray-500 border-solid border-2 items-center justify-center"
				>
					<div
						on:click={() => setColor('black')}
						class="visible cursor-pointer rounded-full bg-black h-6 w-6"
					/>
				</div>
			</div>
		</div>
	</div>
	<span class="ml-16 text-2xl">Coming Soon!</span>
</div>
