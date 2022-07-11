<template>
  <div>{{fullName}}</div>
  <div>{{username}}</div>
</template>

<script>
import { computed, inject, ref, toRefs } from '@vue/runtime-core';

export default {
  name: "home-component",
  props: {
    firstName: String,
    lastName: String
  },
  setup(props, context) {

    console.log(context)

    const username = inject("username")

    let {firstName , lastName} = toRefs(props)
    firstName = ref("Dario")

    const fullName = computed(() => {
      return `${firstName.value} ${lastName.value}` 
    })

    context.expose({
      fullName,
    })

    return {
      fullName,
      username
    }

  },
};
</script>