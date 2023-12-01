<script lang="ts">
    let question = "What is the capital of France?";
    let options = ["Berlin", "Madrid", "Paris", "Rome"];
    let correctOption = 2;
    let selectedOption: number | null = null;
    let isCorrect = null;

    let optionColor = ["None", "None", "None", "None"]

    // let correctButton: HTMLButtonElement;
    let selectedButton: HTMLButtonElement;

    function checkAnswer() {
        isCorrect = options[selectedOption] === options[correctOption];
        // correctButton.classList.add("correct");
        selectedButton.classList.add("correct")
        console.log(selectedButton.classList)
        if (!isCorrect) {
            selectedButton.classList.add("incorrect");
        }else {
            selectedButton.classList.add("correct");

        }
    }
</script>

<div class="quiz-container">
    <div class="question">{question}</div>
    <div class="divider"></div>

    <div class="options">
        {#each options as option, index}
            <button class:correct={optionColor[index] == "g"} class:incorrect={optionColor[index] == "r"}
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
    .quiz-container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: 100%;
    }

    .divider {
        height: 100%;
        border-right: 2px solid #ccc; /* 分割线样式，可以根据需要调整颜色和宽度 */
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
