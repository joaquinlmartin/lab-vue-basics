<template>
     <div class="component">
      <h1>This is the Components page</h1>
      <p>{{2 + 2}}</p>
      <p>{{5 * 10}}</p>
      <button v-bind:class="clicked ? 'hostia' : 'joder'"
       v-on:click ="clicked = !clicked">Botón v-bind</button>
      <button @click="colorchange" v-bind:style="{ color: activeColor }">Botón Color</button>
     <Navbar/>
    </div>
    <Footer></Footer>
    {{message}}
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
    };
  },
  computed: {
    propertyComputed() {
      console.log('I change when this.property changes.');
      return this.property;
    },
  },
  components: {
    Navbar,
    Footer,
  },
  created() {
    this.property = 'Example property update.';
    console.log('propertyComputed will update, as this.property is now reactive.');
  },
  methods: {
    colorchange() {
      console.log('colorsito cambiado');
    },
  },
  /* mounted() {
    this.property = 'Example property update.';
    console.log(this.$el.textContent); // I'm calculating elements inside the component.
  }, */
};
</script>
