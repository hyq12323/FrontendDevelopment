<template>
    <div class="person">
        <h2>姓名：{{ person.name }}</h2>
        <h2>年龄：{{ person.age }}</h2>
        <button @click="changeName">修改名称</button>
        <button @click="changeAge">修改年龄</button>
    </div>
</template>


<script lang="ts" setup name="Person">
import { reactive, toRefs, toRef } from "vue"
let person = reactive({
    name: "张三",
    age: 18
})

let { name, age } = toRefs(person)
let nl = toRef(person, 'age')

function changeName() {
    name.value += "~"
}

function changeAge() {
    age.value += 1
}
</script>

<style scoped></style>