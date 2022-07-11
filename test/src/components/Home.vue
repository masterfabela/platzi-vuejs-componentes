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
  setup(props, context) {

    console.log(context)

    let {firstName , lastName} = toRefs(props)
    firstName = ref("Dario")

    const fullName = computed(() => {
      return `${firstName.value} ${lastName.value}` 
    })

    context.expose({
      fullName
    })

    return {
      fullName
    }

  },
};
</script>