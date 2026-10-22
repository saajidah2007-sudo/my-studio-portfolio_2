<script setup>
import { nextTick, onMounted, onUnmounted, ref } from 'vue'

const props = defineProps({
  project: { type: Object, required: true },
})
const emit = defineEmits(['close'])
const dialog = ref(null)

function close() {
  if (dialog.value?.open) dialog.value.close()
  emit('close')
}

function onDialogClose() {
  emit('close')
}

function onBackdropClick(event) {
  if (event.target === dialog.value) close()
}

onMounted(async () => {
  await nextTick()
  dialog.value?.showModal()
})

onUnmounted(() => {
  if (dialog.value?.open) dialog.value.close()
})
</script>

<template>
  <dialog
    ref="dialog"
    class="project-dialog"
    :aria-labelledby="`dialog-title-${project.id}`"
    @cancel.prevent="close"
    @keydown.esc.prevent="close"
    @close="onDialogClose"
    @click="onBackdropClick"
  >
    <div class="dialog-inner">
      <div class="dialog-topline"><span>PROJECT NOTES · {{ project.category }}</span><button class="dialog-close" type="button" aria-label="Close project details" @click="close">×</button></div>
      <div class="dialog-art"><div class="dialog-art-frame"><span>PRINT NO. {{ project.id.toUpperCase() }}</span><strong>{{ project.name }}</strong><small>PROJECT VISUAL PLACEHOLDER</small></div></div>
      <h2 :id="`dialog-title-${project.id}`">{{ project.name }}</h2>
      <p class="dialog-description">{{ project.description }}</p>
      <div class="dialog-detail-block">
        <h3>Technologies</h3>
        <ul v-if="project.technologies.length" class="technology-list">
          <li v-for="technology in project.technologies" :key="technology">{{ technology }}</li>
        </ul>
        <p v-else class="detail-note">{{ project.technologyNote }}</p>
      </div>
      <div class="dialog-detail-block">
        <h3>Take a closer look</h3>
        <div v-if="project.links.length" class="dialog-links">
          <a v-for="link in project.links" :key="link.label" :href="link.url" target="_blank" rel="noreferrer">{{ link.label }} ↗</a>
        </div>
        <p v-else class="detail-note">GitHub and live-demo links haven’t been supplied yet.</p>
      </div>
      <p class="dialog-footnote">Replace this visual study with a project screenshot when one is available.</p>
    </div>
  </dialog>
</template>
