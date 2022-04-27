<template>
  <div v-if="showHome" id="home">
    <div class="page-title">
      <h1>Single Screen Progressive Web App</h1>
    </div>
    <div class="page-content">
      <p>The mission of SSPWA (Single Screen Progressive Web App) is to create a progressive web app experience that feels like interacting with a movie.</p>
    </div>
    <div class="page-cta">
      <button @click="view" class="page-cta bottom-left">View on GitHub</button>
      <button @click="load" class="page-cta bottom-right">Learn More</button>
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
      this.$emit("load", "menu");
      //window.open('https://github.com/laetadevelopment/sspwa','_blank');
    },
    load() {
      this.$emit("load", "learnMore");
    }
  }
}
</script>
