<template>
  <div>
      <p>{{msg}}</p>
      <p>{{msgData}}</p>
      <p>{{msgChange}}</p>
      <p>{{type}}</p>
      <!-- <p>{{title}}</p> -->
      <p>{{isPublished}}</p>
      <p v-for="(item,index) in commentIds" :key="index">{{item}}</p>
      <p>{{author.name}}</p>
      <p>{{author.company}}</p>
      <button @click="changgeMsg">changgeMsg</button>
  </div>
</template>

<script>
export default {
    inheritAttrs: false,
    //prop在子组件中接收值的时候，应该是一个对象的形式，希望每个 prop 都有指定的值类型。

    //错误的形式
    // props:['title','is-published','comment-ids','author']

    //正确的形式
    props:{
        msg:String,
        // title:[String, Number],
        type:{
            validator:function(value){
                return value>=0 && value<=128;
            },
        },

        isPublished:{
            type:Boolean,
            default:false
        },
        commentIds:{
            type:Array,
            default:()=>{
                return []
            }
        },
        author:{
            type:Object,
            default:()=>{
                return {}
            }
        }
    },
    data() {
        return {
           msgData:this.msg 
        }
    },
    computed:{
        msgChange(){
            return this.msg.trim().toLowerCase()
        }
    },
    methods: {
        changgeMsg(){
            this.msgData = '6666'
            console.log(this.msgData,this.msg)
        }
    },
}
</script>

<style lang="scss" scoped>
</style>
