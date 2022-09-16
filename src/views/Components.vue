<template>
     <div class="component">
      <h1>This is the Components page</h1>
      <p>2 + 2</p>
     <Navbar/>
    </div>
    <Footer></Footer>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'Components',
  components: {
    Navbar,
    Footer,
  },
  mounted() {
    console.log(this.$el.textContent); // I'm calculating elements inside the component.
  },
};
</script>
