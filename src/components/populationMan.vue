<script setup>

import {onMounted, ref} from 'vue';
import axios from 'axios';

let worldData = ref([]);

const getPopulation = async () => {
  await axios.get("https://countriesnow.space/api/v0.1/countries/population")
      .then( req => req.data.data.forEach( d => worldData.value.push(d)))
}

onMounted( () => {
  getPopulation();
})
</script>

<template>
  <div class="country-container">
    <div v-for="item in worldData" :key="item.code" class="item-popul">

      <div class="country-info">
        <p>Pais: {{item.country}}</p>
        <p>Codigo: {{item.code}}</p>
      </div>


    </div>
  </div>
</template>

<style scoped>
.country-container{
  display: flex;
  flex-direction: row;
  gap: 2rem;

}

.country-info {
  display: flex;
  padding: 1rem;
  gap: 1rem;
  background-color: #2c3e50;
}
</style>