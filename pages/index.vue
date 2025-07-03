<script setup lang="ts">
import hotProducts from "~/assets/json/hotProducts.json"
</script>

<template>
  <UContainer class="py-8">
    <section>
      <div class="mb-6">
        <h2 class="text-2xl font-bold">지금 많이 구매하는 상품</h2>
      </div>

      <div class="grid grid-cols-4 gap-y-8 place-items-center items-stretch">
        <ProductCard v-for="product of hotProducts" :key="product.name" :name="product.name" :price="product.price"
          :availability="product.availability" />
      </div>
    </section>

    <section class="mt-8">
      <div class="mb-6">
        <h2 class="text-2xl font-bold">재입고된 상품</h2>
      </div>

      <div class="grid grid-cols-4 gap-y-8 place-items-center items-stretch">
        <ProductCard v-for="product of hotProducts" :key="product.name" :name="product.name" :price="product.price"
          :availability="product.availability" />
      </div>
    </section>
  </UContainer>
</template>