<script lang="ts">
  import type { CounterInfo } from "../../routes/+page.svelte";
  import Counter from "./Counter.svelte";

  export let counters:Array<CounterInfo>;
  export let totalCount:number;
</script>

<section class="counterlist-container">
    <ul>
        {#each counters as counter (counter.id)}
            <Counter bind:counter={counter} bind:totalCount={totalCount} />
        {/each}
    </ul>
</section>

<style>
    .counterlist-container ul {
        padding: 0;
        margin: 0;
    }
</style>