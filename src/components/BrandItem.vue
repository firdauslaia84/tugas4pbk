<!-- src/components/BrandItem.vue -->
<template>
  <div class="brand-item">
    <h3 @click="toggleDetails">{{ brand.name }}</h3>
    <div v-if="showDetails">
      <slot></slot>
      <product-detail v-for="product in brand.products" :key="product.id" :product="product"></product-detail>
    </div>
  </div>
</template>

<script>
import ProductDetail from './ProductDetail.vue';

export default {
  components: {
    ProductDetail
  },
  props: ['brand'],
  data() {
    return {
      showDetails: false
    };
  },
  methods: {
    toggleDetails() {
      this.showDetails = !this.showDetails;
      this.$emit('brand-selected', this.brand);
    }
  }
};
</script>

<style scoped>
.brand-item {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px 0;
  cursor: pointer;
}
.brand-item:hover {
  background-color: #f0f0f0;
}
</style>
