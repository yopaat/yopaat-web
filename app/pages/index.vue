<script setup lang="ts">
useSeoMeta({
  title: 'Yopaat — Technology & Management Services',
  description: 'Yopaat is a cross-industry, cross-disciplinary B2B services company with a focus on technology and management services in Information & Communication Technologies.',
  keywords: 'Yopaat, B2B services, technology, management, ICT, consultancy, specializations',
  ogTitle: 'Yopaat — Technology & Management Services',
  ogDescription: 'Bringing together industrial specialization and technology expertise.',
  ogImage: '/yopaat-logo.png',
  twitterImage: '/yopaat-logo.png',
  twitterCard: 'summary_large_image'
})

// Scroll reveal intersection observer
onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach(el => {
        if (el.isIntersecting) {
          el.target.classList.add('revealed')
          observer.unobserve(el.target)
        }
      })
    },
    { threshold: 0.1 }
  )
  document.querySelectorAll('.scroll-reveal').forEach(el => observer.observe(el))
})

const services = [
  {
    icon: 'i-lucide-handshake',
    title: 'Consultancy Services',
    href: '/services/consultancy-services',
    items: ['Planning', 'Implementation', 'Maintenance, Support & Training'],
    featured: false
  },
  {
    icon: 'i-lucide-laptop',
    title: 'Project Services',
    href: '/services/project-services',
    items: ['Strategy Development', 'Pre-Sales', 'Technology Architecture & Best Practices'],
    featured: true
  },
  {
    icon: 'i-lucide-briefcase',
    title: 'Outplacement Services',
    href: '/services/outplacement-services',
    items: ['Experienced, certified professionals on short-, mid, and long-term assignments as required by clients.'],
    featured: false
  }
]
</script>

<template>
  <div class="overflow-x-hidden">
    <!-- ===================== HERO ===================== -->
    <section class="relative min-h-[92vh] flex items-center justify-center overflow-hidden">
      <!-- Background gradient blobs -->
      <div class="absolute inset-0 pointer-events-none z-0">
        <div class="absolute top-[-10%] left-[-5%] w-[600px] h-[600px] rounded-full bg-blue-500/10 blur-[140px] animate-slow-pulse" />
        <div class="absolute bottom-[-15%] right-[-5%] w-[500px] h-[500px] rounded-full bg-indigo-600/10 blur-[120px] animate-slow-pulse animation-delay-1000" />
        <!-- Dot grid -->
        <div
          class="absolute inset-0 opacity-30"
          style="background-image: radial-gradient(circle, rgb(148 163 184 / 0.4) 1px, transparent 1px); background-size: 36px 36px;"
        />
      </div>

      <UContainer class="relative z-10 text-center py-24 px-4">
        <!-- Hero badge -->
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full border border-primary/30 bg-primary/10 text-primary text-xs font-semibold tracking-wide mb-8 animate-fade-in">
          <span class="w-1.5 h-1.5 rounded-full bg-primary animate-pulse inline-block" />
          Technology & Management Services
        </div>

        <!-- Main headline -->
        <h1 class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-bold tracking-tight leading-[1.1] mb-6 animate-fade-in-up animation-delay-200">
          Bringing Together
          <br class="hidden sm:block">
          <span class="font-light text-muted">Industrial Specialization</span>
          <br>
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-500 to-indigo-600 animate-gradient">
            &amp; Technology Expertise
          </span>
        </h1>

        <!-- Sub-headline -->
        <p class="max-w-2xl mx-auto text-lg md:text-xl text-muted font-light leading-relaxed mb-10 animate-fade-in-up animation-delay-400">
          Yopaat's capabilities bring a verticalized articulation of technological prowess.
          Clients benefit from established industry standards and proven best practices, out of the box.
        </p>

        <!-- CTAs -->
        <div class="flex flex-wrap items-center justify-center gap-4 animate-fade-in-up animation-delay-600">
          <UButton
            to="/services"
            size="xl"
            class="rounded-full px-8 font-semibold shadow-lg shadow-primary/20"
            trailing-icon="i-lucide-arrow-right"
          >
            Our Services
          </UButton>
          <UButton
            to="/contact"
            size="xl"
            color="neutral"
            variant="outline"
            class="rounded-full px-8 font-semibold"
          >
            Get in Touch
          </UButton>
        </div>
      </UContainer>

      <!-- Scroll indicator -->
      <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 animate-float">
        <span class="text-xs text-muted tracking-widest uppercase">Scroll</span>
        <UIcon name="i-lucide-chevron-down" class="text-muted w-4 h-4" />
      </div>
    </section>

    <!-- ===================== SERVICES CARDS ===================== -->
    <section class="py-24 bg-default">
      <UContainer>
        <!-- Section header -->
        <div class="text-center mb-16 scroll-reveal">
          <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-3">What We Do</p>
          <h2 class="text-3xl md:text-4xl font-bold mb-4">Our Services</h2>
          <p class="text-muted max-w-xl mx-auto text-lg font-light">
            End-to-end technology and management services tailored to your industry needs.
          </p>
        </div>

        <!-- 3-column cards -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div
            v-for="(service, i) in services"
            :key="service.title"
            class="scroll-reveal card-hover"
            :style="`animation-delay: ${i * 0.15}s`"
          >
            <NuxtLink :to="service.href" class="block h-full">
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
                  {{ service.title }}
                </h3>

                <!-- Items list -->
                <ul class="flex flex-col gap-2 flex-1">
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
                  <UIcon name="i-lucide-arrow-right" class="w-4 h-4 transition-transform group-hover:translate-x-1" />
                </div>
              </div>
            </NuxtLink>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ===================== ABOUT / MISSION ===================== -->
    <section class="py-24 relative overflow-hidden">
      <!-- Subtle bg tint -->
      <div class="absolute inset-0 pointer-events-none">
        <div class="absolute top-0 right-0 w-[500px] h-[500px] rounded-full bg-primary/5 blur-[120px]" />
      </div>

      <UContainer class="relative">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <!-- Left: Text -->
          <div class="scroll-reveal">
            <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-4">
              Plan, Organize and Execute Your Projects Together
            </p>
            <h2 class="text-3xl md:text-4xl font-bold leading-[1.2] mb-6">
              Yopaat is here
              <span class="font-light text-muted"> to help you manage that storm of change.</span>
            </h2>
            <p class="text-muted text-lg leading-relaxed mb-8 max-w-lg">
              Yopaat takes its name from the ancient Mayan storm god. Its relevance is inspiring since
              we are all taken by the storm of technological change — and being able to manage that
              change is the ultimate power.
            </p>
            <UButton
              to="/specializations"
              size="lg"
              class="rounded-full px-7 font-semibold shadow-lg shadow-primary/20"
              trailing-icon="i-lucide-arrow-right"
            >
              Learn More
            </UButton>
          </div>

          <!-- Right: Placeholder visual -->
          <div class="scroll-reveal animation-delay-400 relative">
            <!-- Floating card 1 (back) -->
            <div class="absolute -top-6 -left-6 w-48 h-32 rounded-2xl bg-gradient-to-br from-indigo-500/20 to-blue-600/20 border border-primary/20 backdrop-blur-sm shadow-xl animate-float animation-delay-600" />
            <!-- Main card -->
            <div class="relative rounded-3xl bg-gradient-to-br from-default to-elevated border border-default shadow-2xl overflow-hidden aspect-[4/3] flex items-center justify-center animate-float animation-delay-200">
              <div class="text-center px-8">
                <div class="w-20 h-20 mx-auto mb-4 rounded-2xl bg-primary/10 flex items-center justify-center">
                  <UIcon name="i-lucide-zap" class="w-10 h-10 text-primary" />
                </div>
                <p class="text-2xl font-bold mb-1">Ready to Transform?</p>
                <p class="text-muted text-sm">Image coming soon</p>
              </div>
            </div>
            <!-- Stats badge -->
            <div class="absolute -bottom-4 -right-4 bg-primary text-white rounded-2xl px-5 py-3 shadow-xl shadow-primary/30 animate-float animation-delay-800">
              <p class="text-xs font-medium opacity-80">Industry Expertise</p>
              <p class="text-2xl font-bold">10+</p>
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ===================== SPECIALIZATIONS & INDUSTRIES ===================== -->
    <section id="spec" class="py-24 bg-elevated">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <!-- Left: Visual Parallax Stack -->
          <div class="relative scroll-reveal">
            <!-- Back card -->
            <div
              class="absolute top-8 left-8 w-[75%] aspect-[4/3] rounded-2xl bg-gradient-to-br from-indigo-400/20 to-blue-500/20 border border-primary/20 shadow-xl backdrop-blur-sm"
              style="transform: translateY(0px); transition: transform 0.3s ease;"
            />
            <!-- Front card -->
            <div class="relative w-[85%] aspect-[4/3] rounded-2xl bg-gradient-to-br from-default to-white dark:to-muted border border-default shadow-2xl overflow-hidden flex items-center justify-center">
              <div class="text-center">
                <div class="w-16 h-16 mx-auto mb-3 rounded-xl bg-primary/10 flex items-center justify-center">
                  <UIcon name="i-lucide-layers" class="w-8 h-8 text-primary" />
                </div>
                <p class="font-semibold text-lg">Multi-Domain Expertise</p>
                <p class="text-muted text-sm">Image placeholder</p>
              </div>
            </div>
          </div>

          <!-- Right: Text blocks -->
          <div class="flex flex-col gap-12">
            <!-- Specializations -->
            <div class="scroll-reveal">
              <h3 class="text-2xl font-bold mb-3">Specializations</h3>
              <p class="text-muted leading-relaxed mb-5">
                Yopaat excels in putting skills and specializations of various fields into a coherent,
                coordinated action plan in order to meet and exceed client expectations.
              </p>
              <UButton
                to="/specializations"
                size="md"
                class="rounded-full px-6 font-semibold"
                trailing-icon="i-lucide-arrow-right"
              >
                Specializations
              </UButton>
            </div>

            <USeparator />

            <!-- Industries -->
            <div class="scroll-reveal animation-delay-200">
              <h3 class="text-2xl font-bold mb-3">Industries</h3>
              <p class="text-muted leading-relaxed mb-5">
                A deep understanding in an industry enables not only getting client needs right but
                also taking a client by hand to expand their horizons — providing an extended view
                beyond their initially assumed set of needs.
              </p>
              <UButton
                to="/industries"
                size="md"
                class="rounded-full px-6 font-semibold"
                trailing-icon="i-lucide-arrow-right"
              >
                Industries
              </UButton>
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ===================== CTA BANNER ===================== -->
    <section class="py-20 bg-default">
      <UContainer>
        <div class="scroll-reveal rounded-3xl bg-gradient-to-r from-blue-600 to-indigo-700 p-12 text-center text-white shadow-2xl shadow-primary/20 relative overflow-hidden">
          <!-- BG noise texture -->
          <div class="absolute inset-0 opacity-10 pointer-events-none"
            style="background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMzAwIj48ZmlsdGVyIGlkPSJuIj48ZmVUdXJidWxlbmNlIHR5cGU9ImZyYWN0YWxOb2lzZSIgYmFzZUZyZXF1ZW5jeT0iMC45IiBzdGl0Y2hUaWxlcz0ic3RpdGNoIi8+PC9maWx0ZXI+PHJlY3Qgd2lkdGg9IjMwMCIgaGVpZ2h0PSIzMDAiIGZpbHRlcj0idXJsKCNuKSIgb3BhY2l0eT0iMSIvPjwvc3ZnPg==');"
          />
          <p class="text-sm font-semibold tracking-widest uppercase opacity-80 mb-4">Let's Work Together</p>
          <h2 class="text-3xl md:text-4xl font-bold mb-4 leading-tight">
            Ready to navigate the storm<br class="hidden sm:block"> of technological change?
          </h2>
          <p class="text-white/75 text-lg font-light max-w-xl mx-auto mb-8">
            Get in touch with our team and discover how Yopaat can accelerate your digital transformation.
          </p>
          <UButton
            to="/contact"
            size="xl"
            color="neutral"
            variant="solid"
            class="rounded-full px-10 font-semibold bg-white text-primary hover:bg-white/90 shadow-xl"
            trailing-icon="i-lucide-arrow-right"
          >
            Contact Us
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
