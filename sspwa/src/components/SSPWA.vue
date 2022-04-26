<template>
  <div id="sspwa">
    <div id="content">
      <div>
        <img @click="install" id="logo" alt="SSPWA logo" src="../assets/logo.png">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SSPWA',
  data() {
    return {
      deferredPrompt: null
    }
  },
  created() {
    window.addEventListener("beforeinstallprompt", e => {
      e.preventDefault();
      this.deferredPrompt = e;
    });
    window.addEventListener("appinstalled", () => {
      this.deferredPrompt = null;
    });
  },
  methods: {
    async install() {
      console.log('test');
      this.deferredPrompt.prompt();
    }
  }
}
</script>

<style scoped>
#sspwa {
  width:  100%;
  height:  100%;
}
#content {
  width: 90%;
  height: 90%;
  position: absolute;
  top: 5%;
  left: 5%;
  background: #FFFFFF;
}
#logo {
  max-width: 50%;
  max-height: 50%;
  position: absolute;
  left: 25%;
  top: 25%;
  cursor: pointer;
}
</style>
