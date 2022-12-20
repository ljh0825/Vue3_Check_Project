<script setup>
import {computed, ref} from "vue";

const props = defineProps({

});

let id = 0;
const newTodo = ref('');
const hideCompleted = ref(false);
const todos = ref([
  { id: id++, text: 'HTML 배우기', done: false},
  { id: id++, text: 'JavaScript 배우기', done: false},
  { id: id++, text: 'Vue 배우기', done: false},
]);

const filterTodos = computed(() => {
  return hideCompleted.value? todos.value.filter((todo) => !todo.done) : todos.value
});

function addTodo() {
  todos.value.push({id: id++, text: newTodo.value, done: false});
  newTodo.value = '';
};

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
};

function hideComplete() {
  hideCompleted.value = !hideCompleted.value;
}
</script>
<template>
  <div>
    <input v-model="newTodo">
    <button @click="addTodo">할 일 추가</button>
    <ul>
      <li v-for="todo in filterTodos" :key="todo.id">
        <input type="checkbox" v-model="todo.done">
        {{ todo.text }}
        <button @click="removeTodo(todo)">X</button>
      </li>
    </ul>
    <button @click="hideComplete">완료된 항목 숨기기</button>
  </div>
</template>

<style>
</style>
