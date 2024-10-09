<script setup>

import {onMounted, ref} from 'vue';
import axios from 'axios';

let worldData = ref([]);
let algo = worldData.value

const getPopulation = async () => {
  await axios.get("https://countriesnow.space/api/v0.1/countries/population")
      .then( req => req.data.data.forEach( d => worldData.value.push(d)))
}

onMounted( () => {
  getPopulation();
  console.log(worldData.value.keys)
  worldData.value.forEach( r => console.log(r))
})
</script>

<template>
</template>

<style scoped>

</style>