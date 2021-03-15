<template>
  <vs-card>
    <template #title>
      <h3>{{ product.product_name }}</h3>
    </template>
    <template #img>
      <img
        :src="
          product.product_varieties.length > 0
            ? product.product_varieties[0].images[0].location
            : ''
        "
        :alt="product.product_name"
      />
    </template>
    <template #text>
      <p>
        {{ product.product_description }}
      </p>
    </template>
    <template #interactions>
      <vs-button class="btn-chat" shadow primary>
        <span class="span">
          Add to cart
        </span>
      </vs-button>
    </template>
  </vs-card>
</template>

<script>
export default {
  props: {
    product: {
      type: Object
    }
  }
};
</script>
