<script setup>
const { question, defineEmits } = defineProps({
    question: Object,
    defineEmits: Object
});

const emit = defineEmits(["selectOption"])

const emitSelectedOption = (isCorrect) => {
    emit("selectOption", isCorrect)
}

</script>

<template>
    <div class="question-container">
        <h1 class="question">
            {{question.text}}
        </h1>
    </div>
    <div class="options-container">
        <div 
            v-for="option in question.options" 
            :key="option.id" 
            class="option"
            @click="emitSelectedOption(option.isCorrect)"
        >
            <p class="option-label">{{option.label}}</p>
            <div class="option-value">
                <p>{{option.text}}</p>
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