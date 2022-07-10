<template>
  <div>{{fullName}}</div>
</template>

<script>
import { computed, ref, toRefs } from '@vue/runtime-core';

export default {
  name: "home-component",
  props: {
    firstName: String,
    lastName: String
  },
  setup(props) {

    let {firstName , lastName} = toRefs(props)

    firstName = ref("Dario")

    const fullName = computed(() => {
      return `${firstName.value} ${lastName.value}` 
    })
 
    return {
      fullName
    }

  },
};
</script>