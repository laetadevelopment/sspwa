<template>
  <header>
    <div id="menuButtons">
      <button v-if="!showAppMenu" @click="showMenu">Show Menu</button>
      <button v-if="showAppMenu" @click="hideMenu">Hide Menu</button>
    </div>
    <div id="logo">
      <img @click="home" alt="SSPWA logo" src="../../assets/logo.png">
    </div>
    <div id="appBarButtons">
      <button v-if="!showAppBar" @click="showBar">Show App Bar</button>
      <button v-if="showAppBar" @click="hideBar">Hide App Bar</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'appHeader',
  data() {
    return {
      showAppMenu: false,
      showAppBar: false
    }
  },
  methods: {
    showMenu() {
      this.showAppMenu = true;
      this.$emit("toggle", "appMenu");
    },
    hideMenu() {
      this.showAppMenu = false;
      this.$emit("toggle", "appMenu");
    },
    home() {
      this.$emit("load", "home");
    },
    showBar() {
      this.showAppBar = true;
      this.$emit("toggle", "appBar");
    },
    hideBar() {
      this.showAppBar = false;
      this.$emit("toggle", "appBar");
    }
  }
}
</script>

<style scoped>
header #logo img {
  max-width: 10%;
  max-height: 10%;
  cursor: pointer;
}
</style>
