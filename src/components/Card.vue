<template>
    <div>
        <ul class="list-group">
            <li style="display:inline-block" class="list-group-item" v-for="image in imageList"><img @click="selectImage(image)" :src="image.src" alt="image.name"></li>
        </ul>
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
            ım : ""
        }
    },
    methods:{
        selectImage(image){
            dataBus.$emit("SelectedImage",image)
        }
    }
}
</script>

<style scoped>
    img{
        width: 260px;
        margin-right: 15px;
    }
</style>