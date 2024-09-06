<script lang="ts">
    import { createEventDispatcher } from "svelte";

    export let date: Date;

    const dispatcher = createEventDispatcher<{
        delete: void;
    }>();
</script>

<div class="bottle">
    <p>{date.toLocaleString('en-us')}</p>
    <button on:click={() => dispatcher("delete")}>Delete</button>
</div>

<style>
    .bottle {
        display: flex;
        gap: 1rem;
    }
</style>