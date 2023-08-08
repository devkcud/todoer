<script lang="ts">
    import '$lib/styles/loginregister.scss';

    import User from '$lib/icons/User.svelte';
    import Lock from '$lib/icons/Lock.svelte';

    let email: string;
    let password: string;
    let confirmPassword: string;
    let error: string = '';

    function handleAuth() {
        if (!email || !password || !confirmPassword) {
            let missing = [];

            if (!email) missing.push('Email');
            if (!password) missing.push('Password');
            if (!confirmPassword) missing.push('Confirm Password');

            return (error = `Missing fields: ${missing.join(', ')}`);
        }

        error = '';
    }
</script>

<article>
    <form>
        <h1>Register</h1>

        <section>
            <User />
            <input bind:value={email} type="text" placeholder="Email" id="email-input" />
        </section>

        <section>
            <Lock />
            <input bind:value={password} placeholder="Password" id="password-input" />
        </section>

        <section>
            <Lock />
            <input
                bind:value={confirmPassword}
                type="password"
                placeholder="Confirm Password"
                id="confirm-password-input"
            />
        </section>

        <button on:click={handleAuth} type="submit" id="continue-button">Continue</button>

        {#if error !== ''}
            <p id="error" style="margin-top: 1rem">{error}</p>
        {/if}
    </form>

    <footer>Already have an account? <a href="login">Login</a></footer>
</article>
