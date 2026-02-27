<script setup lang="ts">
useSeoMeta({ title: 'Gesume — Yopaat', description: 'Gesume: smart resume and professional profile management platform by Yopaat.' })
</script>

<template>
  <UContainer class="py-20 min-h-[60vh] flex flex-col items-center justify-center text-center">
    <div class="w-16 h-16 rounded-2xl bg-primary/10 flex items-center justify-center mx-auto mb-6">
      <UIcon name="i-lucide-file-text" class="w-8 h-8 text-primary" />
    </div>
    <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-3">Products</p>
    <h1 class="text-4xl font-bold mb-4">Gesume</h1>
    <p class="text-muted text-lg max-w-md">
      Smart resume and professional profile management platform. Content coming soon.
    </p>
    <UButton to="/products" variant="link" color="neutral" class="mt-8" leading-icon="i-lucide-arrow-left">
      Back to Products
    </UButton>
  </UContainer>
</template>
