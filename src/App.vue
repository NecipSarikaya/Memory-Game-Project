<template>
    <div>
        <component :is="componentId"></component>
        <canvas id="canvas" v-show="componentId == 'appCeleb'"></canvas>
    </div>
</template>

<script>
import Main from "./components/Main";
import Celeb from "./components/Celeb";
import Fail from "./components/Fail";
import {dataBus} from "./main"
export default {
    components:{
        appMain : Main,
        appCeleb : Celeb,
        appFail : Fail
    },
    data() {
        return {
            componentId:"appMain"
        }
    },
    created(){
        dataBus.$on("Sonuc",($event)=>{
            console.log($event)
            setTimeout(()=>{
                if($event == 1){
                this.componentId = "appCeleb"
                }else{
                    this.componentId = "appFail"
                }
            },700)
        })
    }
}
</script>

<style>

</style>
