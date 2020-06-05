<template>
    <li class="list">
        <input type="checkbox" name="" id="" v-model="check">
        <slot name="item" v-bind="{check}">11111</slot>
        <slot name="header">11111</slot>
        <slot>11111</slot>
        <slot name="footer">11111</slot>
    </li>
</template>
<script>
export default {
    props:['item'],
    data () {
        return {
            check:false
        }
    }
}
</script>
<style  scoped>
    .item{
        color :red;
    }
</style>