<script setup>
let props = defineProps(["countryData"])
</script>

<template>
  <div class="country-info">
    <p>Pais: {{countryData.country}}</p>
    <p>Codigo: {{countryData.code}}</p>
  </div>
  <div class="country-hist">
    <div v-for=" item in countryData.populationCounts" class="count">
      <p>Año: {{item.year}}</p>
      <p>Cantidad: {{item.value}}</p>
    </div>
  </div>
</template>

<style scoped>
.country-info {
  display: flex;
  padding: 1rem;
  gap: 1rem;
  background-color: #2c3e50;
}

.country-hist{
  height: 400px;
  overflow-y: scroll;
}
</style>