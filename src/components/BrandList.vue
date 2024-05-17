<!-- src/components/BrandList.vue -->
<template>
  <div class="brand-list">
    <h2>Daftar Merk HP</h2>
    <brand-item
      v-for="brand in brands"
      :key="brand.id"
      :brand="brand"
      @brand-selected="handleBrandSelected"
    >
      <template v-slot>
        <p>Ini adalah detail untuk {{ brand.name }}</p>
      </template>
    </brand-item>
    <p v-if="selectedBrand">
      Merk terpilih: {{ selectedBrand.name }}
    </p>
  </div>
</template>

<script>
import BrandItem from './BrandItem.vue';

export default {
  components: {
    BrandItem
  },
  data() {
    return {
      brands: [
        { id: 1, name: 'Apple', products: [
            { id: 1, name: 'iPhone 12', description: 'Layar 6.1 inci, A14 Bionic', price: 'Rp 10.000.000' },
            { id: 2, name: 'iPhone 13', description: 'Layar 6.1 inci, A15 Bionic', price: 'Rp 14.000.000' }
          ]
        },
        { id: 2, name: 'Samsung', products: [
            { id: 1, name: 'Galaxy S21', description: 'Layar 6.2 inci, Exynos 2100', price: 'Rp 12.000.000' },
            { id: 2, name: 'Galaxy Note 20', description: 'Layar 6.7 inci, Exynos 990', price: 'Rp 13.000.000' }
          ]
        },
        { id: 3, name: 'Xiaomi', products: [
            { id: 1, name: 'Mi 11', description: 'Layar 6.81 inci, Snapdragon 888', price: 'Rp 9.000.000' },
            { id: 2, name: 'Redmi Note 10', description: 'Layar 6.43 inci, Snapdragon 678', price: 'Rp 3.000.000' }
          ]
        },
        { id: 4, name: 'OnePlus', products: [
            { id: 1, name: 'OnePlus 9', description: 'Layar 6.55 inci, Snapdragon 888', price: 'Rp 10.000.000' },
            { id: 2, name: 'OnePlus 8T', description: 'Layar 6.55 inci, Snapdragon 865', price: 'Rp 8.000.000' }
          ]
        },
      ],
      selectedBrand: null,
    };
  },
  methods: {
    handleBrandSelected(brand) {
      this.selectedBrand = brand;
    }
  }
};
</script>

<style scoped>
.brand-list {
  width: 300px;
  margin: 0 auto;
}
</style>
