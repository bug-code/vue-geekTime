<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
   <!--  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
   <p>{{msg}}</p>
    <ul>
      <TodoItem ></TodoItem>  
    </ul>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'App',
  data() {
    return {
      msg:'hello GeekTime'
    }
  },
  components: {
    // HelloWorld
    TodoItem
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
