<script setup>
import { ref } from "vue";
const titleClass = ref('title');
</script>
<template>
  <div>
    <h1 :class="titleClass">{{ titleClass }}</h1>
  </div>
</template>

<style>
.title {
  color: red;
}
@media (min-width: 1024px) {
}
</style>
