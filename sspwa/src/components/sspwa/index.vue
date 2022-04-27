<template>
  <div id="index">
    <appHeader @toggle="toggle" @load="load" />
    <main>
      <!-- app views go here -->
      <home v-if="showHome" @load="load" />
      <learnMore v-if="showLearnMore" @load="load" />
    </main>
    <appMenu v-if="showAppMenu" />
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
      }
      if (page == 'learnMore') {
        this.showHome = false;
        this.showLearnMore = true;
      }
    }
  }
}
</script>
