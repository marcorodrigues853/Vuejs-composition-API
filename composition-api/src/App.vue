<script>
import { computed, ref, reactive } from "vue";
const START_FROM = 10;
export default {
  setup() {
    const counter = ref(0);
    const multiplied = computed(() => counter.value * 10);
    const xxx = reactive({
      counter: 10,
    });
    const x2 = computed(() => multiplied.value);
    const ra = ref([1, 2, 3]);
    const replaceArray = () => (ra.value = [4, 5, 6]);
    const increase = () => counter.value++;
    return {
      counter,
      multiplied,
      START_FROM,
      increase,
      xxx,
      replaceArray,
      ra,
    };
  },
};
</script>
<template>
  <div>Hello world {{ counter }}</div>
  <button @click="increase">Increase</button>
  <button @click="replaceArray">Replace</button>
  <div>x10 {{ xxx.counter }}</div>
  <div>RA {{ ra }}</div>
</template>

<style></style>
