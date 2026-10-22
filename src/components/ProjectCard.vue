<script setup>
import ProjectArtwork from './ProjectArtwork.vue'

defineProps({
  project: { type: Object, required: true },
})
defineEmits(['select'])
</script>

<template>
  <article class="project-card">
    <button class="project-card-button" type="button" :aria-label="`View details for ${project.name}`" @click="$emit('select', project)">
      <ProjectArtwork :variant="project.visual" :title="project.name" />
      <div class="project-card-copy">
        <div class="project-card-meta"><span>{{ project.category }}</span><span class="project-arrow" aria-hidden="true">↗</span></div>
        <h3>{{ project.name }}</h3>
        <span class="project-card-link">View project notes <span aria-hidden="true">→</span></span>
      </div>
    </button>
  </article>
</template>
