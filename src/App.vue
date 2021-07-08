<template>
  <div id="app">
    <Header/>
    <Mainsong/>
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

</style>
