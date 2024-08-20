<script setup>
import quote from './components/quote.vue'
import dummyData from './dummyData.js'

const quoteData = dummyData
</script>

<template>
  <quote :quoteData="quoteData"></quote>
</template>

<style scoped></style>
