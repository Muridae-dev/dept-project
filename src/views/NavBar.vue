<template>
    <nav class="nav-bar" :style="navHidden && !menuActive ? {top : '-115px'} : null">
        <div class="nav-logo-container">
            <div class="letter-container" v-for="(vectorLetter, index) in vectorLetters" :key="vectorLetter">
                <img :src="require(`../assets/dept-vector-white/letter${vectorLetter}.svg`)" :class="index == 4 ? 'copy-right-logo' : 'svg-letters'"/>
            </div>
        </div>

        

        <section class="site-link-container">
            <a v-for="siteLink in siteLinks" :key="siteLink.title" :src="siteLink.link" 
            class="site-links"
            :style="[siteLink.isActive ? {'text-decoration' : 'underline'} : null,
            menuActive ? {'opacity' : '0'} : null]">
                {{siteLink.title}}
            </a>

            <div class="menu-btn" @click="menuActive = !menuActive">
                <img :src="require('../assets/dept-vector-white/menu-btn.svg')"
                :style="!menuActive ? {opacity:'1'} : {opacity:'0'}"/>
                <img :src="require('../assets/misc/closeX.svg')" style="position:absolute; right:6px;"
                :style="menuActive ? {opacity:'1'} : {opacity:'0'}"/>
            </div>

        </section>

        
    </nav>
    <Menu :menuActive="menuActive"/>
</template>

<script>
import Menu from "../components/Menu.vue"

export default {
    name: "NavBar",
    components: {
        Menu
    },
    props: ["siteLinks", "vectorLetters"],
    data() {
        return {
            newScrollY: 0,
            oldScrollY: 0,
            navHidden: false,

            menuActive: false,
        }
    },
    created () {
        window.addEventListener('scroll', (e) => {
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
    destroyed () {
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


    /* -------------- LOGO -------------- */
    .letter-container {
        position:relative;
        float:left;
        height:22px;
    }

    .copy-right-logo {
        position:relative;
        bottom:0px;
        height:7px;
        width:auto;
    }

    .svg-letters {
        height:100%;
        width:auto;
        margin-left:1px;
    }
    /* -------------- END -------------- */

    /* -------------- LINKS -------------- */
    .site-link-container {
        float:right;
        position:relative;
        top:50%;
        right:5%;
        transform:translateY(-50%);
    }

    .site-links {
        padding:16px;
        transition:opacity 1s;
    }

    .menu-btn {
        float:right;
        padding-left:64px;
        cursor:pointer;
        position:relative;

    }

    @media screen and (max-width: 1000px) {
        .site-links {
            display:none;
        }
    }
    /* -------------- END -------------- */
</style>