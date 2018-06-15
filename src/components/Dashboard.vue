<template>
<div class="wrapper">
    <navigation :class="{'short': hideNavBar}"></navigation>
    <full-page :options="options">
        <main-screen></main-screen>
        <products></products>
        <about></about>
        <promo></promo>
        <directions></directions>
    </full-page>
</div>
</template>
<script>
import 'fullpage.js'
import FullPage from 'vue-fullpage.js'
import fullPageMixin from 'vue-fullpage.js/src/fullPageMixin'
import MainScreen from '@/components/MainScreen'
import Products from '@/components/Products'
import Navigation from '@/components/Navigation'
import About from '@/components/About'
import Promo from '@/components/Promo'
import Directions from '@/components/Directions'

export default {
    name: 'Dashboard',
    mixins: [fullPageMixin],
    components: {
        FullPage, MainScreen, Products, Navigation, About, Promo, Directions
    },
    data() {
        return {
            options: {
                navigation: false,
                navigationTooltips: ['Главная', 'Каталог', 'О нас', 'Акции', 'Направления'],
                menu: '#navigation',
                anchors: ['main', 'products', 'about', 'promo', 'directions'],
                showActiveTooltip: false,
                scrollingSpeed: 1000,
                onLeave: this.onLeave
            },
            hideNavBar: false
        }
    },
    methods: {
        onLeave(index, slideIndex, direction) {
            if (index == 1 && slideIndex == 2 && direction == 'down'){
                this.hideNavBar = true;
            } if (index == 2 && slideIndex == 1 && direction == 'up') {
                this.hideNavBar = false;
            }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "@/assets/scss/mixins.scss";
@import "@/assets/scss/colors.scss";

</style>
