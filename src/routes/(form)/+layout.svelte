<script lang="ts">
    import GitHub from '$lib/icons/GitHub.svelte';
</script>

<header>
    <a href="demo">Click to see demo</a>
    <a href="https://github.com/devkcud/todoer">
        <GitHub />
    </a>
</header>

<main>
    <slot />
</main>

<style>
    header {
        position: absolute;

        display: flex;
        justify-content: space-between;
    }
</style>
