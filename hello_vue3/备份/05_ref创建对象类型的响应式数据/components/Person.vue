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
    </div>
</template>

<script lang="ts">
export default {
    name: 'Person',
}
</script>

<script lang="ts" setup>
import { ref } from "vue"
// 数据
let car = ref({
    brand: "奔驰",
    price: 100,
})

let games = ref([
    { id: "1", name: "王者荣耀" },
    { id: "2", name: "CF" },
    { id: "3", name: "DNF" }
])



// 方法
function changePrice() {
    car.value.price += 10
}

function changeFirstGame() {
    games.value[0].name = "一坨大便"
}

</script>

<style scoped></style>