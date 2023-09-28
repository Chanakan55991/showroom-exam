<script lang="ts">
	export let selectedColor: 'silver' | 'blue' | 'black' | 'white' = 'blue';
	import BlueCar from '$lib/amg-blue.png';
	import SilverCar from '$lib/amg-silver.png';
	import BlackCar from '$lib/amg-black.png';
	import WhiteCar from '$lib/amg-white.png';

	const cars = {
		blue: BlueCar,
		silver: SilverCar,
		black: BlackCar,
		white: WhiteCar
	};
</script>

<div class="md:w-[90%] w-full">
	<img src={cars[selectedColor]} alt={`Car with ${selectedColor} color`} />
</div>
