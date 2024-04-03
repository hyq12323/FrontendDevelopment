<template>
    <div class="person">
        <h1>情况三: 监视【reactive】定义的【对象类型】数据</h1>
        <h2>姓名：{{ person.name }}</h2>
        <br>
        <h2>年龄：{{ person.age }}</h2>
        <br>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="changePerson">修改整个人</button>
    </div>
</template>


<script lang="ts" setup name="Person">
import { reactive, watch } from "vue"

// 数据
let person = reactive({
    name: "王杰",
    age: 30
}
)

// 方法
function changeName() {
    person.name = "王杰大傻逼"
}

function changeAge() {
    person.age += 1
}

function changePerson() {
    Object.assign(person, {
        name: "王杰呆逼",
        age: 100
    })
}

/*
    监视
    情况三：监视【reactive】定义的【对象类型】数据，且默认是开始深度监视的
*/

watch(person, (newValue, oldValue) => {
    console.log("person变化了", newValue, oldValue);
}, { deep: true })
</script>

<style scoped></style>