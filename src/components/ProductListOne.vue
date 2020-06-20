<template>
  <div id="product-list-one">
    <h2>Product List One</h2>
    <ul>
      <li v-for="(product, index) in saleProducts" :key="index">
        <span class="name">{{ product.name }}</span>
        <span class="price">Rs.{{ product.price }}</span>
      </li>
    </ul>
    <button @click="reducePrice(4)" class="reducePrice">
      Reduce Price
    </button>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "ProductListOne",
  computed: {
    products() {
      return this.$store.state.products;
    },
    // saleProducts() {
    //   return this.$store.getters.saleProducts;
    // },
    ...mapGetters(["saleProducts"]),
  },
  methods: {
    // reducePrice(amount) {
    //   this.$store.dispatch("reducePriceActionsStore", amount);
    // },
    ...mapActions({
      reducePrice: "reducePriceActionsStore",
    }),
  },
};
</script>

<style scoped>
#product-list-one {
  background: #fff8b1;
  box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
  margin-bottom: 30px;
  padding: 10px 20px;
}
#product-list-one ul {
  padding: 0;
}
#product-list-one li {
  display: inline-block;
  margin-right: 10px;
  margin-top: 10px;
  padding: 20px;
  background: rgba(255, 255, 255, 0.7);
}
.price {
  font-weight: bold;
  color: #e8800c;
  margin-left: 10px;
}
.reducePrice {
  margin-top: 10px;
}
</style>
