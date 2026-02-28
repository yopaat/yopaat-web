<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'

useHead({
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' },
    { name: 'robots', content: 'index, follow' },
    { name: 'theme-color', content: '#1e40af' }
  ],
  link: [
    { rel: 'icon', href: '/favicon.png' },
    { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
    { rel: 'preconnect', href: 'https://fonts.gstatic.com', crossorigin: '' }
  ],
  htmlAttrs: { lang: 'en' }
})

const title = 'Yopaat - Technology & Management Services'
const description
  = 'Yopaat is a cross-industry, cross-disciplinary B2B services company with a focus on technology and management services in Information & Communication Technologies.'

useSeoMeta({
  title,
  description,
  ogTitle: title,
  ogDescription: description,
  ogImage: 'https://yopaat.com/yopaat-logo.png',
  ogType: 'website',
  ogSiteName: 'Yopaat',
  twitterCard: 'summary_large_image',
  twitterTitle: title,
  twitterDescription: description,
  twitterImage: 'https://yopaat.com/yopaat-logo.png',
  twitterSite: '@yopaat'
})

const mobileNavItems: NavigationMenuItem[] = [
  {
    label: 'Services',
    to: '/services',
    defaultOpen: false,
    children: [
      { label: 'Consultancy Services', to: '/services/consultancy-services', icon: 'i-lucide-handshake' },
      { label: 'Project Services', to: '/services/project-services', icon: 'i-lucide-laptop' },
      { label: 'Outplacement Services', to: '/services/outplacement-services', icon: 'i-lucide-briefcase' }
    ]
  },
  {
    label: 'Products',
    to: '/products',
    defaultOpen: false,
    children: [
      { label: 'Gésumé', to: '/products/gesume', icon: 'i-lucide-file-text' }
    ]
  },
  { label: 'Specializations', to: '/specializations', icon: 'i-lucide-star' },
  { label: 'Industries', to: '/industries', icon: 'i-lucide-building-2' },
  { label: 'Contact', to: '/contact', icon: 'i-lucide-mail' }
]
</script>

<template>
  <UApp>
    <UHeader
      :toggle="{ icon: 'i-lucide-menu', color: 'neutral', variant: 'ghost' }"
    >
      <template #left>
        <NuxtLink
          to="/"
          class="flex items-center shrink-0"
          aria-label="Yopaat Home"
        >
          <AppLogo class="w-auto h-7! shrink-0" />
        </NuxtLink>
      </template>

      <!-- Desktop nav — center slot -->
      <template #default>
        <TemplateMenu />
      </template>

      <template #right>
        <UColorModeButton />
      </template>

      <!-- Mobile nav — UHeader's built-in content slot triggers with the toggle button -->
      <template #content>
        <UNavigationMenu
          :items="mobileNavItems"
          orientation="vertical"
          class="w-full px-2 py-4"
          color="neutral"
          variant="pill"
        />
      </template>
    </UHeader>

    <UMain>
      <NuxtPage />
    </UMain>

    <UFooter>
      <template #left>
        <div class="flex flex-col gap-1">
          <NuxtLink
            to="/"
            class="flex items-center"
            aria-label="Yopaat Home"
          >
            <AppLogo class="w-auto h-5! opacity-80 hover:opacity-100 transition-opacity" />
          </NuxtLink>
          <p class="text-xs text-muted mt-1">
            Technology & Management Services · © Yopaat {{ new Date().getFullYear() }}
          </p>
        </div>
      </template>

      <template #right>
        <nav class="flex flex-wrap gap-x-6 gap-y-2 text-sm text-muted">
          <NuxtLink
            to="/services"
            class="hover:text-foreground transition-colors"
          >Services</NuxtLink>
          <NuxtLink
            to="/products"
            class="hover:text-foreground transition-colors"
          >Products</NuxtLink>
          <NuxtLink
            to="/specializations"
            class="hover:text-foreground transition-colors"
          >Specializations</NuxtLink>
          <NuxtLink
            to="/industries"
            class="hover:text-foreground transition-colors"
          >Industries</NuxtLink>
          <NuxtLink
            to="/contact"
            class="hover:text-foreground transition-colors"
          >Contact</NuxtLink>
        </nav>
      </template>
    </UFooter>
  </UApp>
</template>
