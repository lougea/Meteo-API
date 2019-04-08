<template>
  <div id="app">

    <barrePlus/>

  </div>
</template>

<script>
import Image from './assets/nuage.jpg'
import barrePlus from './components/barrePlus.vue'
export default {
  name: 'app',
  components: {
    barrePlus,
  },
  methods :{

  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Rajdhani:500');
#app {
  font-family: 'Rajdhani', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-size: cover;
  background-image: url('./assets/nuage.jpg');
  height: 950px;
}

</style>
