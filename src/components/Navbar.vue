<template>
    <div>
       {{message}}
       <button @click="rey" class="btn">Botón Rey</button>
    </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      message: 'Soy el mensaje de Navbar-Rey',
    };
  },
  methods: {
    rey() {
      console.log('soy el rey del mundo');
    },
  },
};
</script>
