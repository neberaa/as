<template>
<main class="section main">
    <button class="next" @click="moveSectionDown">Next</button>
    Main screen
</main>
</template>

<script>
import fullPageMixin from 'vue-fullpage.js/src/fullPageMixin'
export default {
    name: 'Main',
    mixins: [fullPageMixin],
    data() {
        return {
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "@/assets/scss/mixins.scss";
@import "@/assets/scss/colors.scss";
@import "@/assets/scss/media.scss";

.section {
    width: 100%;
    height: 100vh;
}

.main {
    background: url("../assets/img/header-bg.jpg") center no-repeat;
    background-size: cover;
}


</style>
