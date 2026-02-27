<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'

const navItems: NavigationMenuItem[] = [
  {
    label: 'Services',
    to: '/services',
    children: [
      {
        label: 'Consultancy Services',
        description: 'Planning, implementation and support for your technology journey.',
        icon: 'i-lucide-handshake',
        to: '/services/consultancy-services'
      },
      {
        label: 'Project Services',
        description: 'Strategy development, pre-sales and technology architecture.',
        icon: 'i-lucide-laptop',
        to: '/services/project-services'
      },
      {
        label: 'Outplacement Services',
        description: 'Certified professionals for short, mid or long-term assignments.',
        icon: 'i-lucide-briefcase',
        to: '/services/outplacement-services'
      }
    ]
  },
  {
    label: 'Products',
    to: '/products',
    children: [
      {
        label: 'Gesume',
        description: 'Smart resume and professional profile management platform.',
        icon: 'i-lucide-file-text',
        to: '/products/gesume'
      }
    ]
  },
  {
    label: 'Specializations',
    to: '/specializations'
  },
  {
    label: 'Industries',
    to: '/industries'
  },
  {
    label: 'Contact',
    to: '/contact'
  }
]
</script>

<template>
  <UNavigationMenu
    :items="navItems"
    color="neutral"
    variant="link"
    class="hidden lg:flex"
    :ui="{ link: 'font-medium text-sm' }"
  />
</template>
