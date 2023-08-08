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
        <h1>Register</h1>

        <section>
            <User />
            <input type="text" placeholder="Email" id="email-input" />
        </section>

        <section>
            <Lock />
            <input {type} placeholder="Password" id="password-input" />

            <button type="button" on:click={() => (seePassword = !seePassword)}>
                {#if !seePassword}<Eye />{:else}<EyeDeny />{/if}
            </button>
        </section>

        <section>
            <Lock />
            <input type="password" placeholder="Confirm Password" id="confirm-password-input" />
        </section>

        <button type="submit" id="continue-button">Continue</button>
    </form>

    <span>Already have an account? <a href="login">Login</a></span>
</article>
