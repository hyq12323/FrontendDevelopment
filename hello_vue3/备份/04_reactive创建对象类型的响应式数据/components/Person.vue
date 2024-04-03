<template>
    <div class="person">
        <h2>汽车信息：一辆{{ car.brand }}车，价值{{ car.price }}万</h2>
        <button @click="changePrice">修改汽车价格</button>
        <br>
        <h2>游戏列表：</h2>
        <ul>
            <li v-for="g in games" :key="g.id">{{ g.name }}</li>
        </ul>
        <button @click="changeFirstGame">修改第一个游戏名称</button>
        <br>
        <h2>测试：{{ obj.a.b.c }}</h2>
        <button @click="changeTestData">测试</button>
    </div>
</template>

<script lang="ts">
export default {
    name: 'Person',
}
</script>

<script lang="ts" setup>
import { reactive } from "vue"
// 数据
let car = reactive({
    brand: "奔驰",
    price: 100,
})

let games = reactive([
    { id: "1", name: "王者荣耀" },
    { id: "2", name: "CF" },
    { id: "3", name: "DNF" }
])

let obj = reactive({
    a: {
        b: {
            c: 666
        }
    }
})

// 方法
function changePrice() {
    car.price += 10
}

function changeFirstGame() {
    games[0].name = "一坨大便"
}

function changeTestData() {
    obj.a.b.c = 999
}

</script>

<style scoped></style>