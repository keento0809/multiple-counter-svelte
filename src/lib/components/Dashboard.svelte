<script lang="ts">
    import type { CounterInfo } from "../../routes/+page.svelte";
    export let handleAddNewCounter:() => void;
    export let counters:Array<CounterInfo>
</script>

<section class="dashboard-container">
    <div>
        <button on:click={handleAddNewCounter}>New Counter</button>
    </div>
    <div class="dashboard-content">
        <p><span class="dashboard-content-title">title list:</span> {#each counters as counter (counter.id)}<span class="dashboard-content-titleName">{counter.title + ' '}</span>{/each}</p>
    </div>
    <div class="dashboard-content">
        <p><span class="dashboard-content-title">total count:</span> {counters.reduce((total,curr) => {
            return total + curr.currentCount
        },0)}</p>
    </div>
</section>

<style>
    .dashboard-container {
        padding: 2rem 0;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        gap: 2rem;
    }
    .dashboard-container p {
        margin: 0;
        padding-bottom: 0.5rem;
        border-bottom: 1px solid black;
    }
    .dashboard-container button {
        outline: none;
        border: none;
        border-radius: 8px;
        padding: 0.6rem 2rem;
        cursor: pointer;
        color: white;
        background-color: rgb(175, 54, 188);
        transition: all 0.3s;
    }
    .dashboard-container button:hover {
        transform: scale(1.1);
    }
    .dashboard-content-title {
        font-weight: bold;
    }
    .dashboard-content-titleName {
        display: inline-block;
        border-radius: 8px;
        background-color: rgb(255, 201, 165);
        padding: 0.2rem 0.8rem;
        margin: 0 0.2rem;
    }
</style>