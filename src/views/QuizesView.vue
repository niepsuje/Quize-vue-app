<script setup>
  import q from "../data/quizes.json"
  import {ref, watch} from "vue"
  import Card from "../components/Card.vue"

  const quizes = ref(q)
  const search = ref("")

  watch(search, () => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
  })

</script>

<template>
  <div>
    <header>
      <h1>Quizes</h1>
      <input v-model.trim="search" type="text" placeholder="Search..."/>
    </header>
    <div class="options-container">
      <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
      <!-- <div v-for="quiz in quizes" :key="quiz.id" class="card">
        <img :src="quiz.img" alt="">
        <div class="card-text">
          <h2>{{ quiz.name }}</h2>
          <p>{{ quiz.questions.length }} questions</p>
        </div>
      </div> -->
    </div>
  </div>
</template>

<style scoped>
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

</style>