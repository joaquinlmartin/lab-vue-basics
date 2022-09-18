<template>
    <footer>
      {{ message }}
      <button @click="reina" class="btn">Botón Reina</button>
    </footer>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      message: 'Soy el mensaje sexy de Footer-Reina',
    };
  },
  methods: {
    reina() {
      console.log('soy la reina sexy');
    },
  },
};
</script>
