<template>
  <div></div>
</template>

<script>
import { onMounted } from "vue";
export default {
  name: "home-component",
  setup() {
    onMounted(() => {
      console.log("mounted!");
    });
  },
};
</script>