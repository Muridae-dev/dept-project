<template>
    <!-- This a loops through all the links in the object below -->
    <!-- It only underlines the object/link that "isActive = true" -->
    <a v-for="siteLink in siteLinks" :key="siteLink.title" :src="siteLink.link" 
    :class="isFooter ? 'footer-links' : 'site-links'"
    :style="[siteLink.isActive ? {'text-decoration' : 'underline'} : null,
    menuActive ? {'opacity' : '0'} : null]">
        {{siteLink.title}}
    </a>
</template>

<script>
export default {
    name: "SiteLinks",
    props: ["menuActive", "isFooter"],
    data() {
        return {
            siteLinks: [
                {
                    title: "WORK",
                    link: null,
                    isActive: true,
                },
                {
                    title: "CULTURE",
                    link: null,
                    isActive: false,
                },
                {
                    title: "SERVICE",
                    link: null,
                    isActive: false,
                },
                {
                    title: "INSIGHTS",
                    link: null,
                    isActive: false,
                },
                {
                    title: "CAREERS",
                    link: null,
                    isActive: false,
                },
                {
                    title: "CONTACT",
                    link: null,
                    isActive: false,
                }
            ]
        }
    },
}
</script>

<style>
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