<script lang="ts">
  import type { CounterInfo } from "../../routes/+page.svelte";

  export let counter: CounterInfo;

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

<section class="buttonBlock-container">
  <button class="plus" on:click={() => handleChangeCounter("INCREMENT")}
    >&plus;</button
  >
  <button class="minus" on:click={() => handleChangeCounter("DECREMENT")}
    >&minus;</button
  >
  <button class="reset" on:click={() => handleChangeCounter("RESET")}>0</button>
</section>

<style>
  .buttonBlock-container button {
    outline: none;
    padding: 0.4rem 1.5rem;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    transition: all 0.3s;
  }
  .buttonBlock-container button:hover {
    transform: scale(1.1);
  }
  .buttonBlock-container button.plus {
    background-color: rgb(242, 36, 36);
  }
  .buttonBlock-container button.minus {
    background-color: rgb(90, 90, 203);
  }
  .buttonBlock-container button.reset {
    background-color: rgb(249, 249, 31);
  }
</style>
