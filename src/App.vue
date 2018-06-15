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
    color: $white;
    font-size: 16px;
}
.section {
  width: 100%;
  height: 100vh;
}

h1 {
  font-family: 'GP-bold';
  text-transform: uppercase;
  font-size: 36px;
  @include breakpoint(sm) {
    font-size: 48px;
  }
}
h3 {
  font-family: 'GP-light';
  font-size: 18px;
  @include breakpoint(sm) {
    font-size: 24px;
  }
}
h4 {
    font-family: 'GP-light';
    font-size: 16px;
    margin: 0;
    @include breakpoint(sm) {
        font-size: 20px;
    }
}
p.small {
    font-size: 12px;
    margin: 0;
    @include breakpoint(sm) {
        font-size: 14px;
    }
}
</style>
