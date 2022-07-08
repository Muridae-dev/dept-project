<template>
    <button class="top-arrow-button" @click="scrollTop">
        <img src="../assets/misc/arrow.svg" /> <br/> <br/>
        TOP
    </button>
</template>

<script>
export default {
    methods: {
        scrollTop() {
            window.scrollTo({
              top: 0,
              left: 0,
              behavior: 'smooth'
            });
        }
    }
}
</script>

<style>
    .top-arrow-button {
        padding:0;
        margin:0;

        width:calc(9vw - 1px);
        background:#0E0E0E;
        height:310px;
        border:none;
        border-left:1px solid #3E3E3E;
        float:left;
        color:white;

        cursor: pointer;
    }

    @media screen and (max-width: 1350px) {
        .top-arrow-button {
            width:calc(9vw - 5px);
        }
    }

    @media screen and (max-width: 1000px) {
        .top-arrow-button {
            width:calc(9vw - 5px);
            display:none;
        }
    }
</style>