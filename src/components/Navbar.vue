<template>
    <div>
       {{msg}}
       <button @click="rey">Botón Rey</button>
    </div>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    msg: String,
  },
  methods: {
    rey() {
      console.log('soy el rey del mundo');
    },
  },
};
</script>
