<template>
<nav id="navigation">
    <section class="navigation-wrapper">
        <div class="logo-container">
            <a class="logo" @click.prevent="goToSlide(1)"></a>
            <div class="logo-title" v-if="!IS_MOBILE"><h2>Astex</h2><span>group</span></div>
        </div>
        <button v-if="IS_MOBILE" @click.prevent="showOverlay = !showOverlay" class="hamburger hamburger--squeeze" :class="{'is-active': showOverlay}" type="button">
              <span class="hamburger-box">
                <span class="hamburger-inner"></span>
              </span>
        </button>
        <div class="content" :class="{'content--mobile' : IS_MOBILE, 'overlay': showOverlay}">
            <div class="fullscreen-overlay"></div>
            <ul class="contact-list">
                <li class="email"><a href="mailto:info@astex-group.com.ua">info@astex-group.com.ua</a></li>
                <li class="phone">
                    <a class="phone__number" href="tel:+38(057)700-00-00">+38(057) 700-00-00</a>
                    <a class="cta-button" href="#">перезвоните мне!</a>
                </li>
            </ul>
            <ul class="navigation-list">
                <li data-menuanchor="main" :class="{'animated fadeInDown': showOverlay}" class="active"><a href="#main" @click.prevent="goToSlide(1)">Главная</a></li>
                <li data-menuanchor="products" :class="{'animated fadeInDown': showOverlay}"><a href="#products" @click.prevent="goToSlide(2)">Каталог</a></li>
                <li data-menuanchor="about" :class="{'animated fadeInDown': showOverlay}"><a href="#about" @click.prevent="goToSlide(3)">О нас</a></li>
                <li data-menuanchor="promo" :class="{'animated fadeInDown': showOverlay}"><a href="#promo" @click.prevent="goToSlide(4)">Акции</a></li>
                <li data-menuanchor="directions" :class="{'animated fadeInDown': showOverlay}"><a href="#directions" @click.prevent="goToSlide(5)">Направления</a></li>
            </ul>
        </div>

    </section>
</nav>
</template>

<script>
export default {
    name: 'Navigation',
    data() {
        return {
            IS_DESKTOP: window.innerWidth >= 992,
            IS_TABLET: window.innerWidth > 767 && window.innerWidth < 992,
            IS_MOBILE: window.innerWidth <= 767,
            showOverlay: false
        }
    },
    mounted() {
      fadeInListDelay();
    },
    methods: {
        goToSlide(i) {
            $.fn.fullpage.moveTo(i, 0);
            if(this.IS_MOBILE) {
                this.showOverlay = false;
            }
        }
    }
}


function fadeInListDelay() {
    let list = $('.navigation-list').find('li');
    let dotsNav = $('#fp-nav');

    list.each(function(i,e) {
      $(e).css('animation-delay', `${500*i}ms`)
    });

}

</script>

<style lang="scss" scoped>
@import "@/assets/scss/colors.scss";
@import "@/assets/scss/fonts.scss";
@import "@/assets/scss/mixins.scss";
@import "@/assets/scss/media.scss";

ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

#navigation {
    display: flex;
    position: fixed;
    top: 0;
    width: 100%;
    background-color: transparent;
    z-index: 10;
    .navigation-wrapper {
        max-width: 1300px;
        display: flex;
        justify-content: space-between;
        margin: auto;
        width: 100%;
        @media screen and (max-width: 1320px) {
            padding: 0 3%;
        }
        .logo-container {
            width: 130px;
            height: 180px;
            background-color: $red;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            cursor: pointer;
            z-index: 3;
            @include breakpoint(sm) {
                width: 120px;
                height: 150px;
            }
            @include breakpoint(xs) {
                height: 65px;
                background-color: transparent;
            }
            &:hover {
                .logo {
                    background: url("../assets/img/icons/logo-grey.png") center no-repeat;
                    background-size: contain;
                    width: 100px;
                    height: 65px;
                    margin: 0 auto;
                }
                .logo-title {
                    color: $dark-grey;
                }
            }
            .logo {
                background: url("../assets/img/icons/logo-white.png") center no-repeat;
                background-size: contain;
                width: 100px;
                height: 65px;
                margin: 0 auto;
                transition: background .4s ease;
                @include breakpoint(xs) {
                    background: url("../assets/img/icons/logo-red.png") center no-repeat;
                    background-size: contain;
                    width: 90px;
                }
            }
            .logo-title {
                margin-bottom: 20px;
                color: $white;
                font-size: 20px;
                font-family: 'GP-light';
                overflow: hidden;
                transition: color .4s ease;
                h2 {
                    margin: 0 0 0 -20px;
                    font-size: 30px;
                    font-family: 'GP-bold';
                }
                span {
                    margin-right: -45px;
                }
            }
        }
        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            @include breakpoint(xs) {
                flex-direction: row;
                justify-content: flex-end;
                flex: 0 1 120px;
            }
            .fullscreen-overlay {
                top: -100%;
                transition: top 1s ease-in;
                display: block;
                content: '';
                position: fixed;
                height: 100vh;
                background-color: $white;
                z-index: 2;
                left: 0;
                right: 0;
            }
            .contact-list, .navigation-list {
                display: flex;
                list-style: none;
                justify-content: flex-end;
                align-items: center;
                a {
                    font-family: 'GothamPro';
                    font-size: 16px;
                    color: $white;
                }
            }
            .contact-list {
                display: flex;
                flex: 1 1 auto;
                @media screen and (max-width: 850px) {
                    flex-direction: column;
                    justify-content: space-evenly;
                    align-items: flex-end;
                    li a {
                        font-size: 14px;
                        color: $white;
                        &.phone__number {
                            font-size: 16px !important;
                        }
                    }
                    li:first-child.email {
                        margin-right: 0;
                        margin-left: 70px;
                        & a:before {
                            width: 35px;
                            height: 35px;
                            top: -7px;
                        }
                    }
                    li.phone {
                        margin-left: 60px;
                        & a:before {
                            width: 35px;
                            height: 35px;
                            top: 3px;
                        }
                    }
                }
                li {
                    &:first-child {
                        margin-right: 120px;
                    }
                    a {
                        text-decoration: none;
                        display: block;
                        cursor: pointer;
                        position: relative;
                        transition: color 1.2s ease-in;
                        &::before {
                            height: 45px;
                            width: 45px;
                            position: absolute;
                            display: block;
                            content: '';
                            background-position: center;
                            background-repeat: no-repeat;
                            background-size: contain;
                        }
                    }
                    a.cta-button {
                        font-family: 'GP-bold';
                        color: $red;
                        text-align: left;
                    }
                    &.email {
                        a::before {
                            left: -70px;
                            top: -12px;
                            @include bg-icon('../assets/img/icons/svg/message.svg', $red);
                        }
                    }
                    &.phone {
                        a.phone__number {
                            font-size: 20px;
                            &::before {
                                left: -60px;
                                @include bg-icon('../assets/img/icons/svg/phone-call.svg', $red);
                            }
                        }
                    }
                }
            }
            .navigation-list {
                li {
                    margin-right: 20px;
                    &.active {
                        a {color: $red};
                    }
                    &:last-child {
                        margin-right: 0;
                    }
                    a {
                        text-decoration: none;
                        text-transform: uppercase;
                        font-size: 20px;
                        transition: color .4s ease;
                        @include breakpoint(sm) {
                            font-size: 16px;
                        }
                    }
                }
            }
            &.content--mobile {

                .contact-list {
                    display: none;
                }
                .navigation-list {
                    display: none;
                }
            }
            &.overlay {
                .fullscreen-overlay {
                    top: 0;
                }
                .contact-list {
                    z-index: 3;
                    display: block;
                    li a {
                        color: $dark-grey;
                    }
                }
                .navigation-list {
                    display: block;
                    z-index: 3;
                    @include center(x);
                    top: 200px;
                    li {
                        margin-right: 0;
                        margin-bottom: 40px;
                        a{color: $dark-grey;}
                        &.active {
                            a{color: $red;}
                        }
                    }

                }
            }
        }
        .hamburger {
            outline: none;
            z-index: 3;
            transition-duration: 1.2s;
            width: 60px;
            flex: 1;
            &-inner, &-inner::before, &-inner::after {
                width: 60px;
                border-radius: 0;
                height: 4px;
                background-color: $white;
            }
            &-inner::before {
                top: -15px;
            }
            &.hamburger--squeeze.is-active .hamburger-inner::after {
                bottom: 0 !important;
            }
            &-inner::after {
                bottom: -15px;
            }
            &.is-active {
                .hamburger-inner, .hamburger-inner::before, .hamburger-inner::after {
                    background-color: $dark-grey;
                }
            }
        }
    }
    &.short {
        height: 65px;
        background: transparent;
        .logo {
            background: url("../assets/img/icons/logo-red.png") center no-repeat;
            background-size: contain;
            width: 100px;
            height: 60px;
            margin: 0 auto;
        }
        .logo-title {
            display: none;
        }
    }
}
</style>