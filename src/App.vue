<script setup>
import { ref } from 'vue';
import axios from 'axios';

import ResultContainer from './components/ResultContainer.vue';
import NavBarComponent from '@/components/globals/NavBarComponent.vue'

const search = ref('');
const isLoading = ref(false);
const isData = ref(false);
const isValid = ref(true);
const job = ref({});

const handleSearch = () => {
  const urlApi = "http://localhost:3000/api/scrape";

  const urlRegex = /^https:\/\/www\.linkedin\.com\/jobs\/view\/\d+\/$/

  if (urlRegex.test(search.value)) {
    isValid.value = true
    isLoading.value = true;
    isData.value = false;
    axios.post(urlApi, { search: search.value })
      .then((response) => {
        isLoading.value = false
        search.value = ""
        isData.value = true
        job.value = response.data
      })
      .catch(error => console.log(error))
  } else {
    isValid.value = false
    search.value = "";
  }
}

</script>

<template>
  <NavBarComponent />
  <div class="container align-items-center justify-content-center body">
    <form @submit.prevent="handleSearch">
      <div class="container row align-items-center justify-content-center">
        <div class="col-10">
          <input type="text" class="form-control" v-model="search" placeholder="Saisissez l'url du du job">
        </div>
        <button type="submit" class="btn btn-primary col-2">Collecter</button>
      </div>
    </form>
    <div class="">
      <div v-if="isLoading" class="spinner-border text-primary mt-4" role="status">
        <span class="visually-hidden">Loading...</span>
      </div>
      <ResultContainer v-if="isData" :job="job" />
      <div class="container mt-4" v-if="!isValid">
        <p>Url non valide, utilisez une url sous la forme <strong>https://www.linkedin.com/jobs/view/3709823773/</strong>
        </p>
      </div>

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
  /* margin-top: 60px; */
  background-color: black;
  color: antiquewhite;
  height: 100vh;
}

.body {
  margin-top: 10%;
}
</style>
