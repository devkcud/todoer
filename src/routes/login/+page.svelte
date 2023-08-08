<script lang="ts">
    import '$lib/styles/loginregister.scss';

    import User from '$lib/icons/User.svelte';
    import Eye from '$lib/icons/Eye.svelte';
    import EyeDeny from '$lib/icons/EyeDeny.svelte';
    import Lock from '$lib/icons/Lock.svelte';

    let seePassword = false;
    $: type = seePassword ? 'text' : 'password';
</script>

<article>
    <form>
        <h1>Login</h1>

        <section>
            <User />
            <input type="text" placeholder="Email or Username" id="email-username-input" />
        </section>

        <section>
            <Lock />
            <input {type} placeholder="Password" id="password-input" />

            <button type="button" on:click={() => (seePassword = !seePassword)}>
                {#if !seePassword}<Eye />{:else}<EyeDeny />{/if}
            </button>

            <a href="reset" id="reset-password">reset password</a>
        </section>

        <button type="submit" id="continue-button">Continue</button>
    </form>

    <span>Don't have an account? <a href="register">Register</a></span>
</article>
