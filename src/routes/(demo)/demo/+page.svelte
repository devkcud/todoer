<script lang="ts">
    import Todo from '$lib/components/Todo.svelte';
    import Add from '$lib/icons/Add.svelte';
    import Door from '$lib/icons/Door.svelte';
    import Gear from '$lib/icons/Gear.svelte';
    import UserRounded from '$lib/icons/UserRounded.svelte';

    $: todos = [] as string[];
    let todoTitle: string;

    function addTodo() {
        if (todoTitle === undefined || todoTitle === '') return;
        todos = [...todos, todoTitle];
        todoTitle = '';
    }
</script>

<header>
    <img
        src="https://placehold.co/100"
        alt="Placeholder with the geometry 100x100 to be used in profile in demo (not clickable)"
    />

    <section>
        <h2>Welcome back, <span class="bold-green">Unknown</span></h2>

        <nav>
            <a class="button" href="/demo/account">
                <UserRounded />
                Account
            </a>
            <a class="button" href="/demo/settings">
                <Gear />
                Settings
            </a>
            <a class="button logout" href="/">
                <Door />
                Logout
            </a>
        </nav>
    </section>
</header>

<section id="body">
    <h1>Todos</h1>

    <div id="create-todo">
        <input bind:value={todoTitle} type="text" placeholder="What to be done?" />
        <Add on:click={() => addTodo()} />
    </div>

    <ul id="todos">
        {#each todos as todo}
            <Todo title={todo} />
        {/each}
    </ul>
</section>
