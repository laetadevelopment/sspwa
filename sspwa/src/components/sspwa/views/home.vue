<template>
  <div v-if="showHome" id="home" class="page">
    <div class="page-title">
      <h1>Single Screen Progressive Web App</h1>
    </div>
    <div class="page-content">
      <h2>The mission of the SSPWA (Single Screen Progressive Web App) Template is to create a progressive web app experience that feels like interacting with a movie.</h2>
      <p>SSPWA (Single Screen Progressive Web App) is a MIT-licensed open source project built with the Vue.js Progressive JavaScript Framework. A good movie experience feels the same on an old, square TV as it does on a new, widescreen TV that has the same screen size. The modern screen may provide an enhanced experience, but you do not loose the quality of the movie in terms of storyline and performance of the actors. A SSPWA will provide a similar experience where the actors in a movie can be compared to the elements on the screen of the app. The app will feel the same regardless of what device you open the app with.</p>
    </div>
    <div class="page-cta">
      <button class="gradient-border" @click="view">View on GitHub</button>
      <button @click="load">Learn More</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'home',
  data() {
    return {
      showHome: true
    }
  },
  methods: {
    view() {
      window.open('https://github.com/laetadevelopment/sspwa','_blank');
    },
    load() {
      this.$emit("load", "learnMore");
    }
  }
}
</script>
