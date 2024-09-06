<script lang="ts">
    import Bottle from "./Bottle.svelte";

    export let data: { dates: Date[] };

    let dates = data.dates;

    const handleDelete = (date: Date) => {
        dates = dates.filter((d: Date) => d !== date);
    };
</script>

<div class="bottle-list">
    {#each dates as date}
        <Bottle {date} on:delete={() => handleDelete(date)} />
    {/each}
</div>

<style>
    .bottle-list {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
</style>