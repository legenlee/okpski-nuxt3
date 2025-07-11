<script setup lang="ts">
import navigationMenuItems from "~/assets/json/navigationMenuItems.json";
</script>

<template>
  <div>
    <UContainer class="flex justify-end my-1 gap-4">
      <UButton
        icon="i-lucide-shopping-cart"
        variant="link"
        color="neutral"
        size="xl"
      />
    </UContainer>

    <USeparator />

    <UContainer class="flex py-4">
      <div class="w-1/4 flex items-center gap-4">
        <h1 class="text-4xl font-bold">Okpski</h1>
      </div>

      <div class="w-3/4 flex items-center">
        <UInput
          class="w-full"
          size="xl"
          placeholder="TWS Dog Leg Railed Dust Cover ..."
        >
          <template #trailing>
            <UButton
              color="neutral"
              variant="link"
              size="xl"
              icon="i-lucide-search"
            />
          </template>
        </UInput>
      </div>
    </UContainer>

    <UContainer>
      <UNavigationMenu :items="navigationMenuItems" />
    </UContainer>
  </div>
</template>
