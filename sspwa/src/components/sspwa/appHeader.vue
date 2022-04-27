<template>
  <header>
    <div id="menuButtons">
      <button style="background: #FF9777;" v-if="!showAppMenu" @click="showMenu">Show Menu</button>
      <button style="background: #007AC7;" v-if="showAppMenu" @click="hideMenu">Hide Menu</button>
    </div>
    <div id="logo">
      <img @click="home" alt="SSPWA logo" src="../../assets/logo.png">
    </div>
    <div id="appBarButtons">
      <button style="background: #FF9777;" v-if="!showAppBar" @click="showBar">Show App Bar</button>
      <button style="background: #007AC7;" v-if="showAppBar" @click="hideBar">Hide App Bar</button>
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
header {
  width: 100% !important;
  height:  20% !important;
  overflow: hidden !important;
  position: relative;
  border-top-left-radius: 15px;
  border-top-right-radius: 15px;
}
#menuButtons {
  width: 50px;
  height: 50px;
  position: absolute;
  left: 20px;
  top: 20px;
}
#menuButtons button {
  width: 100%;
  height: 100%;
  font-size: 0;
  border-radius: 10px;
}
header #logo {
  width: 20%;
  height: 100%;
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
#appBarButtons {
  width: 50px;
  height: 50px;
  position: absolute;
  right: 20px;
  top: 20px;
}
#appBarButtons button {
  width: 100%;
  height: 100%;
  font-size: 0;
  border-radius: 10px;
}
</style>
