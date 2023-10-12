<script setup>
  // import {RouterView} from "vue-router"
  // import QuizesView from "./views/QuizesView.vue"

</script>

<template>
  <div class="container">
    <header>
      <h1>Quizes</h1>
      <input type="text" placeholder="Search..."/>
    </header>
    <div class="options-container">
      <div class="card">
        <img src="https://img.freepik.com/free-vector/counting-number-0-9-math-symbols_1308-104139.jpg?size=626&ext=jpg&ga=GA1.1.1413502914.1696982400&semt=sph" alt="">
        <div class="card-text">
          <h2>Math</h2>
          <p>15 questions</p>
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
    margin-bottom: 300px;
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