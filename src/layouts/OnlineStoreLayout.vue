<template>
    <section>
        <!-- Header -->
        <header>
            <!-- Header desktop -->
            <div class="wrap-menu-desktop" v-bind:class="{'fix-menu-desktop':(toggleFixedDesktopMenu || currentPage != 'home')}">
                <nav class="limiter-menu-desktop container">
                    <!-- Logo desktop -->
                    <router-link to="/" class="logo">
                        <img src="@/assets/images/icons/logo-01.png" alt="IMG-LOGO" @click="navChange('home')">
                    </router-link>
                    <!-- Menu desktop -->
                    <div class="menu-desktop">
                        <ul class="main-menu">
                            <li v-bind:class="{'active-menu':currentPage=='home'}" v-on:click="navChange('home')">
                                <router-link to="/">Home</router-link>
                            </li>
                            <li v-bind:class="{'active-menu':currentPage=='shop'}" v-on:click="navChange('shop')">
                                <router-link to="/shop">Shop</router-link>
                            </li>
                            <li v-bind:class="{'active-menu':currentPage=='about'}" v-on:click="navChange('about')">
                                <router-link to="/about">About</router-link>
                            </li>
                            <li v-bind:class="{'active-menu':currentPage=='contact'}" v-on:click="navChange('contact')">
                                <router-link to="/contact">Contact</router-link>
                            </li>
                        </ul>
                    </div>
                    <!-- Icon header -->
                    <div class="wrap-icon-header flex-w flex-r-m">
                        <router-link to="/shop/shopping-cart" class="icon-header-item cl2 hov-cl1 trans-04 p-l-22 p-r-11 icon-header-noti" data-notify="2">
                            <i class="fa fa-shopping-cart" aria-hidden="true"></i>
                        </router-link>
                        <router-link to="/shop/wishlist" class="dis-block icon-header-item cl2 hov-cl1 trans-04 p-l-22 p-r-11 icon-header-noti" data-notify="0">
                            <i class="fa fa-heart-o" aria-hidden="true"></i>
                        </router-link>
                    </div>
                </nav>
            </div>
            <!-- Header Mobile -->
            <div class="wrap-header-mobile" v-if="toggleMobileMenu">
                <!-- Logo moblie -->
                <div class="logo-mobile">
                    <router-link to="/"><img src="@/assets/images/icons/logo-01.png" alt="IMG-LOGO"></router-link>
                </div>
                <!-- Icon header -->
                <div class="wrap-icon-header flex-w flex-r-m m-r-15">
                    <router-link to="/shop/shopping-cart" class="icon-header-item cl2 hov-cl1 trans-04 p-r-11 p-l-10 icon-header-noti" data-notify="2">
                        <i class="fa fa-shopping-cart" aria-hidden="true"></i>
                    </router-link>
                    <router-link to="/shop/wishlist" class="dis-block icon-header-item cl2 hov-cl1 trans-04 p-r-11 p-l-10 icon-header-noti" data-notify="0">
                        <i class="fa fa-heart-o" aria-hidden="true"></i>
                    </router-link>
                </div>
                <!-- Button show menu -->
                <div class="btn-show-menu-mobile hamburger hamburger--squeeze" v-bind:class="{'is-active':hamburgerStatus}" @click="toggleHamburger()">
                    <span class="hamburger-box">
                        <span class="hamburger-inner"></span>
                    </span>
                </div>
            </div>
            <!-- Menu Mobile -->
            <div class="menu-mobile" v-if="hamburgerStatus">
                <ul class="main-menu-m">
                    <li>
                        <router-link to="/">Home</router-link>
                    </li>
                    <li>
                        <router-link to="shop">Shop</router-link>
                    </li>
                    <li>
                        <router-link to="about">About</router-link>
                    </li>
                    <li>
                        <router-link to="contact">Contact</router-link>
                    </li>
                </ul>
            </div>
        </header>
        <!-- Main Content -->
        <router-view></router-view>
        <!-- Footer -->
        <footer class="bg3 p-t-75 p-b-32">
            <div class="container">
                <div class="row">
                    <div class="col-sm-6 col-lg-4 p-b-50">
                        <h4 class="stext-301 cl0 p-b-30">
                            Categories
                        </h4>
                        <ul>
                            <li class="p-b-10">
                                <a href="#" class="stext-107 cl7 hov-cl1 trans-04">
                                    Women
                                </a>
                            </li>
                            <li class="p-b-10">
                                <a href="#" class="stext-107 cl7 hov-cl1 trans-04">
                                    Men
                                </a>
                            </li>
                            <li class="p-b-10">
                                <a href="#" class="stext-107 cl7 hov-cl1 trans-04">
                                    Shoes
                                </a>
                            </li>
                            <li class="p-b-10">
                                <a href="#" class="stext-107 cl7 hov-cl1 trans-04">
                                    Watches
                                </a>
                            </li>
                        </ul>
                    </div>
                    <div class="col-sm-6 col-lg-4 p-b-50">
                        <h4 class="stext-301 cl0 p-b-30">
                            Help
                        </h4>
                        <ul>
                            <li class="p-b-10">
                                <a href="#" class="stext-107 cl7 hov-cl1 trans-04">
                                    Track Order
                                </a>
                            </li>
                            <li class="p-b-10">
                                <a href="#" class="stext-107 cl7 hov-cl1 trans-04">
                                    Returns
                                </a>
                            </li>
                            <li class="p-b-10">
                                <a href="#" class="stext-107 cl7 hov-cl1 trans-04">
                                    Shipping
                                </a>
                            </li>
                            <li class="p-b-10">
                                <a href="#" class="stext-107 cl7 hov-cl1 trans-04">
                                    FAQs
                                </a>
                            </li>
                        </ul>
                    </div>
                    <div class="col-sm-6 col-lg-4 p-b-50">
                        <h4 class="stext-301 cl0 p-b-30">
                            GET IN TOUCH
                        </h4>
                        <p class="stext-107 cl7 size-201">
                            Any questions? Let us know in store at 8th floor, 379 Hudson St, New York, NY 10018 or call us on (+1) 96 716 6879
                        </p>
                        <div class="p-t-27">
                            <a href="#" class="fs-18 cl7 hov-cl1 trans-04 m-r-16">
                                <i class="fa fa-facebook"></i>
                            </a>
                            <a href="#" class="fs-18 cl7 hov-cl1 trans-04 m-r-16">
                                <i class="fa fa-instagram"></i>
                            </a>
                            <a href="#" class="fs-18 cl7 hov-cl1 trans-04 m-r-16">
                                <i class="fa fa-pinterest-p"></i>
                            </a>
                        </div>
                    </div>
                </div>
                <div class="p-t-40">
                    <div class="flex-c-m flex-w p-b-18">
                        <a href="#" class="m-all-1">
                            <img src="@/assets/images/icons/icon-pay-01.png" alt="ICON-PAY">
                        </a>
                        <a href="#" class="m-all-1">
                            <img src="@/assets/images/icons/icon-pay-02.png" alt="ICON-PAY">
                        </a>
                        <a href="#" class="m-all-1">
                            <img src="@/assets/images/icons/icon-pay-03.png" alt="ICON-PAY">
                        </a>
                    </div>
                    <p class="stext-107 cl6 txt-center">
                        Copyright &copy; 2019 All rights reserved
                    </p>
                </div>
            </div>
        </footer>
        <!-- Back to top -->
        <div class="btn-back-to-top" v-show="toggleBtnTop" @click="scrollToTop()">
            <span class="symbol-btn-back-to-top">
                <i class="fa fa-chevron-up" aria-hidden="true"></i>
            </span>
        </div>
    </section>
</template>
<script>
export default {
    name: "OnlineStoreLayout",
    data() {
        return {
            toggleBtnTop: false,
            toggleFixedDesktopMenu: false,
            toggleMobileMenu: true,
            hamburgerStatus: false,
            currentPage: ""
        }
    },
    methods: {
        handleScroll(event) {
            let wh = window.innerHeight / 2;
            let sp = window.scrollY;
            if (sp > wh) {
                this.toggleBtnTop = true;
            } else {
                this.toggleBtnTop = false;
            }
            if (sp > 40) {
                this.toggleFixedDesktopMenu = true;
            } else {
                this.toggleFixedDesktopMenu = false;
            }
        },
        scrollToTop() {
            window.scroll({
                top: 0,
                left: 0,
                behavior: 'smooth'
            });
        },
        handleresize() {
            let winWdth = window.innerWidth;
            if (winWdth >= 992) {
                this.toggleMobileMenu = false;
                this.hamburgerStatus = false;
            } else {
                this.toggleMobileMenu = true;
            }
        },
        toggleHamburger() {
            this.hamburgerStatus = !this.hamburgerStatus;
        },
        navChange(currentNav) {
            this.currentPage = currentNav;
        }
    },
    created() {
        let routeName = this.$route.name;
        if (routeName == "shophome" || routeName == "productdetail" || routeName == "shoppingcart" || routeName == "wishlist") {
            routeName = "shop"
        }
        this.currentPage = routeName;
        window.addEventListener("scroll", this.handleScroll);
        window.addEventListener("resize", this.handleresize);
        this.handleScroll();
    },
    destroyed() {
        window.removeEventListener("scroll", this.handleScroll);
        window.removeEventListener("resize", this.handleresize);
    }
}
</script>