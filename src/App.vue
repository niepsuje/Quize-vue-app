<script setup>
  import q from "./data/quizes.json"
  import {ref, watch} from "vue"

  const quizes = ref(q)
  const search = ref("")

  watch(search, () => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
  })

</script>

<template>
  <div class="container">
    <header>
      <h1>Quizes</h1>
      <input v-model.trim="search" type="text" placeholder="Search..."/>
    </header>
    <div class="options-container">
      <div v-for="quiz in quizes" :key="quiz.id" class="card">
        <img :src="quiz.img" alt="">
        <div class="card-text">
          <h2>{{ quiz.name }}</h2>
          <p>{{ quiz.questions.length }} questions</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .container {
    max-width: 1000px;
    margin: 0 auto
  }

  .header {
    margin-bottom: 10px;
    margin-top: 25px;
    display: flex;
    align-items:center
  }

  header h1 {
    font-weight: bold;
    margin-right: 30px;
  }

  header input {
    border: 4mm ridge rgba(211, 220, 50, .6);
    background-color: rgb(130, 130, 140, 0.2);
    padding: 8px;
    border-radius: 8px;
  }

  .options-container {
    display: flex;
    flex-wrap: wrap;
    margin-top: 20px;
  }

  /* CARD */

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