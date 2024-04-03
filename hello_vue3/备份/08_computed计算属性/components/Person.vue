<template>
    <div class="person">
        姓：<input type="text" v-model="fristName">
        <br>
        名：<input type="text" v-model="lastName">
        <br>
        全名：<span>{{ fullName }}</span>
        <br>
        <button @click="changeFullName">修改全名</button>
    </div>
</template>


<script lang="ts" setup name="Person">
import { ref, computed } from "vue"

let fristName = ref("zhang")
let lastName = ref("san")

// 这么定义的fullName是一个计算属性，且是只读的
// let fullName = computed(() => {
//     return fristName.value.slice(0, 1).toUpperCase() + fristName.value.slice(1) + lastName.value
// })

// 这么定义的fullName是一个计算属性，且是可读可写的
let fullName = computed({
    get() {
        return fristName.value.slice(0, 1).toUpperCase() + fristName.value.slice(1) + lastName.value
    },
    set(val) {
        console.log(val)
        const [str1, str2] = val.split("-")
        fristName.value = str1
        lastName.value = str2
    }
})

function changeFullName() {
    fullName.value = "li-si"
}
</script>

<style scoped></style>