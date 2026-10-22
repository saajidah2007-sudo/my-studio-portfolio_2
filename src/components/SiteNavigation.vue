<script setup>
import { ref } from 'vue'

defineProps({
  activeSection: { type: String, default: 'home' },
})

const menuOpen = ref(false)
const links = [
  { id: 'home', label: 'Home' },
  { id: 'about', label: 'About' },
  { id: 'skills', label: 'Toolkit' },
  { id: 'projects', label: 'Projects' },
  { id: 'contact', label: 'Contact' },
]

function closeMenu() {
  menuOpen.value = false
}
</script>

<template>
  <header class="site-header">
    <nav class="nav-shell" aria-label="Main navigation">
      <a class="wordmark" href="#home" @click="closeMenu">
        <span class="wordmark-mark" aria-hidden="true">SA</span>
        <span>Saajidah Abrahams</span>
      </a>
      <button
        class="menu-toggle"
        type="button"
        :aria-expanded="menuOpen"
        aria-controls="site-navigation-links"
        :aria-label="menuOpen ? 'Close navigation menu' : 'Open navigation menu'"
        @click="menuOpen = !menuOpen"
      >
        <span></span><span></span>
      </button>
      <div id="site-navigation-links" class="nav-links" :class="{ 'is-open': menuOpen }">
        <a
          v-for="link in links"
          :key="link.id"
          :href="`#${link.id}`"
          :class="{ 'is-active': activeSection === link.id }"
          :aria-current="activeSection === link.id ? 'location' : undefined"
          @click="closeMenu"
        >{{ link.label }}</a>
      </div>
    </nav>
  </header>
</template>
