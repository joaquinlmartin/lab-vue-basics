<template>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
    </head>
    <body>
     <div class="component">
      <h1>This is the Components page</h1>
     <Navbar/>
    </div>
    <aside>
      2 + 2
    </aside>
    <aside>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit.
    </aside>
    <aside>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit.
    </aside>
    <footer>
      <Footer/>
    </footer>
    </body>
    </html>
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
};
</script>
