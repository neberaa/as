<template>
<full-page :options="options">
    <main-screen></main-screen>
    <products></products>
</full-page>
</template>
<script>
import 'fullpage.js'
import FullPage from 'vue-fullpage.js'
import fullPageMixin from 'vue-fullpage.js/src/fullPageMixin'
import MainScreen from '@/components/MainScreen'
import Products from '@/components/Products'
export default {
    name: 'Dashboard',
    mixins: [fullPageMixin],
    components: {
        FullPage,
        MainScreen,
        Products
    },
    data() {
        return {
            options: {
                navigation: true,
                navigationTooltips: ['Main', 'Our products'],
                showActiveTooltip: true,
                scrollingSpeed: 1000
            },
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "@/assets/scss/mixins.scss";
@import "@/assets/scss/colors.scss";

</style>
