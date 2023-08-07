<script lang="ts">
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

<style lang="scss">
    article {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        min-height: 100vh;

        form {
            width: 600px;
            height: 400px;

            h1 {
                color: #ffffff;

                font-size: 5rem;
                font-style: normal;
                font-weight: 700;

                margin-bottom: 20px;
            }

            section {
                position: relative;

                width: 100%;

                display: inline-flex;
                gap: 15px;

                border-bottom: 1px solid #ffffff;

                padding: 14px;
                margin-bottom: 24px;

                input {
                    background: none;
                    color: #ffffff;

                    border: none;
                    outline: none;

                    font-size: 1.1rem;
                    width: 100%;
                }

                button {
                    background: none;
                    border: none;

                    &:hover {
                        cursor: pointer;
                    }
                }
            }

            button#continue-button {
                display: flex;
                justify-content: center;
                align-items: center;

                width: 320px;
                height: 50px;

                margin-top: 2rem;

                margin-inline: auto;

                border: none;
                border-radius: 10px;

                background: #2c8d24;
                color: #ffffff;

                font-size: 24px;
                font-style: normal;
                font-weight: 700;

                &:hover {
                    cursor: pointer;
                }
            }
        }

        span {
            position: absolute;
            bottom: 30px;

            a {
                color: #2c8d24;
                font-weight: 700;
            }
        }
    }
</style>
