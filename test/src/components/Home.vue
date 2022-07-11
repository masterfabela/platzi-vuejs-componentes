<template>
  <div>{{fullName}}</div>
  <div>{{username}}</div>
  <button ref="btn">Click!</button>
</template>

<script>
import { computed, inject, ref, toRefs, watch } from '@vue/runtime-core';

export default {
  name: "home-component",
  props: {
    firstName: String,
    lastName: String
  },
  setup(props, context) {

    console.log(context)

    const username = inject("username")

    const btn = ref(null);

    console.log(btn.value)

    let {firstName , lastName} = toRefs(props)
    firstName = ref("Dario")

    const fullName = computed(() => {
      return `${firstName.value} ${lastName.value}` 
    })

    watch(btn, (value) => {
      console.log(value)
    })

    context.expose({
      fullName,
    })

    return {
      fullName,
      username,
      btn
    }

  },
};
</script>