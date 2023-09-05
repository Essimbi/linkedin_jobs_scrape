<script setup>
import { ref } from 'vue';
import axios from 'axios';

import ResultContainer from './components/ResultContainer.vue' ;

const search = ref('');
const isLoading = ref(false) ;
const isData = ref(false) ;
const job = ref({}) ;

const handleSearch = () => {
  const url = "http://localhost:3000/api/scrape";
  isLoading.value = true ;
  axios.post(url, { search: search.value })
    .then((response) => {
      isLoading.value = false
      search.value = "";
      isData.value = true
      job.value = response.data ;
    })
    .catch(error => console.log(error));
}

</script>

<template>
  <div class="container align-items-center justify-content-center body">
    <form @submit.prevent="handleSearch">
      <div class="container row align-items-center justify-content-center">
        <div class="col-10">
          <input type="text" class="form-control" v-model="search">
        </div>
        <button type="submit" class="btn btn-primary col-2">Collecter</button>
      </div>
    </form>
    <div class="">
      <div v-if="isLoading" class="spinner-border text-primary mt-4" role="status">
        <span class="visually-hidden">Loading...</span>
      </div>
      <ResultContainer v-if="isData" :job="job"/>

    </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.body {
  margin-top: 20%;
}
</style>
