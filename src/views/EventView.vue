<script setup>
import { ref } from "vue";
const count = ref(0);

function countUp() {
  count.value++;
}
</script>
<template>
  <div>
    <h1 @click="countUp">{{count}}</h1>
  </div>
</template>

<style>


</style>
