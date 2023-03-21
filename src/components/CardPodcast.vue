<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    podcast: Object,
})

</script>

<template>
  <div class="card">
    <h1>{{ podcast }}</h1>
    <h1>AUTHOR : {{ podcast }}</h1>
  </div>
</template>

<style lang="scss">
.card {
    width: 1000px;
    height: 100px;
    background-color: red;
    color:white;
}
</style>
