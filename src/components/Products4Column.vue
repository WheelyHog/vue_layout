<script setup>
import Product from "@/components/Product.vue";
import {ref} from "vue";
import UIButton from "@/components/UI/Button.vue";

const props = defineProps({
  products:{
    required: true,
  }
})

</script>

<template>
  <div class="products-container">

    <div class="products">
      <Product v-for="product of products" :key="product.id" :img="product.img" :title="product.title"
               :price="product.price"/>
    </div>
    <div class="products-link">
      <UIButton color="lightgray" type="link" to="/">View Collection</UIButton>
    </div>

  </div>


</template>

<style scoped lang="scss">
.products {
  padding: 0 80px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  column-gap: 20px;
  margin-bottom: 64px;
  @media (max-width: 1024px) {
    grid-template-columns: repeat(2, 1fr);
    grid-row-gap: 20px;
  }
  @media (max-width: 768px) {
    grid-template-columns:1fr;

  }

  &-container {
    margin-bottom: 56px;
  }

  &-link {
    text-align: center;

    &:hover {
      text-decoration: underline;
    }
  }
}
</style>