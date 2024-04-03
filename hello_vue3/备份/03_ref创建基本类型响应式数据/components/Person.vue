<template>
    <div class="person">
        <h2>姓名：{{ name }}</h2>
        <h2>年龄：{{ age }}</h2>
        <h2>地址：{{ address }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看联系方式</button>
    </div>
</template>

<script lang="ts">
export default {
    name: 'Person',
}
</script>

<script lang="ts" setup>
import { ref } from "vue"
// setup函数中的this是undefined，Vue3中已经弱化this了
// 数据，原来写在data中的，此时的name、age、tel都是响应式的数据
let name = ref("张三") // 此时name不是响应式的
let age = ref(18) // 此时age不是响应式的
let tel = "18351175517" // 此时tel不是响应式的
let address = "北京"

// 方法
function changeName() {
    name.value = "zhansan"
}
function changeAge() {
    age.value += 1
}
function showTel() {
    alert(tel)
}

</script>

<style scoped></style>