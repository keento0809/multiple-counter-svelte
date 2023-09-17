<script lang="ts">
  import type { CounterInfo } from "../../routes/+page.svelte";

    export let totalCount:number;
    export let handleAddNewCounter:() => void;
    export let counters:Array<CounterInfo>
</script>

<section class="dashboard-container">
    <div>
        <button on:click={handleAddNewCounter}>New Counter</button>
    </div>
    <div>
        <p>title list: {#each counters as counter (counter.id)}{counter.title + ' '}{/each}</p>
    </div>
    <div>
        <p>total count: {totalCount}</p>
    </div>
</section>

<style>
    .dashboard-container {
        padding: 2rem 0;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        gap: 0.5rem;
    }
    .dashboard-container p {
        margin: 0;
    }
</style>