<template>
<ul id="navigation">
    <li data-menuanchor="main" class="active"><a href="#main" @click.prevent="goToSlide(1)">Main</a></li>
    <li data-menuanchor="products"><a href="#products" @click.prevent="goToSlide(2)">Products</a></li>
</ul>
</template>

<script>
export default {
    name: 'Navigation',
    data() {
        return {}
    },
    methods: {
        goToSlide(i) {
            $.fn.fullpage.moveTo(i, 0);
        }
    }
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/colors.scss";

#navigation {
    display: flex;
    position: fixed;
    top: 0;
    width: 100%;
    height: 60px;
    background-color: $grey;
    z-index: 10;
}
</style>