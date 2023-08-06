<script setup>
import api from "@/api.js";
import Products from "@/components/Products4Column.vue";
import {onMounted, ref} from "vue";
import Loader from "@/components/UI/Loader.vue";

onMounted(async () => {
  popularProducts.value = await api.getPopularProducts()
  loading.value = false;
})

const popularProducts = ref([]);
const loading = ref(true)

</script>

<template>
  <Loader v-if="loading"/>
  <Products :products="popularProducts" v-else/>
</template>

<style scoped lang="scss">

</style>