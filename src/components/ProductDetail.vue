<script setup>
import {ref} from "vue";
import Button from "@/components/UI/Button.vue";
import {useCartStore} from "@/store/cart.js";

const quantity = ref(1);
const cartStore = useCartStore()

const props = defineProps({
  product: {
    type: Object,
    default: () => {
    },
    required: true,
  }
})

const changeQuantity=(type)=>{
  if(type === 'minus'){
    quantity.value===1 ? quantity.value = 1 : quantity.value--
  }
  if(type === 'plus'){
    quantity.value===3 ? quantity.value = 3 : quantity.value++
  }
}

</script>

<template>
  <div class="product">
    <div>
      <img :src="product.image" :alt="product.name">
    </div>
    <div>
      <h2 class="product-name">{{ product.name }}</h2>
      <span class="product-price">£ {{ product.price }}</span>
      <div class="product-block product-description">
        <span class="product-block-title">Product description</span>
        <div v-html="product.description"></div>
      </div>
      <div class="product-block">
        <span class="product-block-title">Dimensions</span>
        <span class="product-param" v-for="(param, index) of product.params"
              key="index">{{ param.title }}: {{ param.value }}</span>
      </div>
      <div class="product-block">
        <span class="product-block-title">Quantity</span>
        <div class="product-quantity">
          <span class="product-quantity-symbol" @click="changeQuantity('minus')">-</span>
          <span class="product-quantity-value">{{ quantity }}</span>
          <span class="product-quantity-symbol" @click="changeQuantity('plus')">+</span>
        </div>
      </div>
      <Button @click="cartStore.addToCart(product, quantity)">Add to Cart</Button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.product {
  background: #F9F9F9;
  padding: 50px 80px;
  display: grid;
  align-items: center;
  grid-template-columns: 1fr 500px;
  column-gap: 65px;
  margin-bottom: 65px;

  &-name {
    margin: 0 0 16px 0;
    font-size: 36px;
  }

  &-price {
    display: block;
    font-size: 24px;
    margin-bottom: 28px;
  }

  &-block {
    margin-bottom: 40px;

    &-title {
      display: block;
      margin-bottom: 14px;
    }
  }

  &-description {
    border-top: 1px solid var(--border-grey);
    padding-top: 24px;
  }

  &-param {
    display: block;
  }

  &-quantity {
    background: #ffffff;
    width: 122px;
    height: 46px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 16px;

    &-symbol {
      color: var(--lightgray);
      cursor: pointer;
    }
  }
}
</style>