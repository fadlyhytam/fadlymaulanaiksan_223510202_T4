<template>
  <button class="add-to-cart-button" @click="addToCart">Add to Cart</button>
</template>

<script>
export default {
  props: ['product'],
  methods: {
    addToCart() {
      this.$emit('product-added', this.product)
    }
  }
}
</script>

<style scoped>
.add-to-cart-button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}
.add-to-cart-button:hover {
  background-color: #0056b3;
}
</style>
