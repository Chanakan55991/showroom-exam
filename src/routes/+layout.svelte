<script lang="ts">
    import Navbar from '$lib/components/navbar.svelte'
    import '../style.pcss'
</script>

<main class="w-[96%] mx-auto flex h-screen">
    <Navbar />
    <div class="pt-24 h-full flex w-screen">
        <slot />
    </div>
</main>