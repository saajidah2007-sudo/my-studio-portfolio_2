<script setup>
import { ref } from 'vue'
import { projects } from '../data/projects'
import ProjectCard from './ProjectCard.vue'
import ProjectDetails from './ProjectDetails.vue'

const selectedProject = ref(null)
</script>

<template>
  <section id="projects" class="projects-section page-section">
    <div class="content-shell">
      <div class="section-kicker"><span>04</span><span class="kicker-line"></span><span>THE PROJECT GALLERY</span></div>
      <div class="section-heading-row projects-heading">
        <div>
          <p class="eyebrow">Selected work & learning projects</p>
          <h2>A few frames<br />from <span>the process.</span></h2>
        </div>
        <p class="heading-aside">Six projects, each a chance to learn<br />something new and make it real.</p>
      </div>
      <div class="project-grid">
        <ProjectCard v-for="project in projects" :key="project.id" :project="project" @select="selectedProject = $event" />
      </div>
      <p class="gallery-note"><span></span> PROJECT VISUALS ARE PLACEHOLDERS UNTIL SCREENSHOTS ARE ADDED</p>
    </div>
    <ProjectDetails v-if="selectedProject" :project="selectedProject" @close="selectedProject = null" />
  </section>
</template>
