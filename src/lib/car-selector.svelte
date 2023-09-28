<script lang="ts">
	export let selectedColor: 'grey' | 'blue' | 'black' | 'white' = 'blue';
	import BlueCar from '$lib/amg-blue.png';
	import GreyCar from '$lib/amg-grey.png';
	import BlackCar from '$lib/amg-black.png';
	import WhiteCar from '$lib/amg-white.png';

	const cars = {
		blue: BlueCar,
		grey: GreyCar,
		black: BlackCar,
		white: WhiteCar
	};
</script>

<div class="w-[90%]">
	<img src={cars[selectedColor]} alt={`Car with ${selectedColor} color`} />
</div>
