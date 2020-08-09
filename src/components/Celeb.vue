<template>
    <div id="back">
        <div id="text">
            <h1>Doğru fotoğrafı buldunuz</h1>
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
    #text{
        position: absolute;
        left: 30%;
        top:40%
    }
    h1{
        color: green;
        font-weight: bold;
        font-size: 45px;
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