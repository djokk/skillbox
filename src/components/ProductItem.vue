<template>
  <li class="catalog__item">
    <a
      class="catalog__pic"
      href="#"
      @click.prevent="gotoPage('product', {id: product.id})"
    >
      <img :src="product.image" :alt="product.title" />
    </a>
    <h3 class="catalog__title">
      <a href="#">{{ product.title }}</a>
    </h3>
    <span class="catalog__price">
      {{ product.price | numberFormat}} ₽
    </span>

    <ProductColors :colors="product.colors" :current-color.sync="productCurrentColor"/>
  </li>
</template>

<script>
import gotoPage from '@/helpers/gotoPage';
import numberFormat from '@/helpers/numberFormat';
import ProductColors from './ProductColors.vue';

export default {
  name: 'ProductItem',
  data() {
    return {
      productCurrentColor: this.product.colors[0].code,
    };
  },
  props: ['product', 'currentColor'],
  components: {
    ProductColors,
  },
  filters: {
    numberFormat,
  },
  // computed: {
  //   colorData() {
  //     return colorData;
  //   },
  // },
  methods: {
    gotoPage,
  },
};
</script>
