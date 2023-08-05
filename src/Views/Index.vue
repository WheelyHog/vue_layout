<script setup>
import {onMounted} from "vue";
import api from "@/api.js";
import {ref} from "vue";

import Hero from "@/components/Hero.vue";
import AboutBrand from "@/components/AboutBrand.vue";
import Products from "@/components/Products4Column.vue";
import Ideas from "@/components/Ideas.vue";
import Subscribe from "@/components/Subscribe.vue";

const popularProducts = ref([]);

 onMounted(async ()=>{
  popularProducts.value = await api.getPopularProducts()
})

</script>

<template>
  <div>
    <Hero/>
    <AboutBrand/>
    <Products :products="popularProducts"/>
    <Ideas/>
    <Subscribe/>
  </div>
</template>

