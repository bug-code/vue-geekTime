<template>
  <div>
    <button v-append-text="num" @click="num++">按钮</button>
  </div>
</template>

<script>
export default {
  directives:{
      appendText:{
        bind(){
            console.log('bind')
        },
        inserted(el,binding){
            el.appendChild(document.createTextNode(binding.value))
            console.log(el,binding)
        },
        update(){
            console.log('update')
        },
        componentUpdated(el,binding){
            console.log('componentUpdated')
            el.appendChild(document.createTextNode(binding.value))
        },
        unbind(){
            console.log("unbind")
        }
      }
  },
  data() {
    return {
        num:123456
    };
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
</style>
