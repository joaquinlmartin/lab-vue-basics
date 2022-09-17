<template>
    <footer>
      {{msg}}
      <button @click="reina">Botón Reina</button>
    </footer>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      msg: 'Soy el mensaje sexy de Footer-Reina',
    };
  },
  methods: {
    reina() {
      console.log('soy la reina sexy');
    },
  },
};
</script>
