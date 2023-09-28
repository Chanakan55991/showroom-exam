<script lang="ts">
    import { page } from '$app/stores'
    export let path: string
</script>

<a href={path} class:bg-black={path === $page.url.pathname} class:text-white={path === $page.url.pathname} class="border-gray-500 border-solid border-2 rounded-full w-36 bg-[#f2e4d0] text-center py-3">
    <span class="text-lg">
        <slot />
    </span>
</a>