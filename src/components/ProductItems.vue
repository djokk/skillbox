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

    <ProductColor :colors.sync="product.colors" :current-color.sync="currentColor"/>
  </li>
</template>

<script>
import gotoPage from '@/helpers/gotoPage';
import numberFormat from '@/helpers/numberFormat';
import ProductColor from './ProductColor.vue';

export default {
  name: 'ProductItem',
  data() {
    return {
    };
  },
  props: ['product', 'currentColor'],
  components: {
    ProductColor,
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
