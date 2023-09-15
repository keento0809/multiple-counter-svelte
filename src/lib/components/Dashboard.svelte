<script lang="ts">
    let titleList:Array<string> = []
    let totalCount = 0
</script>

<section class="dashboard-container">
    <div>
        <button>New Counter</button>
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