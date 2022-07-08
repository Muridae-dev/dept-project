<template>
    <div class="item-container" @click="redirect(workItem.readMoreLink)">
        <div class="gradient-filter"></div>
        <img class="small-image" :src="require(`../assets/items/${workItem.imageLink}`)" />
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
    props: ["workItem"],
}
</script>

<style>
    /* -------------- SMALL ITEMS -------------- */
    .small-item {
        width:50vw;
        height:35vw;
        position: relative;
        float:left;

        overflow-y: hidden;
    }

    .small-image {
        height:auto;
        width:100%;
    }

    @media screen and (max-width: 1000px) {
        .small-item {
            width:100vw;
            height:60vh;
            overflow-x:hidden;
        }


        .small-image {
            position:absolute;
            left:50%;
            transform:translateX(-50%);
            height:auto;
            width:100%;

        }

    }

        @media screen and (max-width: 580px) {
        .small-item {
            width:100vw;
            height:60vh;
            overflow-x:hidden;
        }

        .small-image {
            position:absolute;
            left:50%;
            transform:translateX(-50%);
            height:60vh;
            width:auto;

        }
    }
    /* -------------- SMALL ITEMS END -------------- */

</style>