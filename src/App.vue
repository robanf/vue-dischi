<template>
  <div id="app">
    <Header/>
    <Mainsong/>
    <p class="lead">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Corrupti, culpa? Qui veritatis repellat corrupti vero officiis inventore amet, porro ducimus asperiores impedit voluptate sequi odit recusandae natus incidunt doloremque accusamus.</p>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Mainsong from './components/Mainsong.vue'

export default {
  name: 'App',
  components: {
    Header,
    Mainsong
  }
}
</script>

<style lang="scss">
@import '@/style/General.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
