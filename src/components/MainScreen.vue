<template>
<main class="section main">
    <button class="next" @click="moveSectionDown"></button>
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
    .next {
        outline: none;
        border: none;
        background: transparent;
        width: 40px;
        height: 70px;
        margin-left: -20px;
        top: 50%;
        margin-top: -35px;
        -webkit-box-shadow: inset 0 0 0 1px #fff;
        box-shadow: inset 0 0 0 1px #fff;
        border-radius: 25px;
        cursor: pointer;
        &::before {
            display: flex;
            content: "";
            width: 8px;
            height: 8px;
            background: #fff;
            margin-left: 10px;
            position: relative;
            top: -20px;
            border-radius: 4px;
            animation-duration: 1.5s;
            animation-iteration-count: infinite;
            animation-name: scroll;
        }
    }
}

@-webkit-keyframes scroll {
    0% {
        opacity: 1;
    }
    100% {
        opacity: 0;
        -webkit-transform: translateY(46px);
        transform: translateY(46px);
    }
}


</style>
