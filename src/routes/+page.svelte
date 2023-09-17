<script context="module" lang="ts">
    export type CounterInfo = {
        id:number;
        title: string;
        currentCount: number;
    };
</script>

<script lang="ts">
    import CounterList from '$lib/components/CounterList.svelte';
    import Dashboard from '$lib/components/Dashboard.svelte';

    let counters:Array<CounterInfo> = [{
        id:1,
        title:'default',
        currentCount:0
    }]
    let titleList:Array<string> = counters.map((c) => c.title)
    let totalCount = 0;

    const handleAddNewCounter:() => void = () => {
        counters = [...counters,{
            id: counters.length + 1,
            title: 'default',
            currentCount: 0
        }]
        titleList = [...titleList,' default']
    }
</script>

<section class="root">
    <h1>Multiple Counter</h1>
    <CounterList bind:counters={counters} bind:totalCount={totalCount} />
    <Dashboard bind:totalCount={totalCount} handleAddNewCounter={handleAddNewCounter} titleList={titleList} />
</section>

<style>
    .root {
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
    }
</style>
