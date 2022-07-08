<template>
    <!---------------MAIN ITEM--------------->
    <section class="main-item">
        <img src="../assets/items/image-main.png" class="image-main"/>

        <div class="main-text-container">
            <header class="main-header">
                WORK
            </header>
            <article class="main-article">
                A selection of projects that <strong>pinoeer tech</strong> and <strong>marketing</strong>
                to help brands stay ahead.
            </article>
        </div>
    </section>
    <!---------------MAIN ITEM END--------------->
</template>

<style>
    /* -------------- MAIN -------------- */
    .main-item {
        width:100vw;
        height:auto;
        position:relative;
    }

    .image-main {
        position: relative;
        width:100vw;
        height:auto;
    }

    .main-text-container {
        color:white;
        position:absolute;
        bottom: 10%;
        left:5%;
        width:580px;

        font-weight: 400;
        font-size:34px;
        line-height:34px;
    }

    .main-header {
        font-size:16px;
        line-height: 16px;

        margin-bottom:5%;
    }

    @media screen and (max-width: 1000px) {
        .main-item {
            width:100vw;
            height:60vh;
            overflow-x:hidden;
        }

        .image-main {
            position:absolute;
            left:50%;
            transform:translateX(-50%);
            height:60vh;
            width:auto;

        }

        .main-text-container {
            width:80vw;

        }
    }
    /* -------------- END -------------- */
</style>