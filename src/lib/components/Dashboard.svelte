<script lang="ts">
    export let totalCount:number;
    export let handleAddNewCounter:() => void;
    export let titleList:Array<string>
</script>

<section class="dashboard-container">
    <div>
        <button on:click={handleAddNewCounter}>New Counter</button>
    </div>
    <div>
        <p>title list: {titleList}</p>
    </div>
    <div>
        <p>total count: {totalCount}</p>
    </div>
</section>

<style>
    .dashboard-container {
        padding: 4rem 0;
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