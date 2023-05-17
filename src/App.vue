<template>
  <h1>Reaction timer</h1>
  <hr>
  <h2>Click on the boxes as quickly as you can!</h2>
  <button @click="startgame()" :disabled="isshow">Start game!</button>
  <block v-if="isshow" :delay="delay" @endgame="res"></block>
  <Result v-if="showres" :resulttime="resulttime" ></Result>
</template>

<script>

import Block from './components/block.vue'
import Result from './components/result.vue'

export default {
  name: 'App',
  data () {
    return {
      isshow: false,
      showres: false,
      resulttime:0,
      delay:0
    }
  },
  components: {Block,Result},
  methods:{
    startgame(){
      this.isshow = true
      this.delay = 2000+Math.random()*5000  //random time between 2 and 7 seconds
      this.showres = false
    },
    res(result){
      this.isshow = false
      this.resulttime = result
      this.showres = true
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
  color: #444;
  margin-top: 60px;
}
</style>
