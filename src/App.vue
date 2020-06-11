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
        <!-- <template v-slot:header>
          <h1>Here might be a page title</h1>
        </template>

        <template v-slot:default>
          <p>A paragraph for the main content.</p>
          <p>And another one.</p>
        </template>

        <template v-slot:footer>
          <p>Here's some contact info</p>
        </template> -->
      </todo-item>
    </ul>
    <hr>
    <!-- <props-page
      :msg="msg"
      title="Demo"
      :is-published="false"
      :comment-ids="list"
      :type="type"
      :author="{
        name: 'Veronica',
        company: 'Veridian Dynamics'
      }"
      class="propDemo"
    ></props-page> -->
    <evevt-page @change="upData" :valueName="info"></evevt-page>
    <h1>{{info}}</h1>
    <directive-page></directive-page>
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem.vue";
// import Props from './components/props.vue';
import Event from './components/Event.vue';

import Directive from './components/directive.vue';


export default {
  name: "App",
  data() {
    return {
      msg: "hello GeekTime",
      info: "",
      list: [],
      type:'successssss',

    };
  },
  methods:{
    handClickAdd(){
      this.list.push(this.info)
      this.info = '';
    },
    upData(data){
      this.info = data;
    }
  },
  components: {
    // HelloWorld
    TodoItem,
  //  "props-page": Props,
   "evevt-page":Event,
   "directive-page":Directive,
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
