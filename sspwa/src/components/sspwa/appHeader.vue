<template>
  <header>
    <div id="menuButton">
      <button class="background-animation" @click="toggleAppMenu" />
    </div>
    <div id="logo">
      <img @click="home" alt="SSPWA logo" src="../../assets/logo.svg">
    </div>
    <div id="appBarButton">
      <button class="background-animation" @click="toggleAppBar" />
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
  width: 100%;
  height:  15%;
  position: relative;
}
#menuButton {
  width: 40px;
  height: 40px;
  position: absolute;
  left: 10px;
  top: 10px;
}
#menuButton button {
  width: 100%;
  height: 100%;
  border-radius: 40px;
}
header #logo {
  height: 100%;
  position: absolute;
  left: 50%;
  top: 5px;
  transform: translate(-50%, 0%);
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
  right: 10px;
  top: 10px;
}
#appBarButton button {
  width: 100%;
  height: 100%;
  border-radius: 40px;
}
</style>
