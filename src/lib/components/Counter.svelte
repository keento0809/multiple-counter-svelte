<script>
    let count = 0
</script>

<section class="counter-container">
    <div>
        <input type="text" placeholder="test">
    </div>
    <div>
        <span>{count}</span>
    </div>
    <div>
        <button class="plus">&plus;</button>
        <button class="minus">&minus;</button>
        <button class="reset">0</button>
    </div>
</section>

<style>
    .counter-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 2rem;
    }
    .counter-container button {
        outline: none;
        padding: 0.4rem 1.5rem;
        border-radius: 8px;
        border: none;
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