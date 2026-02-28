<script setup lang="ts">
useSeoMeta({ title: 'Products — Yopaat', description: 'Yopaat products: discover Gésumé and other solutions.' })
</script>

<template>
  <UContainer class="py-20 min-h-[60vh] flex flex-col items-center justify-center text-center">
    <div class="w-16 h-16 rounded-2xl bg-primary/10 flex items-center justify-center mx-auto mb-6">
      <UIcon
        name="i-lucide-package"
        class="w-8 h-8 text-primary"
      />
    </div>
    <h1 class="text-4xl font-bold mb-4">
      Products
    </h1>
    <p class="text-muted text-lg max-w-md">
      Content coming soon. Discover our product portfolio.
    </p>
    <div class="mt-8">
      <UButton
        to="/products/gesume"
        variant="outline"
        color="neutral"
      >
        Gésumé
      </UButton>
    </div>
  </UContainer>
</template>
