<template>
  <div class="parent-container">
    <h1>Shopping Cart</h1>
    <p>Products added to cart:</p>
    <ul>
      <li v-for="(product, index) in cart" :key="index">{{ product }}</li>
    </ul>
    <product-component @product-added="handleProduct">
      <template v-slot:default>
        <p>Check out our latest products!</p>
      </template>
    </product-component>
  </div>
</template>

<script>
import ProductComponent from './ProductComponent.vue'

export default {
  components: {
    ProductComponent
  },
  data() {
    return {
      cart: []
    }
  },
  methods: {
    handleProduct(product) {
      this.cart.push(product)
    }
  }
}
</script>

<style scoped>
.parent-container {
  text-align: center;
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
</style>
