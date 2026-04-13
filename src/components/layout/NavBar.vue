<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const menuOpen = ref(false)
const scrolled = ref(false)

function onScroll() {
  scrolled.value = window.scrollY > 60
}

onMounted(() => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))

const navLinks = [
  { label: 'Portfolio', href: '#portfolio' },
  { label: 'Services', href: '#services' },
]
</script>

<template>
  <header
    class="nav-header fixed top-0 left-0 right-0 z-50 transition-all duration-500"
    :class="scrolled ? 'nav-scrolled' : 'nav-transparent'"
  >
    <div class="container nav-inner">
      <a href="#home" class="nav-logo">
        aiky
      </a>

      <!-- Desktop nav -->
      <nav class="hidden md:flex items-center gap-10">
        <a
          v-for="link in navLinks"
          :key="link.label"
          :href="link.href"
          class="nav-link"
        >
          {{ link.label }}
        </a>
        <a href="#contact" class="nav-cta">
          Get in touch
        </a>
      </nav>

      <!-- Mobile hamburger -->
      <button
        class="md:hidden flex flex-col gap-[5px] p-1"
        @click="menuOpen = !menuOpen"
        aria-label="Toggle menu"
      >
        <span class="burger-line" :class="menuOpen ? 'rotate-45 translate-y-[6px]' : ''"></span>
        <span class="burger-line" :class="menuOpen ? 'opacity-0' : ''"></span>
        <span class="burger-line" :class="menuOpen ? '-rotate-45 -translate-y-[6px]' : ''"></span>
      </button>
    </div>

    <!-- Mobile menu -->
    <div v-if="menuOpen" class="mobile-menu md:hidden">
      <a
        v-for="link in navLinks"
        :key="link.label"
        :href="link.href"
        class="mobile-link"
        @click="menuOpen = false"
      >
        {{ link.label }}
      </a>
      <a
        href="#contact"
        class="mobile-cta"
        @click="menuOpen = false"
      >
        Get in touch
      </a>
    </div>
  </header>
</template>

<style scoped>
.nav-header {
  border-bottom: 1px solid transparent;
}

.nav-transparent {
  background: transparent;
}

.nav-scrolled {
  background: rgba(250, 248, 245, 0.96);
  backdrop-filter: blur(12px);
  border-bottom-color: rgba(26, 25, 23, 0.1);
}

.nav-logo {
  font-family: 'Playfair', Georgia, serif;
  font-size: 0.75rem;
  letter-spacing: 0.35em;
  text-transform: uppercase;
  color: var(--cream);
  font-weight: 500;
}

.nav-scrolled .nav-logo {
  color: var(--text);
}

.nav-link {
  font-size: 0.7rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--cream-dim);
  transition: color 0.2s;
}

.nav-scrolled .nav-link {
  color: var(--text-muted);
}

.nav-link:hover {
  color: var(--cream);
}

.nav-scrolled .nav-link:hover {
  color: var(--text);
}

.nav-cta {
  font-size: 0.7rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  border: 1px solid rgba(201, 169, 110, 0.5);
  color: var(--bronze);
  padding: 0.55rem 1.4rem;
  transition: all 0.25s;
}

.nav-cta:hover {
  background: var(--bronze);
  color: var(--ink);
  border-color: var(--bronze);
}

.burger-line {
  display: block;
  width: 20px;
  height: 1px;
  background: var(--cream);
  transition: all 0.2s;
}

.mobile-menu {
  background: var(--bg);
  border-top: 1px solid var(--divider);
  padding: 2rem var(--gutter);
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.mobile-link {
  font-size: 0.7rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--text-muted);
  transition: color 0.2s;
}

.mobile-link:hover {
  color: var(--text);
}

.mobile-cta {
  font-size: 0.7rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  border: 1px solid rgba(201, 169, 110, 0.5);
  color: var(--bronze);
  padding: 0.75rem 1.5rem;
  text-align: center;
  width: fit-content;
  transition: all 0.25s;
}

.nav-inner {
  height: 76px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
