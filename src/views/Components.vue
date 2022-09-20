<template>
     <div class="component">
      <h1>This is the {{ adjetive }} Components page</h1>
      <p v-if="mySuperArray.length > 0 && mySuperArray.length === 5">{{2 + 2}}</p>
      <p>{{5 * 10}}</p>
      <button v-bind:class="clicked ? 'joderred' : 'hostiablue'"
       v-on:click ="clicked = !clicked" class="btn">Botón v-bind</button>
      <button @click="colorchange" v-bind:style="{ color: activeColor }"
       class="btn">Botón Color</button>
     <Navbar/>
     <Footer></Footer>
    <h3 v-if="showMessage">{{message}}</h3>
    <h3 v-else>{{messageAlternative}}</h3>
    <button @click="returnString" class="btn">Return</button>
    </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'Components',
  data() {
    return {
      message: 'Soy la hostia y lo sabes',
      property: 'Blank',
      clicked: false,
      activeColor: 'blue',
      adjetive: 'super',
      showMessage: false,
      messageAlternative: 'Yipi ka yei, hijo de puta',
      mySuperArray: [1, 2, 3, 4, 5],
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
    returnString() {
      return 'string' && console.log('string de la buena');
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
    console.log(this.$el.textContent); // Está reflejando en consola el texto de la de la vista.
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
