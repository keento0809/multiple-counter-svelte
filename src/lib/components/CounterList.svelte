<script lang="ts">
  import type { CounterInfo } from "../../routes/+page.svelte";
  import Counter from "./Counter.svelte";

  export let counters:Array<CounterInfo>;
  export let totalCount:number;
</script>

<section>
    <ul>
        {#each counters as counter (counter.id)}
            <Counter bind:counter={counter} bind:totalCount={totalCount} />
        {/each}
    </ul>
</section>

<style>

</style>