<script lang="ts">
    export let question;
    export let options;
    export let correctOption = 0;
    let selectedOption: number | null = null;
    let isCorrect = null;
    let optionColor = ["n", "n", "n", "n"];
    $: {
        console.log("Input value changed:", question);
        optionColor = ["n", "n", "n", "n"];
        let tmp = document.getElementById("audio");
        if (tmp != null)
            tmp.load();
    }

    function checkAnswer() {
        isCorrect = options[selectedOption] === options[correctOption];
        optionColor[correctOption] = "g";
        if (!isCorrect) {
            optionColor[selectedOption] = "r";
        }
    }
</script>

<div class="quiz-container">
    <div class="question">
        <audio id="audio" controls>
            <source src={question} type="audio/mp4" />
            Your browser does not support the audio tag.
        </audio>
    </div>
    <div class="divider"></div>

    <div class="options">
        {#each options as option, index}
            <button
                class="option-button"
                class:correct={optionColor[index] == "g"}
                class:incorrect={optionColor[index] == "r"}
                on:click={() => {
                    selectedOption = index;
                    checkAnswer();
                }}
            >
                {option}
            </button>
        {/each}
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
    }

    .options {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    button {
        margin: 5px;
    }

    .correct {
        border: 2px solid green;
    }

    .incorrect {
        border: 2px solid red;
    }
</style>
