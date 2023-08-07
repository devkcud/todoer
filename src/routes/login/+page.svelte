<script lang="ts">
    import User from '$lib/icons/User.svelte';
    import Eye from '$lib/icons/Eye.svelte';
    import EyeDeny from '$lib/icons/EyeDeny.svelte';
    import Lock from '$lib/icons/Lock.svelte';

    import '$lib/styles/loginregister.scss';

    let seePassword = false;
    $: type = seePassword ? 'text' : 'password';
</script>

<article>
    <form>
        <h1>Login</h1>

        <section>
            <User />
            <input type="text" placeholder="Email or Username" />
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

            a#reset-password {
                position: absolute;
                bottom: -1.5rem;
                left: 0;
                color: #868686;
                font-size: 14px;
                font-style: normal;
                font-weight: 400;
                line-height: normal;
                text-decoration-line: underline;
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
