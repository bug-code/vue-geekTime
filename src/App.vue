<template>
  <div id="app">
    <p>{{msg}}</p>
    <input type="text" v-model="info" >
    <button @click="handClickAdd">添加</button>
    <ul>
      <todo-item v-for="(item ,index) in list" :key='index' :item = item></todo-item>
    </ul>
  </div>
</template>

<script>
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
      this.list.push(this.info)
      this.info = '';
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
