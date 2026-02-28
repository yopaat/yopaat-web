<script setup lang="ts">
useSeoMeta({
  title: 'Outplacement Services — Yopaat',
  description: 'Yopaat provides experienced, certified professionals on short-, mid- and long-term assignments as required by clients.'
})

const specializations = [
  { icon: 'i-lucide-network', text: 'Enterprise Architecture, Technical & Solution Architecture' },
  { icon: 'i-lucide-refresh-cw', text: 'Digital Transformation Planning & Implementation' },
  { icon: 'i-lucide-server', text: 'IT Engineering (including Data-Centers, Infrastructure, Cloud and Networking)' },
  { icon: 'i-lucide-shield-check', text: 'Cybersecurity Auditing & Engineering' },
  { icon: 'i-lucide-database', text: 'Database Administration, Data Management, Data Science' },
  { icon: 'i-lucide-code-2', text: 'Software Development (Embedded, Web Full-Stack, Robotic Process Automation, Blockchain, Internet of Things)' },
  { icon: 'i-lucide-git-merge', text: 'DevOps Engineering' },
  { icon: 'i-lucide-megaphone', text: 'Digital Marketing & Social Media Specialization' }
]

onMounted(() => {
  const observer = new IntersectionObserver(
    entries => entries.forEach((el) => {
      if (el.isIntersecting) { el.target.classList.add('revealed'); observer.unobserve(el.target) }
    }),
    { threshold: 0.1 }
  )
  document.querySelectorAll('.scroll-reveal').forEach(el => observer.observe(el))
})
</script>

<template>
  <div>
    <!-- ── HERO ─────────────────────────────────────────────── -->
    <section class="relative py-24 overflow-hidden">
      <div class="absolute inset-0 pointer-events-none">
        <div class="absolute top-0 left-1/3 w-[500px] h-[500px] rounded-full bg-primary/8 blur-[130px] animate-slow-pulse" />
        <div class="absolute bottom-0 right-1/4 w-[400px] h-[400px] rounded-full bg-indigo-500/8 blur-[110px] animate-slow-pulse animation-delay-1000" />
        <div
          class="absolute inset-0 opacity-20"
          style="background-image: radial-gradient(circle, rgb(148 163 184 / 0.4) 1px, transparent 1px); background-size: 36px 36px;"
        />
      </div>

      <UContainer class="relative text-center">
        <div class="flex items-center justify-center gap-2 text-sm text-muted mb-8 animate-fade-in">
          <NuxtLink
            to="/services"
            class="hover:text-foreground transition-colors"
          >Services</NuxtLink>
          <UIcon
            name="i-lucide-chevron-right"
            class="w-3 h-3"
          />
          <span>Outplacement Services</span>
        </div>

        <div class="animate-fade-in-up">
          <p class="text-xs font-semibold text-muted tracking-[0.25em] uppercase mb-5">
            Your Projects & Assignments in Safe Hands
          </p>
          <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold leading-[1.15] mb-6 max-w-3xl mx-auto">
            <span class="font-light">Yopaat provides</span> experienced, certified
            <span class="font-light"> professionals</span>
          </h1>
          <p class="text-xl md:text-2xl text-muted font-light leading-relaxed max-w-xl mx-auto">
            on short-, mid- and long-term assignments as required by clients.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- ── SPECIALIZATIONS – Dark Section ──────────────────── -->
    <section class="relative overflow-hidden bg-slate-900">
      <!-- Grid texture -->
      <div
        class="absolute inset-0 opacity-10"
        style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.5) 1px, transparent 1px); background-size: 36px 36px;"
      />
      <!-- Glowing blob -->
      <div class="absolute -top-40 -left-40 w-[600px] h-[600px] rounded-full bg-primary/20 blur-[120px] pointer-events-none" />
      <div class="absolute -bottom-40 -right-40 w-[500px] h-[500px] rounded-full bg-indigo-600/20 blur-[120px] pointer-events-none" />

      <UContainer class="relative py-24">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-20 items-start">
          <!-- Left heading -->
          <div class="scroll-reveal">
            <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white leading-snug">
              Some of the main specializations could be listed as follows:
            </h2>
          </div>

          <!-- Right list -->
          <ul class="flex flex-col gap-4">
            <li
              v-for="(spec, i) in specializations"
              :key="spec.text"
              class="scroll-reveal flex items-start gap-4 group"
              :style="`transition-delay: ${i * 0.07}s`"
            >
              <div class="mt-0.5 w-9 h-9 rounded-lg bg-white/10 group-hover:bg-primary/30 border border-white/10 flex items-center justify-center shrink-0 transition-colors duration-300">
                <UIcon
                  :name="spec.icon"
                  class="w-4 h-4 text-white/70 group-hover:text-white transition-colors duration-300"
                />
              </div>
              <span class="text-white/80 text-base leading-relaxed group-hover:text-white transition-colors duration-300">
                {{ spec.text }}
              </span>
            </li>
          </ul>
        </div>
      </UContainer>
    </section>

    <!-- ── MISSION CALLOUT ────────────────────────────────────── -->
    <section class="py-24 bg-elevated">
      <UContainer>
        <div class="scroll-reveal max-w-2xl mx-auto text-center">
          <div class="w-14 h-14 rounded-2xl bg-primary/10 flex items-center justify-center mx-auto mb-6">
            <UIcon
              name="i-lucide-zap"
              class="w-7 h-7 text-primary"
            />
          </div>
          <h2 class="text-3xl md:text-4xl font-bold leading-snug mb-5">
            Yopaat is here to help you manage that storm of change.
          </h2>
          <p class="text-muted text-lg leading-relaxed">
            Taken by storm of change and never-ending innovation, the way we live and conduct
            business gets disrupted at a pace that is hard to keep up with.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- ── CTA BANNER ─────────────────────────────────────────── -->
    <section class="relative overflow-hidden">
      <div class="absolute inset-0 bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900" />
      <div
        class="absolute inset-0 opacity-10"
        style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.6) 1px, transparent 1px); background-size: 36px 36px;"
      />
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[300px] rounded-full bg-primary/20 blur-[100px] pointer-events-none" />

      <UContainer class="relative py-28">
        <div class="scroll-reveal max-w-xl">
          <h2 class="text-3xl sm:text-4xl font-bold text-white leading-snug mb-6">
            Get in touch
            <span class="font-light text-white/70"> and let us know how we can help</span>
          </h2>
          <UButton
            to="/contact"
            size="lg"
            class="rounded-full px-8 font-semibold"
            trailing-icon="i-lucide-arrow-right"
          >
            Get Started
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
