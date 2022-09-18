<template>
     <div class="component">
      <h1>This is the {{ adjetive }} Components page</h1>
      <p>{{2 + 2}}</p>
      <p>{{5 * 10}}</p>
      <button v-bind:class="clicked ? 'joderred' : 'hostiablue'"
       v-on:click ="clicked = !clicked" class="btn">Botón v-bind</button>
      <button @click="colorchange" v-bind:style="{ color: activeColor }"
       class="btn">Botón Color</button>
     <Navbar/>
     <Footer></Footer>
    {{message}}
    </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'Components',
  data() {
    return {
      message: 'Hola soy la hostia y lo sabes',
      property: 'Blank',
      clicked: false,
      activeColor: 'blue',
      adjetive: 'super',
    };
  },
  components: {
    Navbar,
    Footer,
  },
  methods: {
    colorchange() {
      this.activeColor = 'red';
      console.log('colorsito cambiado');
    },
  },
  computed: {
    propertyComputed() {
      console.log('I change when this.property changes.');
      return this.property;
    },
  },
  created() {
    this.property = 'Example property update.';
    console.log('propertyComputed will update, as this.property is now reactive.');
  },
  mounted() {
    this.property = 'Example property update.';
    console.log(this.$el.textContent); // I'm calculating elements inside the component.
  },
};
</script>

<style>
  .component {
  color: purple;
}

.btn {
  border-radius: 3rem;
}

.hostiablue {
  background-color: blue;
}

.joderred {
  background-color: red;
}
</style>
