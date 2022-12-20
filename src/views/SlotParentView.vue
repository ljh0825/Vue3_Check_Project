<script setup>
import {ref} from "vue"
import SlotChideView from "./SlotChideView.vue";

const msg = ref('Vue는 개발자에게 정말 유용하죠! 🎁')
</script>
<template>
  <SlotChideView>부모로부터 : {{ msg }}</SlotChideView>
</template>

<style>

</style>
