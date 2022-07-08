<template>
    <div class="big-item-container" :style="workItem.floatRight ? 'float:right' : null"
    @click="redirect(workItem.readMoreLink)">
        <div class="gradient-filter"></div>

        <img class="big-image" :src="require(`../assets/items/${workItem.imageLink}`)" />

        <div class="item-text-container">
            <!---------------HEADER TEXT--------------->
            <header class="item-header">
                {{workItem.header}}
            </header>

            <!---------------ARTICLE TEXT--------------->
            <article class="item-article">
                {{workItem.article}}
            </article>

            <!---------------READ MORE--------------->
            <a class="read-more">
                <div class="outer-circle">
                    <div class="inner-circle">
                    </div>
                </div>
                &nbsp; Read more
            </a>
        </div>
    </div>
</template>

<script>
export default {
    props: ["workItem"]
    
}
</script>

<style>
    /* -------------- BIG ITEMS -------------- */
    .big-item-container {
        height:35vw;
        width:70vw;
        position:relative;
        float:left;
        cursor:pointer;
    }

    .big-item {
        width:100vw;
        height:35vw;
        position: relative;

        overflow-y: hidden;
    }

    .big-image {
        height:auto;
        width:70vw;
    }


    @media screen and (max-width: 1000px) {
        .big-item {
            width:100vw;
            height:95vh;
            overflow-x:hidden;
        }

        .big-item-container {
            width:100vw;
            height:60vh;
        }

        .big-image {
            position:relative;
            left:50%;
            transform:translateX(-50%);
            height:auto;
            width:100vw;

        }
    }

    @media screen and (max-width: 580px) {
        .big-item {
            width:100vw;
            height:auto;
            overflow-x:hidden;
        }

        .big-image {
            position:relative;
            left:50%;
            transform:translateX(-50%);
            height:60vh;
            width:auto;

        }
    }
    /* -------------- BIG ITEMS END -------------- */
</style>