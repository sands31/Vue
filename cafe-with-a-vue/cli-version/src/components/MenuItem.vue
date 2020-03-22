<template>       
    <div class="menu-item">
        <img
        class="menu-item__image"
        :src="item.image.source"
        :alt="item.image.alt"
        />
        <div>
        <h3>{{ item.name }}</h3>
        <p v-if="item.inStock">In Stock</p>
        <p v-else>Out of Stock</p>
        <div>
            <label for="add-item-quantity"
            >Quantity: {{ item.quantity }}</label
            >
            <input
            v-model.number="item.quantity"
            id="add-item-quantity"
            type="number"
            />
            <button @click="addToShoppingCart(item.quantity)">
            Add to Shopping Cart
            </button>
        </div>
        </div>
    </div>    
</template>

<script>
export default {
    name: 'MenuItem',
    props: {
        item: {
            name: String,
            image: {
                source: String,
                alt: String
            },
            inStock: Boolean,
            quantity: Number       
        }
    },
    methods: {
        addToShoppingCart(amount) {
            this.shoppingCart += amount
        }
  } 
}
</script>

<style>
  .menu-item {
    display: flex;
    width: 500px;
    justify-content: space-between;
    margin-bottom: 30px;
  }

  .menu-item__image {
    max-width: 300px;
  }
</style>