<script lang="ts">
    import GitHub from '$lib/icons/GitHub.svelte';
</script>

<header>
    <a href="/demo">Click to see demo</a>
    <a href="https://github.com/devkcud/todoer">
        <GitHub />
    </a>
</header>

<main>
    <slot />
</main>

<style lang="scss">
    header {
        width: 100%;

        position: absolute;

        display: flex;
        justify-content: space-between;

        padding: 16px;

        a {
            color: #868686;
            font-family: Inter;
            font-size: 18px;
            font-style: normal;
            font-weight: 400;
            line-height: normal;
            text-decoration-line: underline;
        }
    }

    main {
        min-height: 100vh;

        background: linear-gradient(135deg, #04060c 0%, #0f1421 100%);
        color: #ffffff;
    }
</style>
