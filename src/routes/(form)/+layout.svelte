<script lang="ts">
    import '$lib/styles/__global__.scss';

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
