<script lang="ts">
    import CircleFilled from '$lib/icons/CircleFilled.svelte';
    import CircleOutline from '$lib/icons/CircleOutline.svelte';
    import Cross from '$lib/icons/Cross.svelte';
    import Edit from '$lib/icons/Edit.svelte';

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
    <div style="display: flex; gap: 1rem;">
        {#if done}
            <CircleFilled on:click={toggleDone} />
        {:else}
            <CircleOutline on:click={toggleDone} />
        {/if}
        <h2>{title}</h2>
    </div>

    <Cross on:click={() => todoItem.remove()} />
</div>
