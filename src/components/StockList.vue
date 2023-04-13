<template>
    <div class="container">
        <button @click="buttonClick">Click me</button>
        <StockDetails v-for="stock in stockList" :key="stock.id" :stockName="stock.name" :stockPrice="stock.price" :stockTicker="stock.ticker" >
        </StockDetails>
    </div>
</template>

<script>
import StockDetails from './StockDetails.vue'
import { ref } from 'vue'
import { Stock } from './stock'
export default {
    name: 'StockList',
    components: {StockDetails},
    setup() {
        let counter = 0
        const stockList = ref([])
        const buttonClick = () => {
            const stock = new Stock("air canada", "25", "AC", counter)
            counter += 1
            stockList.value.push(stock)
        }
        return {stockList, buttonClick}
    }
}
</script>

<style>
.container {
    height: 300px;
    width: 1000px;
    /* width: 100%; */
    border: 2px solid red;
    background: purple;
}

.stock-list-container {
    height: 100%;
}
</style>