<script setup lang="ts">
useSeoMeta({
  title: 'Services — Yopaat',
  description: 'Explore Yopaat\'s full suite of technology and management services: Consultancy, Project, and Outplacement Services.'
})

const services = [
  {
    icon: 'i-lucide-handshake',
    label: 'Consultancy Services',
    href: '/services/consultancy-services',
    color: 'from-blue-500 to-indigo-600',
    description:
      'Guiding organisations from planning through implementation and beyond. We bring structured methodology and deep expertise to every engagement.',
    items: ['Planning', 'Implementation', 'Maintenance, Support & Training'],
    featured: false
  },
  {
    icon: 'i-lucide-laptop',
    label: 'Project Services',
    href: '/services/project-services',
    color: 'from-indigo-500 to-violet-600',
    description:
      'End-to-end project delivery backed by proven technology architecture and best practices — from strategy through pre-sales to execution.',
    items: ['Strategy Development', 'Pre-Sales', 'Technology Architecture & Best Practices'],
    featured: true
  },
  {
    icon: 'i-lucide-briefcase',
    label: 'Outplacement Services',
    href: '/services/outplacement-services',
    color: 'from-sky-500 to-blue-600',
    description:
      'On-demand access to experienced, certified professionals ready for short-, mid-, and long-term assignments tailored to your business needs.',
    items: ['Certified Professionals', 'Flexible Assignment Lengths', 'Industry-matched Placements'],
    featured: false
  }
]

const process = [
  { icon: 'i-lucide-search', step: '01', title: 'Discovery', description: 'We listen closely to understand your goals, constraints, and context before proposing anything.' },
  { icon: 'i-lucide-pencil-ruler', step: '02', title: 'Strategy', description: 'Our experts craft a tailored roadmap combining industry standards with your unique requirements.' },
  { icon: 'i-lucide-rocket', step: '03', title: 'Delivery', description: 'We execute with precision, keeping you informed and in control at every milestone.' },
  { icon: 'i-lucide-shield-check', step: '04', title: 'Support', description: 'Post-delivery we remain a trusted partner, providing ongoing support, training, and refinement.' }
]

onMounted(() => {
  const observer = new IntersectionObserver(
    entries => entries.forEach((el) => {
      if (el.isIntersecting) {
        el.target.classList.add('revealed')
        observer.unobserve(el.target)
      }
    }),
    { threshold: 0.1 }
  )
  document.querySelectorAll('.scroll-reveal').forEach(el => observer.observe(el))
})
</script>

<template>
  <div>
    <!-- ── HERO ──────────────────────────────────────────────── -->
    <section class="relative py-28 overflow-hidden">
      <!-- bg blobs + dot grid -->
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
          <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold leading-[1.15] mb-6 max-w-4xl mx-auto">
            <span class="font-light text-muted">End-to-end technology</span><br>
            and management services
            <span class="text-transparent bg-clip-text bg-linear-to-r from-blue-500 to-indigo-600"> tailored to you.</span>
          </h1>

          <p class="text-lg md:text-xl text-muted font-light leading-relaxed max-w-2xl mx-auto">
            From strategy and planning to delivery, support, and expert staffing — Yopaat covers
            the full spectrum of business and technology services your organisation needs.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- ── SERVICE CARDS ─────────────────────────────────────── -->
    <section class="py-24 bg-elevated">
      <UContainer>
        <div class="text-center mb-16 scroll-reveal">
          <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-3">
            Our Services
          </p>
          <h2 class="text-3xl md:text-4xl font-bold mb-4">
            Three Ways We Serve You
          </h2>
          <p class="text-muted max-w-xl mx-auto text-lg font-light">
            Each service line is designed to integrate seamlessly with the others, creating a comprehensive support system for your organisation.
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div
            v-for="(service, i) in services"
            :key="service.label"
            class="scroll-reveal"
            :style="`transition-delay: ${i * 0.12}s`"
          >
            <NuxtLink
              :to="service.href"
              class="group block h-full"
            >
              <div
                class="h-full rounded-2xl border p-8 flex flex-col gap-5 transition-all duration-300"
                :class="service.featured
                  ? 'bg-primary text-white border-primary shadow-xl shadow-primary/25'
                  : 'bg-default border-default hover:border-primary/40 hover:shadow-lg'"
              >
                <!-- Icon -->
                <div
                  class="w-14 h-14 rounded-xl flex items-center justify-center"
                  :class="service.featured ? 'bg-white/20' : 'bg-primary/10'"
                >
                  <UIcon
                    :name="service.icon"
                    class="w-7 h-7"
                    :class="service.featured ? 'text-white' : 'text-primary'"
                  />
                </div>

                <!-- Title -->
                <h3
                  class="text-xl font-bold"
                  :class="service.featured ? 'text-white' : ''"
                >
                  {{ service.label }}
                </h3>

                <!-- Description -->
                <p
                  class="text-sm leading-relaxed flex-1"
                  :class="service.featured ? 'text-white/80' : 'text-muted'"
                >
                  {{ service.description }}
                </p>

                <!-- Items list -->
                <ul class="flex flex-col gap-2">
                  <li
                    v-for="item in service.items"
                    :key="item"
                    class="flex items-start gap-2 text-sm"
                    :class="service.featured ? 'text-white/80' : 'text-muted'"
                  >
                    <UIcon
                      name="i-lucide-check"
                      class="w-4 h-4 mt-0.5 shrink-0"
                      :class="service.featured ? 'text-white/70' : 'text-primary'"
                    />
                    {{ item }}
                  </li>
                </ul>

                <!-- CTA -->
                <div
                  class="flex items-center gap-1 text-sm font-semibold mt-2"
                  :class="service.featured ? 'text-white' : 'text-primary'"
                >
                  Learn more
                  <UIcon
                    name="i-lucide-arrow-right"
                    class="w-4 h-4 transition-transform duration-200 group-hover:translate-x-1"
                  />
                </div>
              </div>
            </NuxtLink>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ── HOW WE WORK – Dark Section ────────────────────────── -->
    <section class="relative overflow-hidden bg-slate-900">
      <!-- bg decoration -->
      <div
        class="absolute inset-0 opacity-10"
        style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.5) 1px, transparent 1px); background-size: 36px 36px;"
      />
      <div class="absolute -top-40 -left-40 w-[600px] h-[600px] rounded-full bg-primary/20 blur-[120px] pointer-events-none" />
      <div class="absolute -bottom-40 -right-40 w-[500px] h-[500px] rounded-full bg-indigo-600/20 blur-[120px] pointer-events-none" />

      <UContainer class="relative py-24">
        <!-- Section header -->
        <div class="text-center mb-16 scroll-reveal">
          <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-3">
            Our Approach
          </p>
          <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
            How We Work
          </h2>
          <p class="text-white/60 max-w-xl mx-auto text-lg font-light">
            A structured, collaborative methodology that puts your success at the centre of every engagement.
          </p>
        </div>

        <!-- Process steps -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
          <div
            v-for="(step, i) in process"
            :key="step.step"
            class="scroll-reveal group relative rounded-2xl border border-white/10 bg-white/5 hover:bg-white/10 hover:border-primary/40 p-8 transition-all duration-300"
            :style="`transition-delay: ${i * 0.1}s`"
          >
            <!-- Step number -->
            <span class="absolute top-6 right-6 text-5xl font-black text-white/5 group-hover:text-white/10 transition-colors duration-300 select-none leading-none">
              {{ step.step }}
            </span>

            <!-- Icon -->
            <div class="w-12 h-12 rounded-xl bg-primary/20 group-hover:bg-primary/40 flex items-center justify-center mb-5 transition-colors duration-300">
              <UIcon
                :name="step.icon"
                class="w-6 h-6 text-primary/80 group-hover:text-white transition-colors duration-300"
              />
            </div>

            <h3 class="text-lg font-bold text-white mb-2">
              {{ step.title }}
            </h3>
            <p class="text-white/60 text-sm leading-relaxed">
              {{ step.description }}
            </p>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ── MISSION CALLOUT ─────────────────────────────────────── -->
    <section class="py-24 bg-default">
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
            Yopaat takes its name from the ancient Mayan storm god. Being able to manage the
            relentless storm of technological change is the ultimate power — and we're here to
            hand it to you.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- ── CTA BANNER ──────────────────────────────────────────── -->
    <section class="relative overflow-hidden">
      <div class="absolute inset-0 bg-linear-to-br from-slate-900 via-slate-800 to-slate-900" />
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
          <div class="flex flex-wrap gap-4">
            <UButton
              to="/contact"
              size="lg"
              class="rounded-full px-8 font-semibold"
              trailing-icon="i-lucide-arrow-right"
            >
              Get Started
            </UButton>
            <UButton
              to="/specializations"
              size="lg"
              color="neutral"
              variant="outline"
              class="rounded-full px-8 font-semibold border-white/20 text-white hover:bg-white/10"
            >
              Our Specializations
            </UButton>
          </div>
        </div>
      </UContainer>
    </section>
  </div>
</template>
