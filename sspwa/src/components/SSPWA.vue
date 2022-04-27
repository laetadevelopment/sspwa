<template>
  <div id="sspwa">
    <div id="content">
      <div class="viewable">
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
  width: 100%;
  height: 100%;
  border: 20px solid #0E5FF2;
  box-sizing: border-box;
}
.viewable {
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 15px;
  background: #FFFFFF;
}
#logo {
  max-width: 50%;
  max-height: 50%;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  cursor: pointer;
}
</style>
