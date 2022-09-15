<template>
    <footer>
      <button @click="reina">Botón Reina</button>
    </footer>
</template>

<script>
export default {
  name: 'Footer',
  props: {
    msg: String,
  },
  methods: {
    reina() {
      console.log('soy la reina sexy');
    },
  },
};
</script>
