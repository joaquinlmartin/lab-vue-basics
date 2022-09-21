<template>
    <div>
       {{message}}
       <button :disabled="variableRey" @click="rey" class="btn">Botón Rey</button>
    </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      message: 'Soy el mensaje de Navbar-Rey',
      variableRey: false, // disabled está funcionando al revés, se activa cuando está en true.
    };
  },
  methods: {
    rey() {
      console.log('soy el rey del mundo');
    },
  },
};
</script>
