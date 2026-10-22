<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
import SiteNavigation from './components/SiteNavigation.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import TechnicalSkills from './components/TechnicalSkills.vue'
import ProjectGallery from './components/ProjectGallery.vue'
import ContactSection from './components/ContactSection.vue'
import SiteFooter from './components/SiteFooter.vue'

const activeSection = ref('home')
const sectionIds = ['home', 'about', 'skills', 'projects', 'contact']
let observer

onMounted(() => {
  if (!('IntersectionObserver' in window)) return

  document.documentElement.classList.add('motion-ready')
  observer = new IntersectionObserver(
    (entries) => {
      entries
        .filter((entry) => entry.isIntersecting)
        .forEach((entry) => { entry.target.dataset.visible = 'true' })
      const visible = entries
        .filter((entry) => entry.isIntersecting)
        .sort((a, b) => b.intersectionRatio - a.intersectionRatio)[0]
      if (visible) activeSection.value = visible.target.id
    },
    { rootMargin: '-25% 0px -55% 0px', threshold: [0, 0.15, 0.35, 0.6] },
  )

  sectionIds.forEach((id) => {
    const section = document.getElementById(id)
    if (section) observer.observe(section)
  })
})

onUnmounted(() => observer?.disconnect())
</script>

<template>
  <a class="skip-link" href="#main-content">Skip to content</a>
  <SiteNavigation :active-section="activeSection" />
  <main id="main-content">
    <HeroSection />
    <AboutSection />
    <TechnicalSkills />
    <ProjectGallery />
    <ContactSection />
  </main>
  <SiteFooter />
</template>
