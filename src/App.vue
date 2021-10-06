<template>
  <h2>{{ state.count }}, doubled = {{state.double}}</h2>
  <button @click="UpdateCount(true)">Increment</button>
  <button @click="UpdateCount(false)">Decrease</button>
</template>

<script>
import { reactive, computed } from "vue";

export default {
  setup() {
    const state = reactive({
      count: 0,
      double: computed(() => state.count *2)
    })

    function UpdateCount(increase) {
      if (increase) 
        state.count++;
      else 
        state.count--;

    }

   

    return {
        state,
        UpdateCount
      };
  },
};
</script>

<style>
</style>
