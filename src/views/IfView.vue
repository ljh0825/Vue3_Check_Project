<script setup>
import { ref } from "vue";

const awesome = ref(true);

function toggle(e) {
  awesome.value = !awesome.value;
}
</script>
<template>
  <div>
    <button @click="toggle">토글 버튼</button>
    <h1 v-if="awesome">Vue는 굉장해</h1>
    <h1 v-else>오 안돼</h1>
  </div>
</template>
<style>
</style>
