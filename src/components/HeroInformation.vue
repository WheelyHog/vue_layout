<script setup>
import UIButton from "@/components/UI/Button.vue";

const props = defineProps({
  title: {
    type: String,
    required: false
  },
  description: {
    type: String,
    required: false
  },
  link: {
    type: String,
    required: false
  },
  colorTitle: {
    type: String,
    default: ''
  },
  colorDescription: {
    type: String,
    default: '#5b5676'
  },
  background: {
    type: String,
    default: '#fff'
  },
  colorLink: {
    type: String,
    required: false
  },
  mobilePadding: {
    type: Boolean,
    default: false
  }
})
</script>

<template>

  <div class="hero-info" :style="{background: background}" :class="{'hero-info--mobile-padding':mobilePadding}">
    <div class="hero-info-text">
      <h2 class="hero-info__title" :style="{color: colorTitle}">{{ title }}</h2>
      <span class="hero-info__description" :style="{color: colorDescription}">{{ description }}</span>
    </div>
    <UIButton :color="colorLink || 'secondary'" type="link" to="/" :mobileFullWidth:="true">View Collection</UIButton>
<!--    <img src="/img/hero.png" alt="" class="hero-info&#45;&#45;image">-->
  </div>

</template>

<style scoped lang="scss">
.hero {

  &-info {
    background: #ffffff;
    max-width: 630px;
    padding: 50px 55px;
    min-height: 444px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;

    & a {
      align-self: center;
    }

    @media (max-width: 768px) {
      padding: 47px 0 32px 0;
      min-height: 0;
    }

    &--image {
      margin-top: 32px;
    }

    &-text {
      display: flex;
      flex-direction: column;
      gap: 20px;
      @media (max-width: 768px) {
        margin-bottom: 32px;
      }

      &-title {
        font-size: 32px;
        line-height: 44px;
      }

      &-description {
        font-size: 18px;
      }
      &--mobile-padding{
        @media (max-width: 768px) {
          padding: 36px 32px;
        }
      }
    }


  }
}
</style>