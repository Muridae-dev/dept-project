<template>
    <div class="questions-container">
        <div class="questions-text">
            QUESTION? <br /> 
            WE ARE HERE TO HELP!
        </div>
        <form>
            <div class="questions-form-container">
                <div class="input-container">
                    <div class="name-container">
                        <label for="fname">NAME:</label><br>
                        <input type="text" id="name" name="name" required><br>
                    </div>

                    <div class="email-container">
                        <label for="email">EMAIL:</label><br>
                        <input type="email" id="email" name="email" required>
                    </div>

                    <div class="message-container">
                        <label for="message">MESSAGE:</label><br>
                        <textarea id="message" name="message" rows="1" cols="33" required></textarea><br>
                    </div>
                </div>
            
            <input type="submit" id="submit-button" value="SEND">
            </div>

        </form>
    </div>
</template>

<script>
export default {
    
}
</script>

<style>
    .questions-container {
        float:left;
        position:relative;

        height:300px;
        width:100vw;
        background:white;
        padding-left:5vw;
        padding-right:5vw;
        padding-top:80px;
        padding-bottom:80px;

    }

    .questions-text {
        width:25vw;
        padding-right:5vw;
        font-size:48px;
        line-height:80px;
        float:left;
    }

    .questions-form-container {
        width:30vw;
        height:300px;
        float:left;

    }

    .input-container {
        width:30vw;
        height:240px;
        display:flex;
        flex-direction: row;
        flex-wrap:wrap;
        gap:10px;

    }

    #submit-button {
        float:left;
        height:45px;
        width:150px;
        background:none;
        border-radius: 50px;
        border:1px solid black;

        cursor:pointer;

    }

    #submit-button:hover {
        border:1px solid #5115F7;
        color:#5115F7;
    }


    @media screen and (max-width: 1000px) {
        .questions-container {
            float:left;
            position:relative;

            height:auto;
            width:100vw;
            background:white;
            padding-left:5vw;
            padding-right:5vw;
            padding-top:8vw;
            padding-bottom:8vw;

        }
        .questions-text {
            width:100vw;
            height:72px;
            padding-right:5vw;
            font-size:26px;
            line-height:26px;
            float:left;
        }

        
        .questions-form-container {
            width:100%;
            height:auto;
            float:left;

        }

        .input-container {
            width:30vw;
            height:auto;
            display:flex;
            flex-direction: row;
            flex-wrap:wrap;
            gap:10px;

        }

        #submit-button {
            float:left;
            height:45px;
            width:90vw;
            background:none;
            border-radius: 50px;
            border:1px solid black;

            cursor:pointer;

        }

    }
</style>

<style scoped>
    input {
        border:none;
        border-bottom:1px solid #DDDDDD;
        margin-bottom:32px;
        width:13vw;
        height:20px;
        font-size:16px;
        font-family:maisonNeue;
        outline:none;
    }

    input:focus, textarea:focus {
        border-bottom:1px solid #5115F7;
    }


    textarea {
        border:none;
        border-bottom:1px solid #DDDDDD;
        margin-bottom:32px;
        resize:none;
        width:13vw;
        height:100px;
        font-size:16px;
        font-family:maisonNeue;
        outline:none;
    }

    label {
        font-size: 16px;

    }

    @media screen and (max-width: 1000px) {
        input {
            width:90vw;

        }

        textarea {
            width:90vw;
            height:100px;
        }

    }
</style>