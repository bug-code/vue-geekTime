<template>
  <div>
     <input type="text" :value="valueName" @change="upDataParentDataInfo"> 
     <div @click="handClickDiv">
        <button  @click="handClickButton">重制成功</button>
        <button  @click="handClickButton">重制失败</button>
     </div>
  </div>
</template>

<script>

/****
 * 子组件--->父组件
 * 子组件绑定方法，方法内触发this.$emit(‘functionName’，value)
 * 父组件上绑定方法，事件为 @ functionName ，事件内取到value的值
 */
export default {
    props:{
        valueName:String,
    },
    data(){
        return {
            name:''
        }
    },
    methods: {
        upDataParentDataInfo(e){
            this.$emit('change',e.target.value)
        },
        handClickDiv(){
            this.$emit('change','') 
        },
        handClickButton(e){
            // 1111111
            e.stopPropagation()
        }
    }
}
</script>

<style lang="scss" scoped>
</style>
