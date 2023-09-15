<script>
    let count = 0
</script>

<section>
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
    section {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 2rem;
    }
    button {
        outline: none;
        padding: 0.4rem 1.5rem;
        border-radius: 8px;
        border: none;
    }
    button.plus {
        background-color: red;
    }
    button.minus {
        background-color: blue;
    }
    button.reset {
        background-color: yellow;
    }
</style>