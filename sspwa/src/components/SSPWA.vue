<template>
  <div id="sspwa">
    <div id="content">
      <div id="viewable">
        <div v-if="showInstall" id="intro">
          <img v-if="installApp" @click="install" id="logo" alt="SSPWA logo" src="../assets/logo.png">
          <img v-if="!installApp" @click="load" id="logo" alt="SSPWA logo" src="../assets/logo.png">
        </div>
        <index v-if="loadIndex" />
      </div>
    </div>
  </div>
</template>

<script>
import index from './sspwa/index.vue'

export default {
  name: 'SSPWA',
  components: {
    index
  },
  data() {
    return {
      installApp: null,
      showInstall: true,
      loadIndex: false
    }
  },
  created() {
    window.addEventListener("beforeinstallprompt", e => {
      e.preventDefault();
      this.installApp = e;
    });
    window.addEventListener("appinstalled", () => {
      this.installApp = null;
    });
  },
  methods: {
    async install() {
      this.installApp.prompt();
    },
    load() {
      this.showInstall = false;
      this.loadIndex = true;
    }
  }
}
</script>

<style scoped>
#sspwa {
  width: 100%;
  height: 100%;
}
#content {
  width: 100%;
  height: 100%;
  border: 20px solid #0E5FF2;
  box-sizing: border-box;
}
#viewable {
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 15px;
  background: #FFFFFF;
}
#intro #logo {
  max-width: 50%;
  max-height: 50%;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  cursor: pointer;
}
</style>
