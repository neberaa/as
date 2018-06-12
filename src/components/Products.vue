<template>
<div class="section products">
    Products
</div>
</template>
<script>
import fullPageMixin from 'vue-fullpage.js/src/fullPageMixin'
export default {
    name: 'Products',
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

.section {
    width: 100%;
    height: 100vh;
}
</style>
