<template>
    <nav class="nav-bar" :style="navHidden && !menuActive ? {top : '-115px'} : null">
        <div class="nav-logo-container">
            <DeptLogo />
        </div>

        <section class="site-link-container">
            <SiteLinks />

            <!------------- MENU BUTTON ------------->
            <div class="menu-btn" @click="menuActive = !menuActive">
                <img :src="require('../assets/dept-vector-white/menu-btn.svg')"
                :style="!menuActive ? {opacity:'1'} : {opacity:'0'}"/>
                <img :src="require('../assets/misc/closeX.svg')" style="position:absolute; right:6px;"
                :style="menuActive ? {opacity:'1'} : {opacity:'0'}"/>
            </div>
            <!------------- MENU BUTTON END ------------->
        </section>
    </nav>

    <Menu :menuActive="menuActive"/>
</template>

<script>
import Menu from "../components/Menu.vue"
import DeptLogo from "../components/DeptLogo.vue"
import SiteLinks from "../components/SiteLinks.vue"

export default {
    name: "NavBar",
    components: {
        Menu,
        DeptLogo,
        SiteLinks
    },
    data() {
        return {
            // THESE THREE ARE USED FOR HIDING THE MENU ON SCROLL DOWN
            newScrollY: 0,
            oldScrollY: 0,
            navHidden: false,

            // THIS IS USED TO SHOW/HIDE THE BIG MENU
            menuActive: false,
        }
    },
    created () {
        // EVENT LISTENER TO HIDE MENU ON SCROLLING DOWN & SHOW ON SCROLL UP
        window.addEventListener('scroll', (e) => {
            // GET THE NEW SCROLL VALUE
            this.newScrollY = window.pageYOffset;

            // IF WE'VE SCROLLED PASSED THE NAV:S HEIGHT
            // AND THE NEW SCROLL IS LARGER THAN THE OLD SCROLL
            // AKA WE ARE SCROLLING DOWN
            if(window.pageYOffset > 115 && this.newScrollY > this.oldScrollY) {
                // WE HIDE THE NAV
                this.navHidden = true;
            }

            // VICE VERSA
            else {
                this.navHidden = false;
            }

            // UPDATE OLD SCROLL AT THE END TO COMPARE AFTER NEXT SCROLL
            this.oldScrollY = window.pageYOffset;
        });
    },
    destroyed () {
        // REMOVES EVENTLISTENER WHEN CLOSING THE APP
        window.removeEventListener('scroll', (e) => {
            this.newScrollY = window.pageYOffset;
            if(window.pageYOffset > 115 && this.newScrollY > this.oldScrollY) {
                this.navHidden = true;
            }

            else {
                this.navHidden = false;
            }

            this.oldScrollY = window.pageYOffset;
        });
    },
}
</script>

<style>

    /* -------------- GENERAL -------------- */
    .nav-bar {
        position:fixed;
        top:0;
        height: 115px;
        width:100vw;
        color:white;
        transition:top 0.5s;

        z-index: 4;
        
        background: #121212;
    }

    .nav-logo-container {
        height:22px;

        position:relative;
        float:left;
        top:50%;
        left:5%;
        transform:translateY(-50%);
       
    }
    /* -------------- END -------------- */
</style>