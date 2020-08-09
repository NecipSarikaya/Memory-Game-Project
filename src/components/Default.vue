<template>
    <div>
        <img :src="Image" alt="">
    </div>
</template>

<script>
import {dataBus} from "../main"
export default {
    data() {
        return {
            imageList:[
                {id:1 ,name:"card-1",src:"/src/assets/card-1.jpg"},
                {id:2 ,name:"card-2",src:"/src/assets/card-2.jpg"},
                {id:3 ,name:"card-3",src:"/src/assets/card-3.jpg"},
                {id:4 ,name:"card-4",src:"/src/assets/card-4.jpg"},
                {id:5 ,name:"card-5",src:"/src/assets/card-5.jpg"}
            ],  
            selectedImage :"",
            Image : ""
        } 
    },
    created(){
        let random = Math.round(Math.random()*this.imageList.length)
        this.selectedImage = this.imageList[random]
        dataBus.$emit("DefaultImage",this.selectedImage)
        this.Image = this.selectedImage.src
        setTimeout(()=>{
            this.Image = "/src/assets/2.jpg"
        },150)
    },
    beforeMount() {
      dataBus.$on("aktif",($event)=>{
          this.Image = this.selectedImage.src
      })  
    },
}
</script>

<style scoped>
    img{
        width: 260px;
        margin-left: 600px;
    }
</style>