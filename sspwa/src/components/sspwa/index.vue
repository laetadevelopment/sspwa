<template>
  <div id="index">
    <appHeader @load="load" @toggle="toggle" />
    <main>
      <!-- app views go here -->
      <home v-if="showHome" @load="load" />
      <learnMore v-if="showLearnMore" @load="load" @toggle="toggle" />
    </main>
    <appMenu v-if="showAppMenu" @load="load" @toggle="toggle" />
    <appBar v-if="showAppBar" />
  </div>
</template>

<script>
import appHeader from './appHeader.vue'
import home from './views/home.vue'
import learnMore from './views/learnMore.vue'
import appMenu from './appMenu.vue'
import appBar from './appBar.vue'

export default {
  name: 'index',
  components: {
    appHeader,
    home,
    learnMore,
    appMenu,
    appBar
  },
  data() {
    return {
      showHome: true,
      showLearnMore: false,
      showAppMenu: false,
      showAppBar: false
    }
  },
  methods: {
    toggle(component) {
      if (component == 'appMenu') {
        if (!this.showAppMenu) {
          this.showAppMenu = true;
        } else {
          this.showAppMenu = false;
        }
      }
      if (component == 'appBar') {
        if (!this.showAppBar) {
          this.showAppBar = true;
        } else {
          this.showAppBar = false;
        }
      }
    },
    // TODO: refactor page loading logic
    load(page) {
      if (page == 'home') {
        this.showLearnMore = false;
        this.showHome = true;
        if (this.showAppMenu) {
          this.showAppMenu = false;
        }
      }
      if (page == 'learnMore') {
        this.showHome = false;
        this.showLearnMore = true;
        if (this.showAppMenu) {
          this.showAppMenu = false;
        }
      }
    }
  }
}
</script>

<style>
#index {
  width: 100%;
  height: 100%;
  position: relative;
}
main {
  width: 100% !important;
  height: 85% !important;
  overflow: hidden !important;
  display: flex;
  border-bottom-left-radius: 15px;
  border-bottom-right-radius: 15px;
}
.page-title {
  height: 10%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.page-title h1 {
  margin: 0;
  font-size: 4.75vw;
}
.page-content {
  height: 80%;
  overflow: hidden;
  display: flex;
  flex-wrap: wrap;
  align-content: center;
}
.page-content h2 {
  margin: 0;
  font-size: 1em;
}
.page-content p {
  margin: 0;
}
.page-cta {
  height: 10%;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}
.page-cta button {
  width: 150px;
  max-width: 47.5%;
  height: 50px;
  max-height: 100%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border-radius: 15px;
  text-align: center;
}
</style>
