<script setup>
import { ref, watch} from "vue";
import { useMouse } from "./ComposableView.vue";

const { x, y } = useMouse();
const todoId = ref(1);
const todoData = ref(null);

async function fetchData() {
  todoData.value = null;
  const res = await fetch(
`https://jsonplaceholder.typicode.com/todos/${todoId.value}`
  );
  todoData.value = await res.json();
};

fetchData()
watch(todoId, fetchData);

</script>
<template>
  <p>할 일 id: {{ todoId}}</p>
  <button @click="todoId++">다음 할 일 가져오가</button>
  <p v-if="!todoData">로딩...</p>
  <pre v-else>{{ todoData }}</pre>

  마우스 위치: {{ x }} , {{ y }}
</template>

<style>
</style>
