<script setup>
import { ref } from "vue";

const text = ref('');

function onInput(e) {
  text.value = e.target.value;
}

</script>
<template>
  <div>
    <input v-model="text"/>
    <p>{{ text }}</p>
  </div>
</template>

<style>
</style>
