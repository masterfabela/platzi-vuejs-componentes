<template>
  <div>
    <button @click="toggle">Modal</button>
    <teleport to="body">
      <div v-show="show" class="modal">
        <h1>Titulo</h1>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Excepturi
          nulla ipsa sapiente delectus porro illum, sit, impedit, error cumque
          cupiditate possimus amet autem fugiat! Quos dolor est quia inventore
          illo!
        </p>
        <button @click="toggle">Cerrar</button>
      </div>
    </teleport>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    };
  },
  methods: {
    toggle() {
      this.show = !this.show;
    },
  },
};
</script>
