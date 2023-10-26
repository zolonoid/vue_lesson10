<template>
  <ProductDetails v-for="p in products"
                  :key="p.name"
                  :productName="p.name"
                  :price="p.price"
                  :available="p.available">
  </ProductDetails>
</template>

<script>
import ProductDetails from './components/ProductDetails.vue';

export default {
  name: 'App',
  components: {
    ProductDetails
  },
  data() {
    return {
      products: [
        {
          name: "Product 1",
          price: 25.75,
          available: true
        },
        {
          name: "Product 2",
          price: 50.25,
          available: false
        },
        {
          name: "Product 3",
          price: 15.99,
          available: true
        }
      ]
    };
  },
}
</script>

<style lang="scss">
#app {
  width: 200px;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>
