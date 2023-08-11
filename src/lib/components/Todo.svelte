<script lang="ts">
    import CircleFilled from '$lib/icons/CircleFilled.svelte';
    import CircleOutline from '$lib/icons/CircleOutline.svelte';

    import '$lib/styles/components/todo.scss';

    $: done = false;

    let todoItem: HTMLDivElement;

    function toggleDone() {
        done = !done;
        todoItem.classList.toggle('done');
    }

    export let title: string;
</script>

<div bind:this={todoItem} class="todo-item">
    {#if done}
        <CircleFilled on:click={toggleDone} />
    {:else}
        <CircleOutline on:click={toggleDone} />
    {/if}

    <h2>{title}</h2>
</div>
