<script lang="ts">
    import '$lib/styles/loginregister.scss';

    import User from '$lib/icons/User.svelte';
    import Lock from '$lib/icons/Lock.svelte';

    let email: string;
    let password: string;
    let error: string = '';

    function handleAuth() {
        if (!email || !password) {
            let missing = [];

            if (!email) missing.push('Email');
            if (!password) missing.push('Password');

            return (error = `Missing fields: ${missing.join(', ')}`);
        }

        error = '';
    }
</script>

<article>
    <form>
        <h1>Login</h1>

        <section>
            <User />
            <input bind:value={email} type="text" placeholder="Email" id="email-username-input" />
        </section>

        <section>
            <Lock />
            <input bind:value={password} placeholder="Password" id="password-input" />

            <a href="reset" id="reset-password">reset password</a>
        </section>

        <button on:click={handleAuth} type="submit" id="continue-button">Continue</button>

        {#if error !== ''}
            <p id="error" style="margin-top: 1rem">{error}</p>
        {/if}
    </form>

    <footer>Don't have an account? <a href="register">Register</a></footer>
</article>
