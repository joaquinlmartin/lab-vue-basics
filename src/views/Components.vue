<template>
     <div class="component">
      <h1>This is the {{ adjetive }} Components page</h1>
      <p v-show="mySuperArray.length > 0 && mySuperArray.length === 5">{{2 + 2}}</p>
      <p>{{5 * 10}}</p>
      <button v-bind:class="clicked ? 'joderred' : 'hostiablue'"
       v-on:click ="clicked = !clicked" class="btn">Botón v-bind</button>
      <button @click="colorchange" v-bind:style="{ color: activeColor }"
       class="btn">Botón Color</button>
     <Navbar/>
     <Footer>
      <template v-slot:slotquierechocolate>
      <p>Esto es un texo introducido por Slot</p>
      </template>
      <template v-slot:estimerosmatadores>
      <p>Somos los estimeros matadores!</p>
      </template>
    </Footer>
    <p>{{ gandalfTheGrey }}</p>
    <ul>
    <li v-for="elem in getAvailableGays"
     :key="elem.id" v-show="elem.id === 4">{{ elem.subtitle }}</li>
    </ul>
    <div v-for="elem in mySuperArrayGay" :key="elem.id" v-show="elem.id !== 4">
      <h3>{{ elem.title }}</h3>
      <h5>{{ elem.subtitle }}</h5>
    </div>
    <h3 v-if="showMessage">{{message}}</h3>
    <h3 v-else>{{messageAlternative}}</h3>
    <button :disabled="showMessage" v-on:click="returnString" class="btn">Return</button>
    <div>
    <br>
    <a href="https://www.google.es" class="a1">Ir a Goggle Forma 1</a>
    <br>
    <a v-bind:href="webToGo" class="a2">Ir a Goggle Forma 2</a>
    <br>
    <a :href="webToGo" class="a3">Ir a Goggle Forma 3</a>
    </div>
    <a :class="showMessage ? 'default' : 'new'"
    :href="webToGo">Ir a Goggle con Condicional</a>
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
      interMessage: ', ',
      messageAlternative: 'Yipi ka yei, hijo de puta',
      webToGo: 'https://www.google.es',
      mySuperArray: [1, 2, 3, 4, 5],
      myArrayGay: [
        {
          id: 1,
          title: 'Web Developer',
          subtitle: 'Fullstack soy Dios',
        },
        {
          id: 2,
          title: 'UX/UI',
          subtitle: 'Pinta y Colorea',
        },
        {
          id: 3,
          title: 'Data Analist',
          subtitle: 'Magnetos en potencia',
        },
      ],
      mySuperArrayGay: [
        {
          id: 1,
          title: 'Web Developer',
          subtitle: 'Fullstack soy Dios',
        },
        {
          id: 2,
          title: 'UX/UI',
          subtitle: 'Pinta y Colorea',
        },
        {
          id: 3,
          title: 'Data Analist',
          subtitle: 'Magnetos en potencia',
        },
      ],
    };
  },
  components: {
    Navbar, // El nombre es de ejemplo
    Footer, // El nombre es de ejemplo
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
    getAvailableGays() {
      return this.myArrayGay.filter((myArrayGay) => myArrayGay.id === 1);
    },
    gandalfTheGrey() {
      return `${this.adjetive + this.interMessage + this.message}`;
    },
  },
  beforeCreate() {
    this.myArrayGay = this.getAvailableGays;
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

.a1 {
  background-color: gold;
  border-radius: 3rem;
}

.a2 {
  background-color: red;
  border-radius: 3rem;
}

.a3 {
  background-color: skyblue;
  border-radius: 3rem;
}

.default {
  background-color:black;
}

.new {
  background-color:lightgreen;
}
</style>
