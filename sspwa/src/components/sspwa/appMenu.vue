<template>
  <div id="appMenu">
    <button @click="home">Home</button>
    <button @click="learnMore">Learn More</button>
    <button @click="view">View on GitHub</button>
  </div>
</template>

<script>
export default {
  name: 'appMenu',
  methods: {
    home() {
      this.$emit("toggle", "appMenu");
      this.$emit("load", "home");
    },
    learnMore() {
      this.$emit("toggle", "appMenu");
      this.$emit("load", "learnMore");
    },
    view() {
      this.$emit("toggle", "appMenu");
      window.open('https://github.com/laetadevelopment/sspwa','_blank');
    }
  }
}
</script>

<style scoped>
#appMenu {
  width: 100%;
  height: 85%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  position: absolute;
  bottom: 0;
  border-bottom-left-radius: 15px;
  border-bottom-right-radius: 15px;
  background: rgba(0, 0, 0, 90%);
}
#appMenu button {
  height: 50px;
  width: 100px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 5px;
}
</style>
