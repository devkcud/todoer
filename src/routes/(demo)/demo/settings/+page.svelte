<script lang="ts">
    import ArrowLeft from '$lib/icons/ArrowLeft.svelte';
    import Feather from '$lib/icons/Feather.svelte';
    import Pencil from '$lib/icons/Pencil.svelte';

    import '$lib/styles/settings.scss';
</script>

<header>
    <a href="/demo" class="button">
        <ArrowLeft />
        Go back
    </a>
</header>

<section id="settings">
    <div id="profile-pic">
        <img
            src="https://placeholder.co/256"
            alt="Placeholder with the geometry 256x256 to be used in profile in demo (not clickable)"
        />
        <Pencil />
    </div>

    <div id="info">
        <div id="info-email">
            <label for="login-email">Login Email:</label>
            <input name="login-email" type="text" placeholder="email@somewhere.com" />

            <label for="recovery-email">Login Email:</label>
            <input name="recovery-email" type="text" placeholder="email@somewhere.com" />
        </div>

        <div id="info-password">
            <label for="current-password">Current Password:</label>
            <input name="current-password" type="password" placeholder="Current password" />

            <label for="new-password">New Password:</label>
            <input name="new-password" type="password" placeholder="New password" />

            <label for="confirm-new-password">Confirm New Password:</label>
            <input name="confirm-new-password" type="password" placeholder="Confirm new password" />
        </div>
    </div>

    <a class="button" href="/demo">
        <Feather />
        Save
    </a>
</section>
