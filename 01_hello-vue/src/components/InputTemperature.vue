<script setup>

    defineProps({
        value: Number,
        unit: String,
    })
</script>

<template>
  <div>
    <label :for="unit">{{ unit }}</label>
    <input type="number" :id="unit" :value="value" v-model="tempK">
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  text-align: left;
  width: 200px;
}
</style>
