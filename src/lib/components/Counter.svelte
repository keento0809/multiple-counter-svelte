<script lang="ts">
  import type { CounterInfo } from "../../routes/+page.svelte";

  export let counter: CounterInfo;
  export let handleDeleteCounter: (selectedId: string) => void;

  type Action = "INCREMENT" | "DECREMENT" | "RESET";

  const handleChangeCounter: (act: Action) => void = (act) => {
    switch (act) {
      case "INCREMENT": {
        counter.currentCount += 1;
        break;
      }
      case "DECREMENT": {
        counter.currentCount -= 1;
        break;
      }
      case "RESET": {
        counter.currentCount = 0;
        break;
      }
      default: {
        return;
      }
    }
  };
</script>

<li class="counter">
  <div>
    <input type="text" placeholder="new" bind:value={counter.title} />
  </div>
  <div class="counter-value">
    <span>{counter.currentCount}</span>
  </div>
  <div>
    <button class="plus" on:click={() => handleChangeCounter("INCREMENT")}
      >&plus;</button
    >
    <button class="minus" on:click={() => handleChangeCounter("DECREMENT")}
      >&minus;</button
    >
    <button class="reset" on:click={() => handleChangeCounter("RESET")}
      >0</button
    >
  </div>
  <div>
    <button class="delete" on:click={() => handleDeleteCounter(counter.id)}
      >&times;</button
    >
  </div>
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
  .counter button.plus {
    background-color: rgb(242, 36, 36);
  }
  .counter button.minus {
    background-color: rgb(90, 90, 203);
  }
  .counter button.reset {
    background-color: rgb(249, 249, 31);
  }
  .counter button.delete {
    background-color: rgb(31, 200, 251);
  }
</style>
