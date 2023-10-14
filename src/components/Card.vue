<script setup>
    import {defineProps} from "vue"

    const { quiz } = defineProps(['quiz'])

    console.log(quiz)
</script>

<template>
    <div class="card">
        <img :src="quiz.img" alt="">
        <div class="card-text">
            <h2>{{ quiz.name }}</h2>
            <p>{{ quiz.questions.length }} questions</p>
        </div>
    </div>
</template>

<style scoped>
  .card {
    width: 340px;
    overflow: hidden;
    border-radius: 2%;
    box-shadow: 1px 1px 10px rgb(123, 161, 9);
    margin-bottom: 25px;
    margin-right: 25px;
    cursor: pointer;
  }

  .card img {
    width: 100%;
    height: 180px;
    margin: 1px;
  }

  .card .card-text {
    padding: 0 50px;
  }

  .card .card-text h2 {
    font-weight: bold;
    font-family: "Gill Sans", sans-serif;
  }

</style>