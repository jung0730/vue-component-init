<script setup>
import { ref } from 'vue'
defineProps({
  product: Object
})
const emit = defineEmits(['update'])
const quantity = ref(1)
</script>
<template>
  <div class="product product-view">
    <a class="quickview" href="javascript:;">
      <img class="thumbnail" alt="商品圖" :src="product.imageUrl" />
    </a>
    <div class="content">
      <h1 class="title">
        <a class="quickview" href="javascript:;">{{ product.title }}</a>
      </h1>
      <div class="type">
        <span class="label">{{ product.specName }}</span>
        <span class="name">{{ product.specValue }}</span>
      </div>
      <div class="price ch">
        <del class="fn-sm">{{ product.originalPrice }}</del>
        <b class="fn-md">{{ product.discountPrice }}</b>
      </div>
      <div class="action-block">
        <div class="number-group">
          <button class="number-less">
            <i class="icon icon-minus"></i>
          </button>
          <input
            class="number-view"
            type="number"
            v-model.number="quantity"
            @change="emit('update', quantity)"
          />
          <button class="number-plus">
            <i class="icon icon-plus"></i>
          </button>
        </div>
        <a>加入購物車</a>
      </div>
    </div>
  </div>
</template>
