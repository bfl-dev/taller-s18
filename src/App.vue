<script setup>
import PopulationMan from "@/components/populationMan.vue";
import MangaRecom from "@/components/mangaRecom.vue";
</script>

<template>
  <main>
    <div class="populman">
      <population-man></population-man>
    </div>
    <div class="mangaRecom">
      <manga-recom></manga-recom>
    </div>
  </main>
</template>

<style scoped>
* {
  gap: 3rem;
}
.populman{
  width: 1000px;
}
</style>
