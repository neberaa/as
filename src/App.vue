<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
    name: 'App',
    data() {
        return {
        }
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/colors.scss";
@import "@/assets/scss/mixins.scss";
@import "@/assets/scss/media.scss";

* {
  box-sizing: border-box;
}
#app {
    font-family: 'GothamPro', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: $dark-grey;
    font-size: 16px;
}
</style>
