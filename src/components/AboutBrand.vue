<script setup>
import {ref} from "vue";

const aboutBrands = [
  {
    id: 1,
    img: '/svg/a-brand1.svg',
    title: 'Next day as standard',
    description: 'Order before 3pm and get your order the next day as standard'
  },
  {
    id: 2,
    img: '/svg/a-brand2.svg',
    title: 'Made by true artisans',
    description: 'Handmade crafted goods made with real passion and craftmanship'
  },
  {
    id: 3,
    img: '/svg/a-brand3.svg',
    title: 'Unbeatable prices',
    description: 'For our materials and quality you won’t find better prices anywhere'
  },
  {
    id: 4,
    img: '/svg/a-brand4.svg',
    title: 'Recycled packaging',
    description: 'We use 100% recycled to ensure our footprint is more manageable'
  },

]
</script>

<template>
  <div class="about-brand">
    <h3 class="about-brand__title">What makes our brand different</h3>
    <div class="about-brand-elements">
      <div class="about-brand-element" v-for="element of aboutBrands" :key="element.id">
        <img
            :src="element.img"
            :alt="element.title" class="about-brand-element__img">
        <h4 class="about-brand-element__title">{{ element.title }}</h4>
        <span class="about-brand-element__description">{{ element.description }}</span>
      </div>
    </div>
  </div>

</template>

<style scoped lang="scss">
.about-brand {
  padding: 80px 80px 130px 80px;
@media (max-width: 768px) {
  padding: 48px 24px;
}
  &__title {
    font-size: 24px;
    text-align: center;
    margin: 0 0 84px 0;
    @media (max-width: 768px) {
      text-align: left;
      font-size: 20px;
      margin-bottom: 36px;
    }
  }

  &-elements {
    display: grid;
    grid-template-columns: repeat(4, 210px);
    justify-content: space-between;
    @media (max-width: 1024px) {
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
    }
    @media (max-width: 768px) {
      grid-template-columns: 1fr;
    }
  }

  &-element {
background: #fdfdfd;
    padding: 48px;
@media (max-width: 768px) {
  padding: 36px 24px;
}
    &__img {
      display: block;
      margin-bottom: 12px;
    }

    &__title {
      margin: 0 0 12px 0;
      color: var(--primary);
      font-size: 20px;
    }

    &__description {
      font-size: 16px;
    }
  }
}
</style>