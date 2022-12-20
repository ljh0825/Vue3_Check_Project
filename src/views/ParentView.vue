<script setup>
import { reactive, ref } from "vue";
import ChildView from "./ChildView.vue";

const message = ref('안녕 Vue!');
//반응형 상태
const counter = reactive({
  count: 0,
});

</script>
<template>
  <div>
    <h1>{{ message }}</h1>
    <p>{{ counter.count }}</p>
  </div>
  <ChildView @response="(msg) => message = msg"/>
</template>

<style>
@media (min-width: 1024px) {
}
</style>
