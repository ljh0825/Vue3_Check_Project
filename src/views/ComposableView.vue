<script>
import {onMounted, onUnmounted, ref} from "vue"

export function useMouse() {
  const x = ref(0);
  const y = ref(0);

 useEventListener(window, 'mousemove', (event) => {
    x.value = event.pageX
    y.value = event.pageY
  });
 return { x, y }
}

export function useEventListener(target, event, callback) {
  onMounted(() => target.addEventListener(event, callback))
  onUnmounted(() => target.removeEventListener(event, callback))
}
</script>
<template>
  마우스 위치 : {{ x }}, {{  y }}
</template>

<style>
</style>
