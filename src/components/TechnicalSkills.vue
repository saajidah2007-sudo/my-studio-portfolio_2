<script setup>
const groups = [
  {
    number: 'A',
    title: 'Frontend',
    note: 'Interfaces, structure & responsive layouts',
    skills: ['HTML', 'CSS', 'JavaScript', 'Vue.js', 'Responsive Web Design', 'Bootstrap'],
  },
  {
    number: 'B',
    title: 'Backend',
    note: 'Server-side foundations & data',
    skills: ['Node.js', 'Express.js', 'PHP', 'MySQL', 'SQL', 'REST API fundamentals'],
  },
]
</script>

<template>
  <section id="skills" class="skills-section page-section">
    <div class="content-shell">
      <div class="section-kicker"><span>03</span><span class="kicker-line"></span><span>MY TOOLKIT</span></div>
      <div class="section-heading-row">
        <div>
          <p class="eyebrow">Tools I’m learning and using</p>
          <h2>Good work starts<br />with <span>good tools.</span></h2>
        </div>
        <p class="heading-aside">A growing toolkit, built through practice.<br />No scorecards — just the tools I reach for.</p>
      </div>
      <div class="skill-groups">
        <article v-for="group in groups" :key="group.title" class="skill-group">
          <div class="skill-group-top">
            <span class="skill-group-index">{{ group.number }}<span> / 02</span></span>
            <span class="skill-group-mark" aria-hidden="true">✳</span>
          </div>
          <h3>{{ group.title }}</h3>
          <p class="skill-note">{{ group.note }}</p>
          <ul class="skill-list">
            <li v-for="skill in group.skills" :key="skill">{{ skill }}</li>
          </ul>
        </article>
      </div>
      <p class="skill-footnote"><span aria-hidden="true">✳</span> Still learning. Always building.</p>
    </div>
  </section>
</template>
