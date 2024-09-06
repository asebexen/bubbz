<script lang="ts">
    import Header from "./component/Header.svelte";
    import BottleList from "./component/BottleList.svelte";
    import AddBottle from "./component/AddBottle.svelte";
    import{ type Data, AppView } from "./types";

    let data: Data = {
        dates: [
        new Date("2024-01-15"),
        new Date("2024-02-29"),
        new Date("2024-03-10")
    ]};

    const viewComponents = {
        [AppView.List]: BottleList,
        [AppView.Add]: AddBottle
    };

    let view = AppView.Add;
    $: ViewComponent = viewComponents[view];

    const handleChangeView = (e: CustomEvent<AppView>) => {
        view = e.detail;
    };
</script>

<main>
    <Header on:changeview={handleChangeView} />
    <svelte:component this={ViewComponent} bind:data />
</main>

<style>
</style>
