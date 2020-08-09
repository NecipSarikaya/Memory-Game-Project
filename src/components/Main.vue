<template>
    <div class="container">
        <div class="row">
            <div class="col-md-6 col-md-offset-3">
                <h1 style="text-align : center">Poğaça Nerede ?</h1>
                <h3 style="text-align : center">Açık kartlardan birini seçtikten sonra kapalı karda tıklayınız</h3>
                <app-card></app-card>
                <hr>
                <br>
                <br>
                <app-default></app-default>
            </div>
        </div>
    </div>
</template>

<script>
import {dataBus} from "../main"
import Cards from "./Card"
import Default from "./Default"
export default {
    components:{
        appCard : Cards,
        appDefault : Default
    },
    data() {
        return {
            defImageid:0,
            selectedImageid:0
        }
    },
    created(){
        dataBus.$on("DefaultImage",($event)=>{
            console.log("def1 "+this.defImageid )
            this.defImageid = $event.id
            console.log("def2 "+this.defImageid )
        })
    },
    beforeMount(){
        dataBus.$on("SelectedImage",($event)=>{
            console.log("sel1 "+this.selectedImageid)
            this.selectedImageid = $event.id
            console.log("sel2 "+this.selectedImageid)
            if(this.defImageid == this.selectedImageid){
                dataBus.$emit("Sonuc",1)
                dataBus.$emit("aktif",1)
            }else{
                dataBus.$emit("Sonuc",0)
                dataBus.$emit("aktif",1)
            }
        })
        
    },
}
</script>

<style>
    
</style>