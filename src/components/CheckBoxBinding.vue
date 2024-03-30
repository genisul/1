<template>
  <div class="container">
    <div>
      <div v-for="category in categoryList" :key="category">
        <input type="checkbox" v-model="selectedCategoryList" :value="category" />
        {{ category }}
      </div>
    </div>
    <div>
      <div v-for="product in filteredProductList" :key="product.name">
        <div>{{ product.name }}</div>
        <div>{{ product.category }}</div>
      </div>
    </div>
    <button @click="console.log(selectedCategoryList)">click</button>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import { products } from '@/data/product'
import { categoryList } from '@/data/category'

const selectedCategoryList = ref<string[]>([])

// 카테고리 리스트 값에서 선택한 상품카테고리가 있으면 true인값만 남김.
const filteredProductList = computed(() => {
  return products.filter((product) => selectedCategoryList.value.includes(product.category))
})
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  flex-direction: column;
  gap: 15px;
}
</style>
@/data/product
