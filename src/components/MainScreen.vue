<template>
<main class="section main">
    <section class="main__content">
        <div class="title-container">
            <h1 class="title">Металлические двери</h1>
            <h3 class="description">Производство входных металлических дверей. Мы будем рады сотрудничеству.</h3>
        </div>
        <div class="cta-container">
            <button class="next" @click="moveSectionDown"></button>
        </div>
        <div class="tips-container">
            <div class="tip">
                <i class="tip__icon"></i>
                <div class="tip-content">
                    <h4 class="tip__title">Надежность</h4>
                    <p class="small tip__desc">Производство входных металлических дверей. Мы будем рады сотрудничеству.</p>
                </div>
            </div>
            <div class="tip">
                <i class="tip__icon"></i>
                <div class="tip-content">
                    <h4 class="tip__title">Доступность</h4>
                    <p class="small tip__desc">Производство входных металлических дверей. Мы будем рады сотрудничеству.</p>
                </div>
            </div>
            <div class="tip">
                <i class="tip__icon"></i>
                <div class="tip-content">
                    <h4 class="tip__title">Гарантия качества</h4>
                    <p class="small tip__desc">Производство входных металлических дверей. Мы будем рады сотрудничеству.</p>
                </div>
            </div>
        </div>
    </section>

</main>
</template>

<script>
import fullPageMixin from 'vue-fullpage.js/src/fullPageMixin'
import 'jquery-parallax.js/parallax.min'
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

.main {
    background: url("../assets/img/header-bg.jpg") center no-repeat;
    background-size: cover;
    &__content {
        padding: 0 3%;
        overflow: hidden;
        display: flex;
        flex-direction: column;
        height: 70vh;
        justify-content: space-around;
        @include breakpoint(sm) {
            justify-content: space-evenly;
            margin-top: 100px;
        }
        @include breakpoint(1300) {
            padding: 0;
            max-width: 1300px;
            margin: auto;
        }
        .title-container {
            position: relative;
            text-align: center;
            @include breakpoint(md) {
                text-align: left;
            }
            h3 {
                margin-left: 10px;
                margin-right: 10px;
            }
            &::after {
                display: block;
                content: '';
                width: 1px;
                height: 70px;
                background-color: red;
                @include center(x);
                bottom: -80px;
                @include breakpoint(sm) {
                    display: none;
                }
            }
        }
        .cta-container {
            display: flex;
            justify-content: center;
            @include breakpoint(sm) {
            }
            .next {
                outline: none;
                border: none;
                background: transparent;
                width: 40px;
                height: 70px;
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
        .tips-container {
            display: none;
            @include breakpoint(sm) {
                display: flex;
                justify-content: space-between;
            }
            .tip {
                background-color: rgba(250,25,25,.55);
                display: flex;
                justify-content: space-around;
                align-items: center;
                max-width: 220px;
                padding: 10px;
                @include breakpoint(md) {
                    max-width: 350px;
                    padding: 20px;
                }
                &__icon {
                    display: block;
                    width: 40px;
                    height: 40px;
                    @include bg-icon('../assets/img/icons/svg/check-symbol.svg', $white);
                    margin-right: 20px;
                }
                &-content {
                    max-width: 150px;
                    text-align: left;
                    @include breakpoint(md) {
                        max-width: 350px;
                    }
                    .tip__title {
                        margin-bottom: 10px;
                    }
                }
            }
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
