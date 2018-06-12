<template>
    <div class="section">
        <button class="next" @click="moveSectionDown">Next</button>
        Main screen
    </div>
</template>
<script>
import fullPageMixin from 'vue-fullpage.js/src/fullPageMixin'
export default {
    name: 'Section1',
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
