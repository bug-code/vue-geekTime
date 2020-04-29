<template>
  <div id="app">
    <!-- <img
      alt="Vue logo"
      src="./assets/logo.png"
    > -->
    <!--  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <p>{{msg}}</p>
    <input type="text" v-model="info" >
    <button @click="handClickAdd">添加</button>
    <ul>
      <todo-item v-for="(item ,index) in list" :key='index' :item = item></todo-item>
    </ul>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TodoItem from "./components/TodoItem.vue";

export default {
  name: "App",
  data() {
    return {
      msg: "hello GeekTime",
      info: "",
      list: []
    };
  },
  methods:{
    handClickAdd(){
      console.log(this.info)
      this.list.push(this.info)
    }
  },
  components: {
    // HelloWorld
    TodoItem
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
