<script>
    // @ts-nocheck

    import RCard from "./cards/RCard.svelte";

    export let current;
    let mode = "L";
    function goBack() {
        current = "home";
    }

    function handleButtonClick(action) {
        mode = action;
    }
</script>

<main>
    <header>
        <button on:click={goBack}>&lt; Back</button>
        <div class="button-container">
            <button on:click={() => handleButtonClick("L")}>Listening</button>
            <button on:click={() => handleButtonClick("S")}>Speaking</button>
            <button on:click={() => handleButtonClick("R")}>Reading</button>
            <button on:click={() => handleButtonClick("W")}>Writing</button>
        </div>
    </header>

    <div class="card">
        {#if mode == "R"}
            <RCard></RCard>
        {/if}
    </div>
</main>

<style>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem;
        background-color: #f0f0f0;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        width: 100%;
    }

    .button-container {
        display: flex;
        margin-left: auto;
    }

    .button-container button {
        margin: 0 0.5rem;
    }

    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 1rem;
        width: 100%;
        box-sizing: border-box; /* 保证宽度包括 padding 和 border */
    }

    .card {
        flex: 7;
        border: 1px solid #ccc;
        border-radius: 8px;
        margin: 1rem;
        width: 80%;
        text-align: center;
    }
</style>
