<script setup lang="ts">
useSeoMeta({ title: 'Project Services — Yopaat', description: 'Yopaat project services: strategy development, pre-sales and technology architecture.' })
</script>

<template>
  <UContainer class="py-20 min-h-[60vh] flex flex-col items-center justify-center text-center">
    <div class="w-16 h-16 rounded-2xl bg-primary/10 flex items-center justify-center mx-auto mb-6">
      <UIcon name="i-lucide-laptop" class="w-8 h-8 text-primary" />
    </div>
    <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-3">Services</p>
    <h1 class="text-4xl font-bold mb-4">Project Services</h1>
    <p class="text-muted text-lg max-w-md">
      Strategy development, pre-sales, technology architecture and best practices. Content coming soon.
    </p>
    <UButton to="/services" variant="link" color="neutral" class="mt-8" leading-icon="i-lucide-arrow-left">
      Back to Services
    </UButton>
  </UContainer>
</template>
