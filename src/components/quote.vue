<script setup>
import { ref, onMounted } from 'vue'
const props = defineProps(["quoteData"])
console.log("props length: ", props.quoteData.length);

const currentQuote = ref({ quote: '', author: '' })

const randomFun = () => {
  currentQuote.value = props.quoteData[Math.floor(Math.random() * (props.quoteData.length))]
  console.log("final value is : ", currentQuote.value)
}

onMounted(() => {
  randomFun();
});

</script>

<template>

  <div class="containerCust d-flex justify-content-center align-items-center ">
    <div class="w-100 p-4">
      <h2 class="align-center text-primary">Todays Quote</h2>
      <hr>
      <figure>
        <blockquote class="blockquote">
          <h3 class="">"{{ currentQuote.quote }}"</h3>
        </blockquote>
        <figcaption class="blockquote-footer mt-3">
          <cite title="Source Title">{{ currentQuote.author }}</cite>
        </figcaption>
        <div class="text-end"><button class="btn btn-success fw-bold" @click="randomFun">New Quote</button></div>
      </figure>
    </div>
  </div>


</template>

<style scoped>
.containerCust {
  height: 100vh;
  width: 60vw;
  margin: 0px auto;
}
</style>
