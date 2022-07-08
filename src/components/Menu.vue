<template>
    <section class="menu-container" :style="menuActive ? null : {top:'-100vh'}">
        <div class="menu-item" v-for="menuItem in menuItems" :key="menuItem.name">
            <a :href="menuItem.link">{{menuItem.name}}</a>
        </div>
    </section>
</template>

<script>
export default {
    props: ["menuActive"],
    data() {
        return {
            menuItems: [
                {
                    name: "HOME",
                    link: "some href"
                },
                {
                    name: "WORK",
                    link: "some href"
                },
                {
                    name: "CULTURE",
                    link: "some href"
                },
                {
                    name: "SERVICES",
                    link: "some href"
                },
                {
                    name: "PARTNERS",
                    link: "some href"
                },
                {
                    name: "STORIES",
                    link: "some href"
                },
                {
                    name: "CAREERS",
                    link: "some href"
                },
                {
                    name: "EVENTS",
                    link: "some href"
                },
                {
                    name: "CONTACT",
                    link: "some href"
                },
            ]
        }
    }    
}
</script>

<style>
    .menu-container {
        height:calc(100vh - 110px);
        width:100vw;
        background: #121212;


        position:fixed;
        top:110px;
        transition: top 1s;
        left:0;
        z-index:3;

    }

    .menu-item {
        width:90%;
        height:auto;
        font-size:60px;
        text-align:right;
        padding-top:10px;

        margin:auto;

        border-bottom:1px solid #A3A3A3;
        
    }
</style>
