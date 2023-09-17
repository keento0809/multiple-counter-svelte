<script>
    import Counter from '$lib/components/Counter.svelte'
    import Dashboard from '$lib/components/Dashboard.svelte';
</script>

<script context="module" lang="ts">
    export type CounterInfo = {
        id:number;
        title: string;
        currentCount: number;
    };
    type NewCounterInfo = Omit<CounterInfo,'id'>
    export let counters:Array<CounterInfo> = [{
        id:1,
        title:'default',
        currentCount:0
    }]
    let titleList:Array<string> = []
    let totalCount = 0;

    const handleAddNewCounter:() => void = () => {
        counters = [...counters,{
            id: counters.length + 1,
            title: '',
            currentCount: 0
        }]
    }
</script>

<section class="root">
    <h1>Multiple Counter</h1>
    <Counter />
    <Dashboard totalCount={totalCount} handleAddNewCounter={handleAddNewCounter} titleList={titleList} />
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
