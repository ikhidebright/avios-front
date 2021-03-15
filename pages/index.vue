<template>
  <div class="container">
    <br />
    <br />
    <p v-if="products.length < 1">Loading...</p>
    <vs-row v-else>
      <vs-col
        v-for="(product, index) in products"
        :key="index"
        vs-type="flex"
        vs-justify="center"
        vs-align="center"
        w="3"
      >
        <ProductCard :product="product" />
      </vs-col>
    </vs-row>
  </div>
</template>

<script>
import axios from "axios";

export default {
  async mounted() {
    const { data } = await axios.get(
      "https://avois.herokuapp.com/api/v1/products"
    );
    this.products = data;
    console.log(data);
  },
  data() {
    return {
      products: []
    };
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
}
</style>
