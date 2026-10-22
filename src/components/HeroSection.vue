<script setup>
const portraitFrames = ['A first frame', 'In the making', 'Still curious']
</script>

<template>
  <section id="home" class="hero-section page-section">
    <div class="hero-layout content-shell">
      <div class="hero-copy">
        <p class="eyebrow"><span class="eyebrow-dot"></span> Developer in progress · Cape Town, SA</p>
        <h1><span class="hero-title-line">Every project</span><span class="hero-title-line">tells a <span class="hero-accent">story.</span></span></h1>
        <p class="hero-intro">
          I’m Saajidah Abrahams, an aspiring full-stack developer who enjoys turning thoughtful
          ideas into useful, welcoming digital experiences.
        </p>
        <div class="hero-actions">
          <a class="button button-primary" href="#projects">
            Explore my work <span aria-hidden="true">↗</span>
          </a>
          <a class="button button-text" href="#contact">Get in touch <span aria-hidden="true">↓</span></a>
        </div>
        <div class="hero-index"><span>01 / 05</span><span class="index-rule"></span><span>THE INTRODUCTION</span></div>
      </div>

      <div class="hero-visual">
        <div class="photo-note note-top"><span>ROLL NO. 01</span><span>CT · ZA</span></div>
        <figure class="photo-strip">
          <img src="/images/profile/portrait-strip.svg" alt="Illustrated black-and-white photo booth portrait strip, a replaceable visual placeholder" />
          <figcaption class="strip-caption">
            <span>SA · CONTACT SHEET</span>
            <span>FIG. 01</span>
          </figcaption>
        </figure>
        <p class="photo-note note-bottom">A little room to make things.</p>
        <div class="frame-stamp" aria-hidden="true">MADE<br />TO LEARN</div>
      </div>
    </div>
    <a class="scroll-cue" href="#about"><span class="scroll-cue-line"></span> Scroll to explore</a>
  </section>
</template>
