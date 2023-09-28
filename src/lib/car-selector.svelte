<script lang="ts">
	export let selectedColor: 'grey' | 'red' | 'blue' | 'black' = 'blue';
	import BlueCar from '$lib/amg-blue.png';
	import GreyCar from '$lib/amg-grey.png';
	import BlackCar from '$lib/amg-black.png';

	const cars = {
		blue: BlueCar,
		grey: GreyCar,
		black: BlackCar
	};
</script>

<div class="w-[70%]">
	<img src={cars[selectedColor]} alt={`Car with ${selectedColor} color`} />
</div>
