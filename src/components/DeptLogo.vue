<template>
        <div class="letter-container" v-for="(vectorLetter, index) in vectorLetters" :key="vectorLetter">
            <img :src="require(`../assets/dept-vector-white/letter${vectorLetter}.svg`)" :class="index == 4 ? 'copy-right-logo' : 'svg-letters'"/>
        </div>
</template>

<script>
export default {
    data() {
        return {
            vectorLetters: ["1", "2", "3", "4", "5"],
        }
    }
}
</script>

<style>
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
</style>