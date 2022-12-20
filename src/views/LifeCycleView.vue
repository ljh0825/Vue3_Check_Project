<script setup>
import {onMounted, onUnmounted, onUpdated, ref} from "vue";
const p = ref(null);
const count = ref(0);

onMounted(() => {
  p.value.textContent = '아니야';
}); //컴포넌트가 마운트 되었을 때,
// 동기식 자식 컴포넌트가 모두 마운트 됨
// 일반적으로 컴포넌트의 렌더링된 Dom에 접근해야 하는 사이드 이펙트를 실행하거나,
// SSR에서 Dom과 관련된 코드를 클라이언트에서만 실행하도록 제한하는 데 사용

onUpdated(() => {
  console.log(document.getElementById('count').textContent);
});
// 컴포넌트의 DomTree가 업데이트된 후 수행
// 부모 컴포넌트의 Updated 훅은 자식 컴포넌트의 훅 이후에 호출
// 상태 변경에 영향을 받을 컴포넌트의 DOM 업데이트 후에 호출

onUnmounted(() => {

});
//컴포넌트가 마운트 해제된 후 호춯될 콜백을 등록
//모든 자식 컴포넌트가 마운트 해제됨
//관련된 모든 반응형 이펙트가 중지됨
</script>
<template>
  <div>
    <p ref="p">안녕</p>
    <button id="count" @click="count++">{{ count }}</button>
  </div>
</template>

<style>
@media (min-width: 1024px) {
}
</style>
