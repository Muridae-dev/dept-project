<template>
    <!---------------FILTER--------------->
    <section class="filter">
        <div class="right-selection">
            Show me 
            <select name="work-filter" id="work-filter">
                <option value="all">all work</option>
                <option value="frontend">front-end</option>
                <option value="design">design</option>
                <option value="marketing">marketing</option>
            </select>
        </div>

        <div class="left-selection">
            In
            <select name="industry-filter" id="industry-filter">
                <option value="all">all industries</option>
                <option value="recreation">recreation</option>
                <option value="art">art</option>
                <option value="digital">digital</option>
            </select>
        </div>
    </section>
    <!---------------FILTER END--------------->
</template>

<style>
    /* -------------- FILTER -------------- */
    .filter {
        color:#A3A3A3;
        font-size:26px;
        line-height:26px;
        font-weight: 400;

        height:10vh;
        position:relative;

    }

    .right-selection {
        position:absolute;
        left:2%;
        top:50%;
        transform:translateY(-50%);
    }

    .left-selection {
        position:absolute;
        right:2%;
        top:50%;
        transform:translateY(-50%);
    }

    #work-filter, #industry-filter {
        border:none;
        -moz-appearance:none; /* Firefox */
        -webkit-appearance:none; /* Safari and Chrome */
        appearance:none;
        text-decoration:underline;
        color:#0E0E0E;

        font-size:26px;
        line-height:26px;
        font-weight: 400;
    }

    @media screen and (max-width: 1000px) {
        #work-filter, #industry-filter {
            font-size:16px;
            line-height:16px;
            font-weight: 400;
            color:white;
            background:#121212;
        }

        .filter {
            font-size:16px;
            line-height:16px;
            background:#121212;

        }
    }
    /* -------------- END -------------- */
</style>