<template>
<div class="section products">
    <h2>Наши двери</h2>
    <div class="slide">
        <div class="slide__content">
            <div class="item">
                <div class="item__body">
                    <h3 class="title">Пакет <span>"Эконом"</span></h3>
                    <div class="image" style="background-image: url('../assets/img/door1.png')"></div>
                    <span class="desc">Металлическая дверь базовой комплектации: ручка-планка, один замок, металл 1,2мм, внутренняя накладка-ДСП 16мм</span>
                </div>
                <div class="item__footer">
                    <div class="price"></div>
                    <div class="cta-button"></div>
                </div>
            </div>
            <div class="item">
                <div class="item__body">
                    <h3 class="title">Пакет <span>"Эконом"</span></h3>
                    <div class="image"></div>
                    <span class="desc">Металлическая дверь базовой комплектации: ручка-планка, один замок, металл 1,2мм, внутренняя накладка-ДСП 16мм</span>
                </div>
                <div class="item__footer">
                    <div class="price"></div>
                    <div class="cta-button"></div>
                </div>
            </div>
        </div>
    </div>
    <div class="slide">
        <div class="slide__content">
            <div class="item">
                <div class="item__body">
                    <h3 class="title">Пакет <span>"Эконом"</span></h3>
                    <div class="image"></div>
                    <span class="desc">Металлическая дверь базовой комплектации: ручка-планка, один замок, металл 1,2мм, внутренняя накладка-ДСП 16мм</span>
                </div>
                <div class="item__footer">
                    <div class="price"></div>
                    <div class="cta-button"></div>
                </div>
            </div>
            <div class="item">
                <div class="item__body">
                    <h3 class="title">Пакет <span>"Эконом"</span></h3>
                    <div class="image"></div>
                    <span class="desc">Металлическая дверь базовой комплектации: ручка-планка, один замок, металл 1,2мм, внутренняя накладка-ДСП 16мм</span>
                </div>
                <div class="item__footer">
                    <div class="price"></div>
                    <div class="cta-button"></div>
                </div>
            </div>
        </div>
    </div>
    <div class="slide">
        <div class="slide__content">
            <div class="item">
                <div class="item__body">
                    <h3 class="title">Пакет <span>"Эконом"</span></h3>
                    <div class="image"></div>
                    <span class="desc">Металлическая дверь базовой комплектации: ручка-планка, один замок, металл 1,2мм, внутренняя накладка-ДСП 16мм</span>
                </div>
                <div class="item__footer">
                    <div class="price"></div>
                    <div class="cta-button"></div>
                </div>
            </div>
            <div class="item">
                <div class="item__body">
                    <h3 class="title">Пакет <span>"Эконом"</span></h3>
                    <div class="image"></div>
                    <span class="desc">Металлическая дверь базовой комплектации: ручка-планка, один замок, металл 1,2мм, внутренняя накладка-ДСП 16мм</span>
                </div>
                <div class="item__footer">
                    <div class="price"></div>
                    <div class="cta-button"></div>
                </div>
            </div>
        </div>
    </div>
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
    },
    methods: {
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
    @import "@/assets/scss/mixins.scss";
    @import "@/assets/scss/media.scss";
    @import "@/assets/scss/colors.scss";

.section {
    width: 100%;
    height: 100vh;
    background-color: grey;
    h2 {
        @include breakpoint(sm) {
            padding-top: 200px;
            margin: 0;
        }
    }
    .slide {
        @include breakpoint(sm) {
            margin-top: -200px;
        }
    }
    .slide__content {
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        .item {
            width: 320px;
            max-height: 650px;
            background-color: hsla(0,0%,100%,.46);
            box-shadow: 3px 5px 7px 0 rgba(70,70,71,.75);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: all .3s ease-in-out;
            cursor: pointer;
            &:hover {
                box-shadow: 13px 15px 7px 0 rgba(70,70,71,.75);
                transform: translate(-10px,-20px);
            }
            .image {
                background-position: center;
                background-repeat: no-repeat;
                background-size: contain;
            }
        }
    }
}
</style>
