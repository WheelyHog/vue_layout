<script setup>
import HeroInformation from "@/components/HeroInformation.vue";
</script>

<template>
  <div class="hero">
      <HeroInformation title="Luxury homeware for people who love timeless design quality" description="Shop the new Spring 2022 collection today" link="#" colorLink="lightgray"/>

    </div>
</template>

<style scoped lang="scss">
.hero {
  background-image: url('/img/hero.png');
  background-size: cover;
  height: 704px;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding-right: 80px;
@media (max-width: 768px) {
  height: auto;
  background: transparent;
  padding-right: 0;
  display: block;
}
  &-img {
    max-width: 100%;
  }
}
</style>