<template>
    <div>
       {{msag}}
       <button @click="rey">Botón Rey</button>
    </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      msag: 'Soy el mensaje de Navbar-Rey',
    };
  },
  methods: {
    rey() {
      console.log('soy el rey del mundo');
    },
  },
};
</script>
