<script setup lang="ts">
useSeoMeta({ title: 'Services — Yopaat', description: 'Explore Yopaat services: Consultancy, Project, and Outplacement Services.' })
</script>

<template>
  <UContainer class="py-20 min-h-[60vh] flex flex-col items-center justify-center text-center">
    <div class="w-16 h-16 rounded-2xl bg-primary/10 flex items-center justify-center mx-auto mb-6">
      <UIcon name="i-lucide-layers" class="w-8 h-8 text-primary" />
    </div>
    <h1 class="text-4xl font-bold mb-4">Services</h1>
    <p class="text-muted text-lg max-w-md">
      Content coming soon. Explore our consultancy, project, and outplacement services.
    </p>
    <div class="flex flex-wrap gap-4 mt-8 justify-center">
      <UButton to="/services/consultancy-services" variant="outline" color="neutral">Consultancy Services</UButton>
      <UButton to="/services/project-services" variant="outline" color="neutral">Project Services</UButton>
      <UButton to="/services/outplacement-services" variant="outline" color="neutral">Outplacement Services</UButton>
    </div>
  </UContainer>
</template>
