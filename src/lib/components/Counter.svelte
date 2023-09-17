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
                totalCount -= counter.currentCount
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
        <input type="text" placeholder="new" bind:value={counter.title}>
    </div>
    <div class="counter">
        <span>{counter.currentCount}</span>
    </div>
    <div>
        <button class="plus" on:click={() => handleChangeCounter('INCREMENT')}>&plus;</button>
        <button class="minus" on:click={() => handleChangeCounter('DECREMENT')}>&minus;</button>
        <button class="reset" on:click={() => handleChangeCounter('RESET')}>0</button>
    </div>
    <div>
        <span>&times;</span>
    </div>
</li>

<style>
    .counter-container {
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
    .counter-container .counter {
        display: block;
        justify-content: center;
        align-items: center;
    }
    .counter-container input {
        padding:0.5rem 0rem 0.5rem 1rem;
        outline: none;
        border: 1px solid rgb(168, 163, 163);
        border-radius: 8px;
        min-width: 14rem;
    }
    .counter-container span {
        display: flex;
        justify-content: center;
        align-items: center;
        min-width: 1rem;
        padding: 0 0.5rem;
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
        background-color: rgb(242, 36, 36);
    }
    .counter-container button.minus {
        background-color: rgb(90, 90, 203);
    }
    .counter-container button.reset {
        background-color: rgb(249, 249, 31);
    }

</style>