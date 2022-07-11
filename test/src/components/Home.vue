<template>
  <div>{{fullName}}</div>
  <div>{{username}}</div>
  <button ref="btn">Click!</button>
</template>


<script>
  export default {
    name: 'home-component'
  }
</script>

<script setup>
import { computed, inject, ref, toRefs, watch, defineExpose, defineProps} from '@vue/runtime-core';

  const props = defineProps({
    firstName: String,
    lastName: String
    })

    const username = inject("username")

    const btn = ref(null);

    console.log(btn.value)

    let {firstName , lastName} = toRefs(props)
    firstName = ref("Dario")

    const fullName = computed(() => {
      return `${firstName.value} ${lastName.value}` 
    })

    defineExpose({
    fullName,
    })

    watch(btn, (value) => {
      console.log(value)
    })

</script>