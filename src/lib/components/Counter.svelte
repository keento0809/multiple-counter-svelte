<script lang="ts">
  import type { CounterInfo } from "../../routes/+page.svelte";
  import { ButtonBlock } from "$lib";

  export let counter: CounterInfo;
  export let handleDeleteCounter: (selectedId: string) => void;
</script>

<li class="counter">
  <input type="text" placeholder="new" bind:value={counter.title} />
  <div class="counter-value">
    <span>{counter.currentCount}</span>
  </div>
  <ButtonBlock bind:counter />
  <button class="delete" on:click={() => handleDeleteCounter(counter.id)}
    >&times;</button
  >
</li>

<style>
  .counter {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 2rem;
    padding: 0.5rem 1rem;
    margin-bottom: 1rem;
    border-radius: 8px;
    background-color: rgb(197, 255, 236);
  }
  .counter .counter-value {
    display: block;
    justify-content: center;
    align-items: center;
  }
  .counter input {
    padding: 0.5rem 0rem 0.5rem 1rem;
    outline: none;
    border: 1px solid rgb(168, 163, 163);
    border-radius: 8px;
    min-width: 15rem;
  }
  .counter span {
    display: flex;
    justify-content: center;
    align-items: center;
    min-width: 2rem;
    padding: 0 0.5rem;
  }
  .counter button {
    outline: none;
    padding: 0.4rem 1.5rem;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    transition: all 0.3s;
  }
  .counter button:hover {
    transform: scale(1.1);
  }
  .counter button.delete {
    background-color: rgb(31, 200, 251);
  }
</style>
