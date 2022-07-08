<template>
    <div class="work-items-container">
        <!-- LOOPED BASED ON THE "workItems" ARRAY FOUND IN <script> -> data() -->
        <section v-for="workItem in workItems" :key="workItem.header" 
        :class="workItem.bigPic ? 'big-item' : workItem.isQuote ? 'quote-container' :'small-item'">
            
            <!---------------MAIN ITEM, BIG OR SMALL--------------->
            <SmallItem v-if="workItem.smallItem" :workItem="workItem"/>
            <BigItem v-if="workItem.bigPic" :workItem="workItem" />


            <!---------------ONLY ON BIG PICTURES--------------->
            <!---------------DO WE ADD SIDE ARTICLES--------------->
            <SideArticle v-if="workItem.bigPic" :workItem="workItem" /> 

            
            <!---------------QUOTES--------------->
            <article v-if="workItem.isQuote" class="quote-article">
                {{workItem.quote}}
            </article>
            <footer v-if="workItem.isQuote" class="quote-author">
                {{workItem.author}}
            </footer>
            <!---------------QUOTES END--------------->

        </section>
    </div>
</template>

<script>
import SmallItem from "../components/SmallItem.vue"
import BigItem from "../components/BigItem.vue"
import SideArticle from "../components/SideArticle.vue"

export default {
    name: "WorkItems",
    components: {
        SmallItem,
        BigItem,
        SideArticle
    },
    methods: {
        redirect(url) {
            window.location.href = url;
        }
    },
    data() {
        return {
            // Where items are added and loaded dynamically in the above <template> -> <section v-for="workItem in workItems"...
            workItems: [
                /* 
                    There are 3 different types of items
                    1. Your regular "square" small-item
                    2. The big-items with side articles, these have 2 extra booleans:
                        - bigPic, this makes the item a big-item
                        - floatRight, if true floats the picture to the right and the side-articles to the left, if false vice-versa
                    3. Quotes which is defined with the boolean "isQuote"

                */
                {
                    // link to image in ../assets/items/
                    imageLink: "image2.png",
                    // the title/header of the article
                    header: "BOL.COM",
                    // the article text
                    article: "A Summer island in the Netherlands",
                    // link to the actual article used as href for the entire div
                    readMoreLink: "some href",
                    // used together with filter inside "Work.vue"
                    filters: ["recreation", "marketing"],
                    // if it is a small item
                    smallItem: true,
                },
                {
                    imageLink: "image3.png",
                    header: "KEMPEN",
                    article: "Not some average banking website",
                    readMoreLink: "some href",
                    filters: ["frontend", "digital"],
                    smallItem: true,
                },
                {
                    imageLink: "image4.png",
                    header: "PHILIPS",
                    article: "Beautiful design meets innovative technology",
                    readMoreLink: "some href",
                    filters: ["design", "digital"],
                    smallItem: true,
                },
                {
                    imageLink: "image5.png",
                    header: "GEMEENTEMUSEUM",
                    article: "A 100 years of Mondriaan & De Stijl",
                    readMoreLink: "some href",
                    filters: ["marketing", "art"],
                    smallItem: true,
                },


                //--------------BIG ITEM--------------
                {
                    imageLink: "image1.png",
                    header: "FLORENSIS",
                    article: "Rethinking the entire online ecosystem",
                    readMoreLink: "some href",
                    filters: ["frontend", "digital"],
                    bigPic: true,
                    floatRight: false,
                },
                //--------------BIG ITEM END--------------


                {
                    imageLink: "image6.png",
                    header: "BE LIGHTNING",
                    article: "Delivering clarity on a global scale",
                    readMoreLink: "some href",
                    filters: ["marketing", "recreation"],
                    smallItem: true,
                },
                {
                    imageLink: "image7.png",
                    header: "TUI",
                    article: "Swipe to find your next holiday destination",
                    readMoreLink: "some href",
                    filters: ["frontend", "digital", "recreation"],
                    smallItem: true,
                },


                //--------------BIG ITEM--------------
                {
                    imageLink: "image14.jpg",
                    header: "FLORENSIS",
                    article: "Rethinking the entire online ecosystem",
                    readMoreLink: "some href",
                    filters: ["frontend", "digital"],
                    bigPic: true,
                    floatRight: true,
                },
                //--------------BIG ITEM END--------------


                {
                    imageLink: "image8.png",
                    header: "CHOCOMEL",
                    article: "A campaign for the limited edition letter packs",
                    readMoreLink: "some href",
                    filters: ["marketing", "art"],
                    smallItem: true,
                },
                {
                    imageLink: "image9.png",
                    header: "JBL",
                    article: "Live like a champion with Jerome Boateng",
                    readMoreLink: "some href",
                    filters: ["marketing", "digital"],
                    smallItem: true,
                },
                {
                    imageLink: "image10.png",
                    header: "ZALANDO",
                    article: "Innovative SEO and content strategy for Zalando",
                    readMoreLink: "some href",
                    filters: ["marketing", "frontend", "digital"],
                    smallItem: true,
                },
                {
                    imageLink: "image11.png",
                    header: "KONINKLIJKE BIBLIOTHEEK",
                    article: "The search of the most influential book ever",
                    readMoreLink: "some href",
                    filters: ["marketing", "art"], 
                    smallItem: true,
                },


                //--------------QUOTE--------------
                {
                    isQuote: true,
                    quote: "“Dept helped us tell our story through a bold new identity and a robust online experience. To the tone of 60% growth in online bookings in just one month”",
                    author: "MATTIJS TEN DRINK - CEO, TRANSAVIA"
                },
                //--------------QUOTE END--------------


                {
                    imageLink: "image12.png",
                    header: "LIBERTY GLOBAL",
                    article: "Delivering complex commerce solutions",
                    readMoreLink: "some href",
                    filters: ["frontend", "digital"], 
                    smallItem: true,
                },
                {
                    imageLink: "image13.png",
                    header: "ARLA",
                    article: "Swipe to find your next holiday destination",
                    readMoreLink: "some href",
                    filters: ["recreation", "marketing"], 
                    smallItem: true,
                },
            ],
        }
    }
}
</script>

<style>
    /* -------------- GENERAL -------------- */
    .work-items-container {
        position:relative;
        float:left;
    }

    .gradient-filter {
        z-index:1;
        position: absolute;

        height:100%;
        width:100%;
        background: linear-gradient(0deg, rgba(0,0,0,0.8) 0%, rgba(255,255,255,0) 50%);
    }

    .item-text-container {
        color:white;
        position:absolute;
        bottom: 10%;
        left:5%;
        width:60%;

        font-weight: 400;
        font-size:34px;
        line-height:34px;
        z-index: 2;
    }

    .item-container {
        height:35vw;
        width:50vw;
        position:relative;
        float:left;
        cursor:pointer;
    }

    .item-header {
        font-size:16px;
        line-height: 16px;

        margin-bottom:5%;
    }

    .read-more {
        color:white;
        position:relative;
        top:1vw;
        font-size: 16px;
        line-height:16px;
        float:left;
    }

    .outer-circle {
        width:12px;
        height:12px;
        border:1px solid white;
        border-radius:50%;
        float:left;
        position:relative;
    }

    .inner-circle {
        width:5px;
        height:5px;
        background:white;
        border-radius:50%;

        position:relative;
        top:50%;
        left:50%;
        transform:translate(-50%,-50%);

    }

    @media screen and (max-width: 1000px) {
        .item-text-container {
            font-size:26px;
            line-height:26px;
        }

        .item-container {
            height:60vh;
            width:100vw;
            position:relative;
        }

        .read-more {
            display:none;
        }
    }
    /* -------------- GENERAL END -------------- */


    /* -------------- QUOTES -------------- */
    .quote-container {
        position:relative;

        width:calc(100vw - 200px);
        height:auto;
        background: #121212;
        float:left;

        padding:100px;
    }

    .quote-article {
        text-align:center;
        font-size:26px;
        line-height:26px;
        color:white;
        padding-bottom:50px;


        height:auto;
        position:relative;
    }

    .quote-author {
        text-align:center;
        font-size:18px;
        line-height:18px;
        color:white;
        padding-left:64px;
        padding-right:64px;

        height:auto;
        position:relative;
    }

    @media screen and (max-width: 1000px) {
        .quote-container {
            position:relative;
            padding:60px;

            width:calc(100vw - 120px);
            height:auto;
            background: #121212;
            float:left;
        }

        
        .quote-article {
            padding-left:unset;
            padding-right:unset;
            padding-bottom:0px;

            top:0;
            left:0;
            transform:unset;
        }

        .quote-author {
            padding-left:unset;
            padding-right:unset;
            padding-top:32px;

            top:0;
            left:0;
            transform: unset;
        }

    }
    /* -------------- SMALL ITEMS END -------------- */
</style>