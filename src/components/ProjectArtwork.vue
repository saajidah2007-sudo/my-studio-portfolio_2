<script setup>
defineProps({
  variant: { type: String, required: true },
  title: { type: String, required: true },
})
</script>

<template>
  <div class="project-artwork" :class="`artwork-${variant}`" aria-hidden="true">
    <div class="mock-browser">
      <div class="mock-topbar"><i></i><i></i><i></i><span>{{ title }}</span></div>
      <div class="mock-canvas">
        <template v-if="variant === 'rentosphere'">
          <div class="mock-rent-nav"><b>rentosphere</b><span></span><span></span><span></span></div>
          <div class="rent-hero"><small>FIND YOUR NEXT PLACE</small><b>A place<br />to call home.</b><span>Explore rentals&nbsp; ↗</span></div>
          <div class="rent-search"><i></i><i></i><i></i></div>
          <div class="rent-listings"><span></span><span></span><span></span></div>
        </template>
        <template v-else-if="variant === 'hrflow'">
          <div class="hr-sidebar"><b>h.</b><i></i><i></i><i></i><i></i></div>
          <div class="hr-main"><small>OVERVIEW</small><b>People, in focus.</b><div class="hr-metrics"><i></i><i></i><i></i></div><div class="hr-row"></div><div class="hr-row"></div><div class="hr-row"></div></div>
        </template>
        <template v-else-if="variant === 'store'">
          <div class="store-nav"><b>FORM / FOUND</b><span>SHOP&nbsp;&nbsp; ABOUT</span></div>
          <div class="store-hero"><div><small>THE EVERYDAY EDIT</small><b>Good things,<br />well chosen.</b><i>SHOP THE COLLECTION →</i></div><span class="store-object"></span></div>
          <div class="store-products"><i></i><i></i><i></i></div>
        </template>
        <template v-else-if="variant === 'gallery'">
          <div class="gallery-top"><b>STUDIES IN STILLNESS</b><span>01 — 08</span></div>
          <div class="gallery-grid"><i></i><i></i><i></i><i></i><i></i><i></i></div>
        </template>
        <template v-else-if="variant === 'showcase'">
          <div class="showcase-nav"><b>OBJECT / 01</b><span>DETAILS&nbsp;&nbsp; STORY</span></div>
          <div class="showcase-body"><div><small>MADE FOR THE MOMENT</small><b>Considered<br />by design.</b><i>DISCOVER MORE ↗</i></div><span class="showcase-object"><i></i></span></div>
        </template>
        <template v-else>
          <div class="cooking-nav"><b>THE COOKING CLASS</b><span>CLASSES&nbsp;&nbsp; CHEFS</span></div>
          <div class="cooking-hero"><small>LEARN SOMETHING DELICIOUS</small><b>Pull up<br />a chair.</b><span>Explore classes&nbsp; ↗</span></div>
          <div class="cooking-cards"><i></i><i></i><i></i></div>
        </template>
      </div>
    </div>
    <span class="artwork-caption">VISUAL STUDY <span>·</span> REPLACE WITH PROJECT SCREENSHOT</span>
  </div>
</template>
