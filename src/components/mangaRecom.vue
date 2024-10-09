<script setup>

import {onMounted, ref} from 'vue';
import axios from 'axios';

let mangaData = ref({});

const getManga = async () => {
  await axios.get("https://api.jikan.moe/v4/random/manga")
      .then( req => mangaData.value = req.data.data);
  console.log(mangaData.value)
}

onMounted( () => {
  //getPopulation();
})
</script>

<template>
<button @click="getManga()">Manga</button>
  <div class="manga-container">
    <img :src="mangaData.images.jpg.image_url">
    <p>Titulo: {{mangaData.title}}</p>
    <p>Titulo en Japones: {{mangaData.title_japanese}}</p>
    <p>Sinopsis:  <br> {{mangaData.synopsis}}</p>
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