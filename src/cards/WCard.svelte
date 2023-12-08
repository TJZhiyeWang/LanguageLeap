<script lang="ts">
    export let question = "questions/audios/conversation4.mp4";
    export let correctOption = "answer";
    let showExample = false;
    function showExampleText() {
        showExample = true;
    }
    $: {
        console.log('Input value changed:', question);
        showExample = false;
    }
</script>

<div class="quiz-container">
    <div class="question">
        {question}
    </div>
    <div class="divider"></div>

    <div class="options">
        <textarea></textarea>
        <button class="option-button" on:click={showExampleText}>Check</button>
        {#if showExample}
            <p>{correctOption}</p>
        {/if}
    </div>
</div>

<style>
        .option-button {
        display: inline-block;
        padding: 8px 16px;
        font-size: 14px;
        text-align: center;
        text-decoration: none;
        cursor: pointer;
        border: 2px solid #3498db;
        color: #3498db;
        background-color: #ffffff;
        border-radius: 3px;
        transition:
            background-color 0.3s,
            color 0.3s,
            border-color 0.3s;
    }

    .option-button:hover {
        background-color: #3498db;
        color: #ffffff;
        border-color: #ffffff;
    }
    .quiz-container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: 100%;
    }

    .divider {
        height: 100%;
        border-right: 2px solid #ccc;
        margin: 0 10px;
    }

    .question,
    .options {
        width: 45%;
        font-size: 20px;
        text-align: center;
        color: #3498db;
    }

    .options {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    button {
        margin: 5px;
    }
</style>
