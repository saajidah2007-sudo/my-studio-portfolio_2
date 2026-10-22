<script setup>
import { ref } from 'vue'

const email = ref('')
const message = ref('')
const copied = ref(false)

async function copyEmail() {
  if (!email.value) {
    message.value = 'Add your email address in ContactSection.vue to enable this action.'
    return
  }

  try {
    await navigator.clipboard.writeText(email.value)
    copied.value = true
    message.value = 'Email address copied.'
    window.setTimeout(() => { copied.value = false }, 2200)
  } catch (error) {
    message.value = 'Copy was unavailable. Add an email link in ContactSection.vue to make contact.'
  }
}
</script>

<template>
  <section id="contact" class="contact-section page-section">
    <div class="contact-inner content-shell">
      <div class="section-kicker section-kicker-light"><span>05</span><span class="kicker-line"></span><span>THE LAST PRINT</span></div>
      <div class="contact-layout">
        <div>
          <p class="eyebrow">Open to opportunities & collaboration</p>
          <h2>Let’s create<br /><span>something useful.</span></h2>
        </div>
        <div class="contact-copy">
          <p>I’m looking forward to what comes next. If you’d like to talk about an opportunity, a project, or the work on this page, I’d be glad to hear from you.</p>
          <button class="button button-light" type="button" @click="copyEmail">
            {{ copied ? 'Email copied' : 'Get in touch' }} <span aria-hidden="true">↗</span>
          </button>
          <p v-if="message" class="contact-status" role="status">{{ message }}</p>
          <p v-else class="contact-setup">Add your email address in <code>ContactSection.vue</code> to activate this contact button.</p>
        </div>
      </div>
      <div class="contact-bottom-line"><span>CAPE TOWN, SOUTH AFRICA</span><span>MADE WITH CURIOSITY&nbsp; · &nbsp;2026</span></div>
    </div>
  </section>
</template>
