<script setup lang="ts">
useSeoMeta({
  title: 'Industries — Yopaat',
  description: 'A deep understanding in an industry enables not only getting client needs right but also taking a client by hand to expand their horizons.'
})

const industries = [
  { icon: 'i-lucide-landmark', text: 'Public Sector' },
  { icon: 'i-lucide-banknote', text: 'Finance' },
  { icon: 'i-lucide-utensils', text: 'Hospitality & Restaurants' },
  { icon: 'i-lucide-radio-tower', text: 'Telecommunications' },
  { icon: 'i-lucide-shopping-bag', text: 'Retail' },
  { icon: 'i-lucide-graduation-cap', text: 'Education' },
  { icon: 'i-lucide-heart-pulse', text: 'Healthcare' },
  { icon: 'i-lucide-microscope', text: 'Life Sciences' },
  { icon: 'i-lucide-plane', text: 'Airlines' },
  { icon: 'i-lucide-flame', text: 'Oil & Gas & Entertainment' },
  { icon: 'i-lucide-gamepad-2', text: 'Gaming' }
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
        <div class="animate-fade-in-up">
          <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full border border-primary/30 bg-primary/10 text-primary text-xs font-semibold tracking-wide mb-8">
            <UIcon
              name="i-lucide-building-2"
              class="w-3.5 h-3.5"
            />
            Industry Expertise
          </div>
          <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold leading-[1.15] mb-6 max-w-3xl mx-auto">
            <span class="font-light">Yopaat takes pride in having</span> built various industry
            views and frameworks
          </h1>
          <p class="text-lg md:text-xl text-muted font-light leading-relaxed max-w-2xl mx-auto">
            A deep understanding in an industry enables not only getting client needs right but
            also taking a client by hand to expand their horizons to have an extended view in
            their initially assumed set of needs.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- ── INDUSTRIES – Dark Section ───────────────────────── -->
    <section class="relative overflow-hidden bg-slate-900">
      <div
        class="absolute inset-0 opacity-10"
        style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.5) 1px, transparent 1px); background-size: 36px 36px;"
      />
      <div class="absolute -top-40 -left-40 w-[600px] h-[600px] rounded-full bg-primary/20 blur-[120px] pointer-events-none" />
      <div class="absolute -bottom-40 -right-40 w-[500px] h-[500px] rounded-full bg-indigo-600/20 blur-[120px] pointer-events-none" />

      <UContainer class="relative py-24">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-20 items-start">
          <!-- Left -->
          <div class="scroll-reveal">
            <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white leading-snug">
              Yopaat's technology and management services stem from its workforce's long history
              of professional services in various industries.
            </h2>
          </div>

          <!-- Right: industry tiles -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
            <div
              v-for="(industry, i) in industries"
              :key="industry.text"
              class="scroll-reveal flex items-center gap-3 group rounded-xl border border-white/10 bg-white/5
                     hover:bg-white/10 hover:border-primary/40 px-4 py-3 transition-all duration-300 cursor-default"
              :style="`transition-delay: ${i * 0.06}s`"
            >
              <div class="w-8 h-8 rounded-lg bg-primary/20 group-hover:bg-primary/40 flex items-center justify-center shrink-0 transition-colors duration-300">
                <UIcon
                  :name="industry.icon"
                  class="w-4 h-4 text-primary/80 group-hover:text-white transition-colors duration-300"
                />
              </div>
              <span class="text-white/80 text-sm font-medium group-hover:text-white transition-colors duration-300 leading-snug">
                {{ industry.text }}
              </span>
            </div>
          </div>
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
