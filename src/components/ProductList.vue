<template>
  <ul class="catalog__list">
    <ProductItems
      v-for="product in products"
      :key="product.id"
      :product="product"
    />
  </ul>
</template>

<script>
import ProductItems from './ProductItems.vue';

export default {
  name: 'ProductList',
  props: ['products'],
  data() {
    return {
    };
  },
  components: {
    ProductItems,
  },
};
</script>
