<script lang="ts">
  import type { CounterInfo } from "../../routes/+page.svelte";
  import Counter from "./Counter.svelte";

  export let counters:Array<CounterInfo>
</script>

<section>
    <ul>
        {#each counters  as counter (counter.id)}
            <Counter counter={counter} />
        {/each}
    </ul>
</section>

<style>

</style>