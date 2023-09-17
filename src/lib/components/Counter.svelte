<script lang="ts">
    import type { CounterInfo } from "../../routes/+page.svelte";
    export let counter:CounterInfo;
    export let totalCount:number;
    type Action = "INCREMENT" | "DECREMENT" | "RESET"
    const handleChangeCounter:(act:Action) => void = (act) => {
        switch(act) {
            case "INCREMENT": {
                counter.currentCount += 1
                totalCount += 1
                break
            }
            case "DECREMENT": {
                counter.currentCount -= 1
                totalCount -= 1
                break
            }
            case "RESET": {
                counter.currentCount = 0
                break
            }
            default: {
                return
            }
        }
    }
</script>

<li class="counter-container">
    <div>
        <input type="text" placeholder="new" value={counter.title}>
    </div>
    <div class="counter">
        <span>{counter.currentCount}</span>
    </div>
    <div>
        <button class="plus" on:click={() => handleChangeCounter('INCREMENT')}>&plus;</button>
        <button class="minus" on:click={() => handleChangeCounter('DECREMENT')}>&minus;</button>
        <button class="reset" on:click={() => handleChangeCounter('RESET')}>0</button>
    </div>
</li>

<style>
    .counter-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 2rem;
        padding: 0.5rem 0;
    }
    .counter-container .counter {
        display: block;
        justify-content: center;
        align-items: center;
    }
    .counter-container button {
        outline: none;
        padding: 0.4rem 1.5rem;
        border-radius: 8px;
        border: none;
        cursor: pointer;
        transition: all 0.3s;
    }
    .counter-container button:hover {
        transform: scale(1.1);
    }
    .counter-container button.plus {
        background-color: red;
    }
    .counter-container button.minus {
        background-color: blue;
    }
    .counter-container button.reset {
        background-color: yellow;
    }

</style>