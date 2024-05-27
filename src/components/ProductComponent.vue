<template>
  <div class="product-container">
    <h2>Product List</h2>
    <div class="product" v-for="product in products" :key="product.id">
      <h3>{{ product.name }}</h3>
      <p>{{ product.description }}</p>
      <add-to-cart-button :product="product" @product-added="emitProduct"></add-to-cart-button>
    </div>
    <slot></slot>
  </div>
</template>

<script>
import AddToCartButton from './AddToCartButton.vue'

export default {
  components: {
    AddToCartButton
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Laptop', description: 'A high performance laptop' },
        { id: 2, name: 'Smartphone', description: 'A new generation smartphone' }
      ]
    }
  },
  methods: {
    emitProduct(product) {
      this.$emit('product-added', product.name)
    }
  }
}
</script>

<style scoped>
.product-container {
  margin: 20px;
  background-color: #fff;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.product {
  margin-bottom: 15px;
}
</style>
