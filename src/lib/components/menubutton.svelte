<script lang="ts">
	import { page } from '$app/stores';
	export let path: string;
</script>

<a
	href={path}
	class:text-white={path === $page.url.pathname}
	class="bg-[antiquewhite] border-gray-500 border-solid border-2 rounded-full w-36 bg-[#f2e4d0] text-center py-3"
	class:!bg-black={path === $page.url.pathname}
>
	<span class="text-lg">
		<slot />
	</span>
</a>

