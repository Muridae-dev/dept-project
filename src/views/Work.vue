<!--  -->
<template>
    <div class="work-container">
        <MainItem />
        <Filter />
        <WorkItems />
    </div>
</template>

<script>
import WorkItems from "./WorkItems.vue"
import MainItem from "../components/MainItem.vue"
import Filter from "../components/Filter.vue"


export default {
    name: "Work",
    components: {
        WorkItems,
        MainItem,
        Filter,
    }

}
</script>

<style>
    /* -------------- GENERAL -------------- */
    .work-container {
        width:100vw;
        height:auto;
        position: relative;
    }
    /* -------------- END -------------- */
</style>
