<template>
    <div class="person">
        <h2>汽车信息：一辆{{ car.brand }}车，价值{{ car.price }}万</h2>
        <button @click="changePrice">修改汽车价格</button>
        <button @click="changeBrand">修改汽车品牌</button>
        <button @click="changeCar">修改汽车</button>
        <br>
        <h2>当前求和：{{ sum }}</h2>
        <button @click="changeSum">点我sum+1</button>
    </div>
</template>

<script lang="ts">
export default {
    name: 'Person',
}
</script>

<script lang="ts" setup>
import { ref } from "vue"
import { reactive } from "vue"
// 数据
// let car = reactive({
//     brand: "奔驰",
//     price: 100,
// })

let car = ref({
    brand: "奔驰",
    price: 100,
})

let sum = ref(0)



// 方法
function changePrice() {
    // car.price += 10
    car.value.price += 10
}

function changeSum() {
    // sum = ref(9) 错误
    sum.value += 1
}

function changeBrand() {
    // car.brand = "宝马"
    car.value.brand = "宝马"
}

function changeCar() {
    // car = { brand: "奥拓", price: 1 } 页面不更新
    // car = reactive({ brand: "奥拓", price: 1 }) 页面不更新
    // Object.assign(car, { brand: "奥拓", price: 1 }) 正确
    car.value = { brand: "奥拓", price: 1 }
}

</script>

<style scoped></style>