<template>
  <div id="app">
    <p>{{msg}}</p>
    <input type="text" v-model="info" >
    <button @click="handClickAdd">添加</button>
    <ul>
      <todo-item v-for="(item ,index) in list" :key='index'>
        <template v-slot:item="itemProps">
           <span :style="{fontSize:'20px',color:itemProps.check ? 'red': 'blue'}">{{item}}</span>
        </template>
        <template v-slot:header>
          <h1>Here might be a page title</h1>
        </template>

        <template v-slot:default>
          <p>A paragraph for the main content.</p>
          <p>And another one.</p>
        </template>

        <template v-slot:footer>
          <p>Here's some contact info</p>
        </template>
      </todo-item>
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
