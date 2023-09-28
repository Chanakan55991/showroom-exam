<script lang="ts">
	import toast from 'svelte-french-toast';
</script>

<div class="flex h-full w-full items-center justify-center">
	<div class="w-64 flex flex-col">
		<span class="text-4xl mb-4">Login</span>
		<label for="username">Username</label>
		<input
			type="text"
			class="p-2 border-black border-2 border-solid rounded-full"
			name="username"
		/>
		<label for="password" class="mt-2">Password</label>
		<input
			type="password"
			class="p-2 border-black border-2 border-solid rounded-full"
			name="password"
		/>

		<button
			on:click={() => toast.error('Coming Soon!')}
			type="submit"
			class="mt-4 border-black border-2 border-solid p-2 px-4 w-full rounded-full">Login</button
		>
	</div>
</div>
