<template>
  <div>{{ text }}</div>
  <div>{{ algo }}</div>
</template>

<script>
import base from "@/mixins/base";

export default {
  name: "App",
  mixins: [base],
  components: {},
  data() {
    return {
      text: "Hola vue",
      show: false,
    };
  },
  beforeCreate() {
    console.log("beforeCreate", this.$data, this.$el);
  },
  created() {
    console.log("created", this.$data, this.$el);
  },
  mounted() {
    console.log("mounted", this.$data, this.$el);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.fade-enter-from {
  opacity: 0;
}
.fade-leave-to {
  opacity: 0;
}

.fade-leave-active,
.fade-enter-active {
  transition: opacity 0.5s ease;
}
</style>
