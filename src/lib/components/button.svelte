<script lang="ts">
        export let active = false
</script>

<span class:bg-black={active} class:text-white={active} class="cursor-pointer border-gray-500 border-solid border-2 rounded-full w-36 px-5 bg-[#f2e4d0] text-center py-3">
        <slot />
</span>