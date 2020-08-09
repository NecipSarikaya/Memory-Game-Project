<template>
    <div id="back">
        <div id="text">
            <h1>Doğru fotoğrafı bulamadınız</h1>
            <br>
            <br>
            <button @click="newgame">Yeni Oyun</button>
        </div>
    </div>
</template>

<script>
export default {
    methods:{
        newgame(){
            location.reload();
        }
    }
}
</script>

<style scoped>
    *{
        margin: 0px;
        padding: 0px;
    }
    #back{
        width: 100vm;
        height: 100vh;
        background-color: red;
    }
    #text{
        position: absolute;
        left: 40%;
        top:45%
    }
    h1{
        font-size: 35px;
    }
    button{
        background-color: green;
        width: 150px;
        height: 5vh;
        border:none;
        color: white;
        font-size: 20px;
        text-align: center;
    }
</style>