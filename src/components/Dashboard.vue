<template>
<div class="wrapper">
    <navigation></navigation>
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
                navigation: true,
                navigationTooltips: ['Главная', 'Каталог', 'О нас', 'Акции', 'Направления'],
                menu: '#navigation',
                anchors: ['main', 'products', 'about', 'promo', 'directions'],
                showActiveTooltip: true,
                scrollingSpeed: 1000
            },
        }
    },
    methods: {
        goToSlide(i) {
            $.fn.fullpage.moveTo(i, 0);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "@/assets/scss/mixins.scss";
@import "@/assets/scss/colors.scss";

</style>
