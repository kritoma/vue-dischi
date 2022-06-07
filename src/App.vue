<template>
  <div id="app">
    <baseHeader/>
    <baseMain/>
  </div>
</template>

<script>
import BaseHeader from './components/block/baseHeader.vue'
import BaseMain from './components/block/baseMain.vue'


export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseMain
    
  }
}
</script>

<style lang="scss">
@import './assets/style/global.scss';
</style>
