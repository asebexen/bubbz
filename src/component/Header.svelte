<script lang="ts">
    import { createEventDispatcher } from "svelte";
    import { AppView } from "../types";

    const dispatcher = createEventDispatcher<{changeview: AppView}>();
</script>

<header>
    <h1>Bubbz</h1>
    <button class='header-item' on:click={() => dispatcher("changeview", AppView.Add)}>Add</button>
    <button class='header-item' on:click={() => dispatcher("changeview", AppView.List)}>View</button>
</header>

<style>
    header {
        display: flex;
        gap: 1rem;
    }
</style>