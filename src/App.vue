<template>
  <div id="app">
    <product-list-one></product-list-one>
    <product-list-two></product-list-two>
  </div>
</template>

<script>
import ProductListOne from "./components/ProductListOne.vue";
import ProductListTwo from "./components/ProductListTwo.vue";

export default {
  name: "App",
  data() {
    return {
      products: [],
    };
  },
  components: {
    "product-list-one": ProductListOne,
    "product-list-two": ProductListTwo,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Cascadia Code;
  color: #555;
}
</style>
