<script setup>
import Product from '../components/ProductItem.vue'
defineProps({
  products: Array
})
const updateHandler = (val) => {
  console.log(val)
}
</script>

<template>
  <div class="row product-group flex">
    <template v-for="(product, index) in products" :key="index">
      <Product :product="product" @update="updateHandler" />
    </template>
  </div>
</template>
