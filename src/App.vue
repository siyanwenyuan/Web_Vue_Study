<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <p>父组件中的数据{{childDate}}</p>
    <HelloWorld
        msg="Welcome to Your Vue.js App"
        :count="parentCount"
        @child-count-change="handler"
    >
      这是默认内容1
    </HelloWorld>
    <HelloWorld>这是默认内容2</HelloWorld>
    <HelloWorld>这是默认内容3</HelloWorld>
    <HelloWorld></HelloWorld>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  data() {
    return {
      parentCount: 1000,
      childDate:0
    }
  },
  methods:{
    handler(childCount){
      this.childDate=childCount
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
