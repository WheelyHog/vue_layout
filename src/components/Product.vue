<script setup>
const props = defineProps({
  img: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  price: {
    type: Number,
    required: true
  },

})
</script>

<template>
  <div class="product">
    <router-link to="/">
      <img :src="img" :alt="title" class="product-image">
    </router-link>
    <router-link to="/" class="product-name">{{ title }}</router-link>
    <span class="product-price"> £{{ price }}</span>
  </div>
</template>

<style scoped lang="scss">
.product {
  &-image {
    display: block;
    margin-bottom: 24px;
    object-fit: cover;
  }

  &-name {
    display: block;
    color: var(--primary);
    font-size: 20px;
    line-height: 28px;
    margin-bottom: 8px;
    text-decoration: none;
    @media (max-width: 768px) {
      font-size: 16px;
    }
    &:hover{
      text-decoration: underline;
    }
  }
  &-price{
    font-size: 18px;
    @media (max-width: 768px) {
      font-size: 16px;
    }
  }
}
</style>