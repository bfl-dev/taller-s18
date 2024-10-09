<script setup>

import {onMounted, ref} from 'vue';
import axios from 'axios';
import Country from "@/components/country.vue";

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
      <country :country-data="item"></country>
    </div>
  </div>
</template>

<style scoped>
.country-container{
  display: flex;
  width: 100%;
  flex-direction: row;
  gap: 2rem;
  overflow-x: scroll;
}


</style>