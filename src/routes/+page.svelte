<script context="module" lang="ts">
  export type CounterInfo = {
    id: string;
    title: string;
    currentCount: number;
  };
</script>

<script lang="ts">
  import { CounterList, Dashboard } from "$lib";
  import { v4 as uuid } from "uuid";

  const commonInitialCounterValues: Omit<CounterInfo, "id"> = {
    title: "new",
    currentCount: 0,
  };
  let counters: Array<CounterInfo> = [
    {
      id: uuid(),
      ...commonInitialCounterValues,
    },
  ];
  const handleAddNewCounter: () => void = () => {
    counters = [
      ...counters,
      {
        id: uuid(),
        ...commonInitialCounterValues,
      },
    ];
  };
  const handleDeleteCounter: (selectedId: string) => void = (selectedId) => {
    counters = counters.filter((c) => c.id !== selectedId);
  };
</script>

<section class="root">
  <h1>Multiple Counter</h1>
  <CounterList bind:counters {handleDeleteCounter} />
  <Dashboard bind:counters {handleAddNewCounter} />
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
