<!-- <script>
// import NavigationView from './components/NavigationView.vue'
// import NavigationPinia from './components/NavPinia.vue'

export default {
components: { }
}
</script>

<template>
  <div>
    <RouterLink to="/pinia/lession1">   One</RouterLink>
    <RouterView />
    </div>
</template> -->
<script setup>
import TheHeader from "@/components/TheHeader.vue";
// import ProductCard from "@/components/ProductCard.vue";
import AppButton from "@/components/AppButton.vue";
import products from "./data/products.json";
import AppCountInput from "@/components/AppCountInput.vue"
import { useProductStore } from "./stores/ProductStore";
useProductStore()
</script>

<template>
  <div class="container">
    <TheHeader />
<ul>
  <li v-for="(product,index) in products" :key="index" class="card">
    <img :src="`/images/${product.image}`" class="mb-3" width="300" />
    <div>
      {{ product.name }} - <span class="text-green-500">${{product.price}}</span>
      <div class="text-center m-4">
        <AppCountInput v-model="count" />
      </div>
      <AppButton
        class="primary">Add to Cart</AppButton>
    </div>
  </li>
</ul>
   
    <br />

  </div>
</template>