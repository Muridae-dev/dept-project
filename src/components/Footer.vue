<template>
    <footer class="footer-container">
        <section class="upper-footer">
            <div class="footer-logo-container">
                <DeptLogo />
            </div>

            
            <div class="footer-link-container">
                <SiteLinks />
            </div>
        </section>

        <section class="lower-footer">
            <div class="lower-footer-text-container">
                <span>Chamber of Commerce: 63464101</span>
                <span>VAT: NL 8552.47.502.B01</span>
                <span>Terms and conditions</span>
                <span style="float:right;" class="footer-copywright">© 2022 Dept Agency</span>
            </div>
        </section>
    </footer>
</template>

<script>
import DeptLogo from "../components/DeptLogo.vue"
import SiteLinks from "../components/SiteLinks.vue"

export default {
    name: "Footer",
    components: {
        DeptLogo,
        SiteLinks
    }
}
</script>

<style>
    .footer-container {
        float:left;
        position:relative;
        height:310px;
        width:calc(90vw - 1px);
        background:#0E0E0E;
        color:white;
    }

    .upper-footer {
        height:50%;
        width:95%;
        margin:auto;
        position:relative;

        border-bottom: 1px solid #3E3E3E;
    }


    .lower-footer {
        height:calc(50% - 1px);
        width:90%;
        margin:auto;
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 18px;

        color: #808080;
    }

    .lower-footer-text-container {
        position:relative;
        top:50%;
        transform:translateY(-50%);
    }

    .footer-link-container {
        float:left;
        position:relative;
        top:50%;
        left:200px;
        transform:translateY(-50%);
    }

    .footer-links {
        padding:16px;
    }

    .footer-logo-container {
        height:22px;

        position:relative;
        float:left;
        top:50%;
        left:5%;
        transform:translateY(-50%);
       
    }

    @media screen and (max-width: 1000px) {
        .footer-container {
            float:left;
            position:relative;
            height:auto;
            width:90vw;
            background:#0E0E0E;
            color:white;
            padding:5vw;
        }

                
        .upper-footer {
            height:300px;
            width:100%;
            margin:auto;
            position:relative;

        }

        .lower-footer {
            height:200px;
            width:90%;
            margin:auto;
            font-style: normal;
            font-weight: 400;
            font-size: 13px;
            line-height: 15px;
            float:left;
            

            color: #808080;
        }

        .footer-links {
            padding:unset;
            padding-top:16px;
            padding-bottom:16px;
            float:left;
        }

        .footer-logo-container {
            display:none;
        }

        .footer-link-container {
            top:unset;
            left:unset;
            transform:unset;
            height:auto;

            display:flex;
            flex-direction: column;

            text-align:left;
        }

        .lower-footer-text-container {
            position:relative;
            top:50%;
            transform:translateY(-50%);
            float:left;
            width:100%;

            display:flex;
            flex-direction:column;

        }

        .footer-copywright {
            margin-top:8%;
        }

    }

</style>

<style scoped>
    span {
        padding-right:5%;
    }

    @media screen and (max-width: 1000px) {
    }
</style>