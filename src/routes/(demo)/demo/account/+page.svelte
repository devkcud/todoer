<script>
    import ArrowLeft from '$lib/icons/ArrowLeft.svelte';
    import Eye from '$lib/icons/Eye.svelte';
    import EyeDeny from '$lib/icons/EyeDeny.svelte';

    import '$lib/styles/account.scss';

    function getDate() {
        const currentDate = new Date();
        const month = String(currentDate.getMonth() + 1).padStart(2, '0');
        const day = String(currentDate.getDate()).padStart(2, '0');
        const year = currentDate.getFullYear();

        return `${month}-${day}-${year}`;
    }

    let email = 'email@somewhere.com';

    $: showEmail = false;

    function hideEmail() {
        const parts = email.split('@');
        const username = parts[0];
        const domain = parts[1];

        const hiddenUsername =
            username.charAt(0) +
            '*****' +
            username.charAt(username.length - 1);

        return hiddenUsername + '@' + domain;
    }
</script>

<header>
    <a href="/demo" class="button">
        <ArrowLeft />
        Go back
    </a>
</header>

<section id="account-info">
    <img
        src="https://placehold.co/256"
        alt="Placeholder with the geometry 256x256 to be used in profile in demo (not clickable)"
    />

    <div>
        <h2>Unknown</h2>

        <p><b>Member since:</b> {getDate()}</p>
        <p><b>Last time seen:</b> {getDate()}</p>
        <p><b>Todos:</b> 0 out of 0 completed</p>

        <div id="email-place">
            <p><b>Login Email:</b></p>

            {#if showEmail}
                <span>{email}</span>
                <EyeDeny on:click={() => showEmail = !showEmail} />
            {:else}
                <span>{hideEmail()}</span>
                <Eye on:click={() => showEmail = !showEmail} />
            {/if}
        </div>
    </div>
</section>
