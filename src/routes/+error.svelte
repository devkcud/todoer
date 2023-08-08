<script>
    import '$lib/styles/errorpage.scss';

    import { page } from '$app/stores';
</script>

<article>
    <section>
        <p>Oh no!</p>
        <h1>A wild <span id="page-status">{$page.status}</span> has appeared!</h1>
        <p><span>At least we got it:</span> {$page.error?.message}</p>
    </section>
</article>
