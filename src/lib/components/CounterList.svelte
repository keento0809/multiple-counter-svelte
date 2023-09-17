<script lang="ts">
  import type { CounterInfo } from "../../routes/+page.svelte";
  import { Counter } from "$lib";

  export let counters: Array<CounterInfo>;
  export let handleDeleteCounter: (selectedId: string) => void;
</script>

<section class="counterlist-container">
  <ul>
    {#each counters as counter (counter.id)}
      <Counter bind:counter {handleDeleteCounter} />
    {/each}
  </ul>
</section>

<style>
  .counterlist-container ul {
    padding: 0;
    margin: 0;
  }
</style>
