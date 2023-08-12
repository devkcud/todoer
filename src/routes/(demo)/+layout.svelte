<script lang="ts">
    import '$lib/styles/demo.scss';
</script>

<main>
    <section id="warning">
        <p><b>ATTENTION:</b> This is just a demo; some features are disabled.</p>
    </section>

    <slot />
</main>

<style>
    section#warning {
        background: #ffbf00;
        color: #000000;
        text-align: center;
    }
</style>
