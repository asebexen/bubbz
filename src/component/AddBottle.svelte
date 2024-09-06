<script lang="ts">
    import { createEventDispatcher } from "svelte";

    export let data: { dates: Date[] };

    const handleAdd = () => {
        data.dates = data.dates.concat([new Date()]);
    };
</script>

<p class="num-bottles">You have added {data.dates.length} bottles!</p>
<button on:click={handleAdd}>Add Bottle</button>

<style>

</style>