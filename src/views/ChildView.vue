<script setup>
import { reactive, ref } from "vue";
import Vforview from './VforView.vue'
const props = defineProps({
  msg: String,
})

const emit = defineEmits(['response']);

emit('response', '자식이 보냅니다')

const message = ref('안녕 Vue!');
//반응형 상태
const counter = reactive({
  count: 0,
});
</script>
<template>
  <div>
    <h1 @response="emit">{{ msg }}</h1>
    받앗슈
    <p></p>
  </div>
</template>

<style>
@media (min-width: 1024px) {
}
</style>
