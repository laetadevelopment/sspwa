<template>
  <div id="appBar">
    <a class="github-button" href="https://github.com/sponsors/laetadevelopment" data-color-scheme="no-preference: dark; light: light; dark: dark;" data-icon="octicon-heart" data-size="large" aria-label="Sponsor @laetadevelopment on GitHub">Sponsor</a>
    <a class="github-button" href="https://github.com/laetadevelopment/sspwa" data-color-scheme="no-preference: dark; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star the SSPWA Template on GitHub">Star</a>
    <a class="github-button" href="https://github.com/laetadevelopment/sspwa/archive/HEAD.zip" data-color-scheme="no-preference: dark; light: light; dark: dark;" data-size="large" aria-label="Download the SSPWA Template on GitHub">Download</a>
  </div>
</template>

<script>
export default {
  name: 'appBar',
  mounted() {
    const plugin = document.createElement("script");
    plugin.setAttribute(
      "src",
      "//buttons.github.io/buttons.js"
    );
    plugin.async = true;
    document.head.appendChild(plugin);
  }
}
</script>

<style scoped>
#appBar {
  width: 100%;
  height: 10%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  position: absolute;
  bottom: 0;
  border-bottom-left-radius: 15px;
  border-bottom-right-radius: 15px;
  background: rgba(62, 140, 132, 50%);
}
#appBar span {
  display: inline-flex;
  align-items: center;
}
</style>
