<template>
    <div class="question-container">
        <h1 class="question">
            What is the chemicalvalue of table salt?
        </h1>
    </div>
    <div class="option-container">
        <div class="option">
            <p class="option-label">A</p>
            <div class="option-value">
                <p>NaCl</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .question-container {
        margin-top: 20px;
    }
    .question {
        font-size: 35px;
        margin-bottom: 17px;
    }
    .option {
        display: flex;
        margin-bottom: 20px;
        cursor: pointer;
    }
    .option-label {
        background-color: rgb(155, 118, 73);
        width: 40px;
        height: 40px;
        font-size: 25px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .option-value {
        background-color: rgb(142, 172, 165);
        width: 100%;
        font-size: 17px;
        padding: 0 15px;
    }
</style>