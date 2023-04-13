<template>
    <div class="stock-information-container">
        <div class="stock-name">Name: {{ props.stockName }}</div>
        <div class="stock-price">Price {{ props.stockPrice }}</div>
        <div class="ticker">Ticker {{ props.stockTicker }}</div>
    </div>
</template>

<script>
import { stringifyExpression } from '@vue/compiler-core';

export default {
    name: 'StockDetails',
    props: {
        stockName: {
            type: String
        },
        stockPrice: {
            type: String
        },
        stockTicker: {
            type: String
        },
        id: {
            type: Number,
        }
    },
    setup(props) {
        return {props}
    }
}
</script>

<style>
.stock-information-container {
    /* width: 100%; */
    height: 50px;
    display: flex;
    flex-direction: row;
    background: grey;
    align-items: center;
    justify-content: space-evenly;
    font-weight: 600;
    font-size: 18px;
}
</style>