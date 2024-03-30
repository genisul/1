<template>
  <div>
    <input type="search" v-model="searchNameList" :value="products" />
    {{ products }}
  </div>

  <div>
    <!-- <div v-for="product in filterSearchProductList" :key="product.name">
        <div>{{ product.name }}</div>
        <div>{{ product.category }}</div>
      </div> -->
  </div>
  <button @click="console.log()">clock!</button>
</template>

<script setup lang="ts">
import { products } from '@/data/product'
import { ref } from 'vue'

const searchNameList = ref('')
// const test = ref([])

// const filterSearchProductList = computed(() => {
//   if (searchNameList.value) {
//     return test.value.filter((product) => searchNameList.value.includes(products))
//   }
// })
</script>

<style scoped></style>
