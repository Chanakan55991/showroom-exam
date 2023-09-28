<script lang="ts">
	import MenuIconButton from '$lib/components/menuiconbutton.svelte';
	import Button from '$lib/components/button.svelte';
	import { Info, Award } from 'lucide-svelte';
	import CarSelector from '$lib/car-selector.svelte';

	let color: 'grey' | 'blue' | 'black' | 'white' = 'blue';
	const setColor = (setcolor) => {
		color = setcolor;
	};
</script>

<div class="pt-8 h-full w-full flex flex-col">
	<div class="flex gap-x-4 items-center">
		<span class="text-4xl font-bold">Mercedes-Benz</span>
		<a href="https://www.mbusa.com/en/vehicles/model/c-class/coupe/c63cs#key-features">
			<MenuIconButton><Info /></MenuIconButton>
		</a>
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

		<div class="flex justify-center">
			<CarSelector selectedColor={color} />
		</div>

		<div class="absolute flex-col items-center flex w-[20rem] mt-[-16rem] right-8">
			<div
				class="bg-black text-white w-full flex items-center justify-center py-6 rounded-xl mb-[-1rem]"
			>
				<div class="rounded-full bg-gray-800 p-3 mr-2">
					<Award size={24} />
				</div>
				<span class="text-xl">Unsurpassed Power</span>
			</div>
			<div
				class="p-4 rounded-xl border-black border-2 border-solid bg-white bg-opacity-50 backdrop-blur-md self-start"
			>
				<span>
					A handcrafted 503-hp biturbo V8 unleashes a 516-lb-ft torrent of torque. Aggressive style
					envelops advanced technologies.
				</span>
			</div>
		</div>
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
				<div
					class:invisible={color != 'white'}
					class="rounded-full w-9 h-9 flex border-gray-500 border-solid border-2 items-center justify-center"
				>
					<div
						on:click={() => setColor('white')}
						class="visible cursor-pointer rounded-full bg-white h-6 w-6"
					/>
				</div>
			</div>
		</div>
	</div>
	<span class="ml-16 text-2xl">Coming Soon!</span>
</div>
