<script setup>
import {ref, onMounted} from "vue";
import {useRoute, useRouter} from "vue-router";
import api   from "@/api.js";
import ProductDetail from "@/components/ProductDetail.vue";
import AboutBrand from "@/components/AboutBrand.vue";
import Subscribe from "@/components/Subscribe.vue";
import PopularProducts from "@/components/PopularProducts.vue";


const  route=useRoute()
const router = useRouter()
const productId = ref('')
let currentProduct=ref({})

onMounted(async ()=>{
  productId.value = route.params.id
  currentProduct.value = await api.getProduct(productId.value)
})
</script>

<template>
<ProductDetail :product="currentProduct"/>
  <PopularProducts/>
  <AboutBrand/>
  <Subscribe/>
</template>

<style scoped lang="scss">

</style>