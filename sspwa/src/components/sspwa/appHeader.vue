<template>
  <header>
    <div id="menuButton">
      <button @click="toggleAppMenu">Show Menu</button>
    </div>
    <div id="logo">
      <img @click="home" alt="SSPWA logo" src="../../assets/logo.png">
    </div>
    <div id="appBarButton">
      <button @click="toggleAppBar">Show App Bar</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'appHeader',
  methods: {
    toggleAppMenu() {
      this.$emit("toggle", "appMenu");
    },
    home() {
      this.$emit("load", "home");
    },
    toggleAppBar() {
      this.$emit("toggle", "appBar");
    }
  }
}
</script>

<style scoped>
header {
  width: 100% !important;
  height:  15% !important;
  overflow: hidden !important;
  position: relative;
}
#menuButton {
  width: 40px;
  height: 40px;
  position: absolute;
  left: 0;
  top: 0;
}
#menuButton button {
  width: 100%;
  height: 100%;
  font-size: 0;
  border-radius: 15px;
  background: #0E5FF2;
}
header #logo {
  width: 20%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  cursor: pointer;
}
header #logo img {
  max-width: 100%;
  max-height: 100%;
}
#appBarButton {
  width: 40px;
  height: 40px;
  position: absolute;
  right: 0;
  top: 0;
}
#appBarButton button {
  width: 100%;
  height: 100%;
  font-size: 0;
  border-radius: 15px;
  background: #0E5FF2;
}
</style>
