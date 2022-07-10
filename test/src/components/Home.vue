<template>
  <div>{{fullName}}</div>
</template>

<script>
import { ref } from '@vue/reactivity';
import { computed } from '@vue/runtime-core';

export default {
  name: "home-component",
  setup() {

    const name = ref('Diana')
    const lastName = ref('Martinez')

    const fullName = computed(() => {
      return `${name.value} ${lastName.value}` 
    })
 
    return {
      fullName
    }

  },
};
</script>