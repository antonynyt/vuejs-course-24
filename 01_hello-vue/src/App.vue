<script setup>
import InputTemperature from './components/InputTemperature.vue'
import {computed, ref, watch} from 'vue'

const tempK = ref(11);

const tempC = computed({
  get: () => tempK.value - 273.15,
  set: (val) => {
    tempK.value = val + 273.15
  }
})

const tempF = computed({
  get: () => tempK.value * 9/5 - 459.67,
  set: (val) => {
    tempK.value = (val + 459.67) * 5/9
  }
})

</script>

<template>
  <h1>Temperature convertor</h1>

  <div>
    <input type="number" v-model="tempK">
    <input type="number" v-model="tempC">
    <input type="number" v-model="tempF">

  </div>


  <!-- <InputTemperature :value="tempK" unit="Kelvin"/>
  <InputTemperature :value="tempC" unit="Celsius"/>
  <InputTemperature :value="tempF" unit="Fahrenheit"/> -->
</template>

<style scoped>
  div {
    display: flex;
    flex-direction: column;
    gap:20px;
    width: 200px;
  }
</style>
