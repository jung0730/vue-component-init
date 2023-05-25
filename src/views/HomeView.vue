<script setup>
import { ref } from 'vue'
import Products from '../components/ProductList.vue'
import Header from '../components/BaseHeader.vue'
import Footer from '../components/BaseFooter.vue'
import rawProducts from '../raw/products.js'

const products = ref(rawProducts)
</script>

<template>
  <Header />
  <Products :products="products" />
  <Footer />
</template>
