<script>
export default {
  name: 'MenuItem',
  props: ['addToShoppingCart', 'image', 'inStock', 'name', 'price', 'quantity'],
  computed: {
    generatedPrice() {
      const date = new Date().getDate()
       if (date % 2 === 0) {
         return (this.price * 0.9).toFixed(2)
       } else {
         return this.price
       }
    }
  },
  beforeMount() {
    
  }
}
</script>

<template>
  <div class="menu-item">
    <img class="menu-item__image" :src="image.source" :alt="image.alt" />
    <div>
      <h3>{{ name }}</h3>
      <p>Price: {{ generatedPrice }}</p>
      <p v-if="inStock">In Stock</p>
      <p v-else>Out of Stock</p>
      <div>
        <label for="add-item-quantity">Quantity: {{ quantity }}</label>
        <input v-model.number="quantity" id="add-item-quantity" type="number" />
        <button @click="addToShoppingCart(quantity)">
          Add to Shopping Cart
        </button>
      </div>
    </div>
  </div>
</template>

<style></style>
