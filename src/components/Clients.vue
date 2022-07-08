<template>
    <section class="clients-container">
        <header class="clients-header">
            Clients
        </header>
        <article class="clients-article">
            We value a great working relationship with our clients above all else. It's why they often come to our parties. It's also why we're able to challenge and inspire 
            them to reach for the stars.
        </article>
        <div class="logo-flex-container">
            <!-- Here we loop through all the logos imported from the folder "../assets/big-logos" -->
            <!-- Look @ methods -> importAll(r) & async created () -> this.logos, below -->
            <div v-for="logo in logos" :key="logo.src" class="clients-logo-container">
                <img class="logo-img" :src="logo.src" />
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "Clients",
    data() {
        return {
            logos: [],
        }
        
    },
    async created() {
        // PUTTING ALL IMPORTED IMAGES INTO "LOGOS" ARRAY
        this.logos = await this.importAll(require.context('../assets/big-logos', false, /\.(png|jpe?g|svg)$/))
    },
    methods: {
        // IMPORTING ALL LOGOS FROM LOGO FOLDER "../assets/big-logos"
        importAll(r) {
            let logosTemp = {}
            r.keys().forEach((logo) => {
                logosTemp[logo.replace('./', '')] = r(logo);
            });
            let logosArray = Object.keys(logosTemp).map(logo => {let img = new Image(); img.src = require('../assets/big-logos/' + logo); return img;})

            return logosArray
        },
    }
}
</script>

<style>
    .clients-container {
        position:relative;
        float:left;
        background: #121212;
        height:auto;
        width:100vw;
        padding-bottom:150px;
    }

    .logo-flex-container {
        position:relative;
        float:left;
        height:auto;
        width:70vw;

        padding-left:15vw;
        padding-right:15vw;

        display:flex;
        flex-direction:row;
        flex-wrap:wrap;
        justify-content: center;
        column-gap:15vw;
        row-gap:150px;
    }

    .logo-img {
        background:transparent;
        height:auto;
        width:10vw;
        min-width:150px;
    }

    .clients-logo-container {
        background:transparent;
        height:auto;
        width:10vw;
        min-width:150px;
    }

    .clients-header {
        position:relative;
        padding-left:5vw;
        padding-top:5vw;
        
        font-weight: 400;
        font-size: 34px;
        line-height: 34px;
        color:white;
    }

    .clients-article {
        position:relative;
        padding-left:5vw;
        padding-top:50px;
        padding-bottom:150px;
        width:90vw;
        
        font-weight: 400;
        font-size: 18px;
        line-height: 18px;
        color:white;
    }

    @media screen and (max-width: 1000px) {
        .logo-img {
            background:transparent;
            height:auto;
            width:10vw;
            min-width:115px;
        }

        .clients-logo-container {
            background:transparent;
            height:auto;
            width:10vw;
            min-width:115px;
        }

        .logo-flex-container {
            column-gap:12vw;
            row-gap:115px;
        }

        .clients-article {
            padding-bottom:100px;
        }

        .clients-header {
            padding-top:80px;
        }
    }
</style>