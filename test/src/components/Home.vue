<template>
  <div>{{ counter }}</div>
</template>

<script>
import {ref, watch } from 'vue'
export default {
  name: "home-component",
  setup() {

    let counter = ref(0)

    setInterval(() => counter.value++, 500)

    watch(counter, (newValue, old) => {
      console.log(newValue, old)
    })

    return {
      counter
    }

  },
};
</script>