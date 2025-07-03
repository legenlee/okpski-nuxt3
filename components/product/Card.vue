<script setup lang="ts">
interface ProductCardProps {
  name: string;
  price: number | string;
  availability: string;
}

const props = defineProps<ProductCardProps>();

const cardUIClassNames = {
  body: "p-0 sm:p-0 h-full flex flex-col",
};

const availabilityColor = computed(() => {
  switch (props.availability) {
    case "in-stock":
      return "primary";

    case "out-of-stock":
    default:
      return "neutral";
  }
});

const availabilityText = computed(() => {
  switch (props.availability) {
    case "in-stock":
      return "재고 있음";

    case "out-of-stock":
    default:
      return "품절";
  }
});

const priceText = computed(() => {
  switch (typeof props.price) {
    case "string":
      return parseInt(props.price).toLocaleString();

    case "number":
    default:
      return props.price.toLocaleString();
  }
});
</script>

<template>
  <UCard class="w-full max-w-64" :ui="cardUIClassNames">
    <div class="h-32 flex justify-center items-center">
      <div>이미지</div>
    </div>

    <USeparator />

    <div class="px-4 py-2 mb-auto">
      <h3 class="text-xl font-bold">{{ props.name }}</h3>

      <div class="flex mt-2 items-center justify-between">
        <div>
          <UChip class="mr-2" standalone inset :color="availabilityColor" />
          <span class="text-base">{{ availabilityText }}</span>
        </div>

        <span class="text-lg font-bold">{{ priceText }} \</span>
      </div>
    </div>

    <USeparator />

    <div class="px-4 py-2 text-right">
      <UButton icon="i-lucide-star" variant="outline" />
      <UButton class="ml-2" icon="i-lucide-shopping-cart" />
    </div>
  </UCard>
</template>
