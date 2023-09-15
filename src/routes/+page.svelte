<script>
    import Counter from '../lib/components/Counter.svelte'
</script>

<section class="root">
    <h1>Multiple Counter</h1>
    <Counter />
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
