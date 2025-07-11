<script setup lang="ts">
import hotProducts from "~/assets/json/hotProducts.json";
import newProducts from "~/assets/json/newProducts.json";

const bannerItems = [
  "AK-74M with ZenitCo Sport-Kit",
  "AK-105 with ZenitCo Leader-Kit",
  "AK-103 with Midwest AK Alpha Kit",
  "AK-104",
];
</script>

<template>
  <UContainer class="py-8">
    <section>
      <UCarousel
        v-slot="{ item }"
        arrows
        dots
        loop
        autoplay
        :items="bannerItems"
      >
        <div
          class="bg-blue-700 h-64 flex justify-center items-center rounded-xl"
        >
          <span>{{ item }}</span>
        </div>
      </UCarousel>
    </section>

    <section class="mt-8">
      <div class="mb-6">
        <h2 class="text-2xl font-bold">지금 많이 구매하는 상품</h2>
      </div>

      <div class="grid grid-cols-4 gap-y-8 place-items-center items-stretch">
        <ProductCard
          v-for="product of hotProducts"
          :key="product.name"
          :name="product.name"
          :price="product.price"
          :availability="product.availability"
        />
      </div>
    </section>

    <section class="mt-8">
      <div class="mb-6">
        <h2 class="text-2xl font-bold">새로 들어온 상품</h2>
      </div>

      <div class="grid grid-cols-4 gap-y-8 place-items-center items-stretch">
        <ProductCard
          v-for="product of newProducts"
          :key="product.name"
          :name="product.name"
          :price="product.price"
          :availability="product.availability"
        />
      </div>
    </section>
  </UContainer>
</template>
