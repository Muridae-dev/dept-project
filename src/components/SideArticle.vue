<template>
    <div class="side-article-container"
    :style="workItem.floatRight ?  {'float':'right'} : {'float':'left'}">
        <!-- LOOPED BASED ON THE "sideArticles" ARRAY FOUND IN <script> -> data() -->
        <div class="side-article" v-for="(sideArticle, index) in sideArticles.slice(0, 3)" :key="sideArticle.header" 
        :style="index < 2 ? {'border-bottom': '1px solid white'} : null">

            <div class="side-article-text-container">
                <!---------------HEADER TEXT--------------->
                <header class="item-header">
                    {{sideArticle.header}}
                </header>

                <!---------------ARTICLE TEXT--------------->
                <article>
                    {{sideArticle.article}}
                </article>

                <!---------------READ MORE--------------->
                <a class="read-more" :href="sideArticle.readMoreLink">
                    <div class="outer-circle">
                        <div class="inner-circle">
                        </div>
                    </div>
                    &nbsp; Read more
                </a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ["workItem"],
    data() {
        return {
             // Side articles loaded with big-items
            sideArticles: [
                {
                    header: "MICROSOFT",
                    article: "Tapping into Ireland's unique gaming culture and bringing a fresh flavour to their Xbox social media channels",
                    readMoreLink: "some href",
                },
                {
                    header: "O'NEILL",
                    article: "Integrating existing content into O'Neills's new e-commerce platform",
                    readMoreLink: "some href",
                },
                {
                    header: "AMAZON",
                    article: "Starting with delivering through drones",
                    readMoreLink: "some href",
                },
                
            ]
        }
    }
}
</script>

<style>
    .side-article-container {
        width:30vw;
        height:35vw;
        position:relative;
        color:white;

        background: #121212;
    }

    .side-article {
        height:33%;
        width:90%;
        margin:auto;
        position:relative;

    }

    .side-article-text-container {
        position:absolute;
        top:50%;
        transform:translateY(-50%);
    }

    @media screen and (max-width: 1000px) {
        .side-article-container {
            width:100vw;
            height:35vh;
            padding-top:5px;

        }

        .side-article {
            height:33%;
            width:90%;
            margin:auto;
            position:relative;

        }

        .side-article-text-container {
            position:absolute;
            top:50%;
            transform:translateY(-50%);
        }
    }

    @media screen and (max-width: 580px) {
        .side-article-container {
            width:100vw;
            height:auto;
            padding-top:20px;

        }

        .side-article {
            height:auto;
            width:90%;
            margin:auto;
            position:relative;
            padding-top:50px;

        }

        .side-article-text-container {
            position:relative;
        }
    }
</style>