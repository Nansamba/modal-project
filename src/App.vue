<template>
<div>
  <h1> ninja Reation timer</h1> 
  <button @click= "start"> play </button>
  <Block v-if="isPlaying" :delay="delay"/>
</div>

</template>

<script>
import Block from './components/Block.vue'
export default {
  name: 'App',
  components: { Block },  

  data(){
  return {
  isPlaying: false,
  delay: null
  }},
  methods: {
  start(){
    this.delay = 2000 + random() * 5000
    this.isPlaying = true
  }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
