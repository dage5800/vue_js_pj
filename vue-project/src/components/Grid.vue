<script setup>
//WjFlexGrid、WjFlexGridColumnコンポーネントをインポートします。
import { WjFlexGrid, WjFlexGridColumn } from '@mescius/wijmo.vue2.grid'
import { registerGrid } from "@mescius/wijmo.vue2.grid"
import { registerGridTransposed } from "@mescius/wijmo.vue2.grid.transposed"
//日本語化カルチャをインポートします。
import '@mescius/wijmo.cultures/wijmo.culture.ja'
//グリッド用のデータを定義します。
const gridData = [
  { no: 1, product: 'TEST48970 L2SSP', date: '2024/10/19', amount: 6000 },
  { no: 2, product: 'TEST48970', date: '2022/10/19', amount: 14500 },
  { no: 3, product: 'TEST48970 L21PART', date: '2022/10/19', amount: 4000 },
  { no: 4, product: 'TEST', date: '2022/10/19', amount: 8000 }
]
</script>

<template>
  <wj-flex-grid :itemsSource="gridData">
    <wj-flex-grid-column header="NO." binding="no" :width="60"></wj-flex-grid-column>
    <wj-flex-grid-column header="NAME" binding="product" :width="200"></wj-flex-grid-column>
    <wj-flex-grid-column header="DATE" binding="date" :width="120"></wj-flex-grid-column>
    <wj-flex-grid-column header="AMOUNT" binding="amount" :width="100"></wj-flex-grid-column>
  </wj-flex-grid>
  <wj-transposed-grid :itemsSource="gridData">
  </wj-transposed-grid>
</template>


<style>
/* Wijmoのスタイルファイルをインポートします */
@import '@mescius/wijmo.styles/wijmo.css';
</style>