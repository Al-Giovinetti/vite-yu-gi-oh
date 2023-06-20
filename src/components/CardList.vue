<script>
import SingleCard from "./SingleCard.vue";
import axios from "axios";

export default{
    name:"CardList",

    data(){
        return{
            CardList:[ ],
        }
    },

    components:{
        SingleCard
    },

    created(){
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=25&offset=0")
        .then((response) => {
            console.log(response)
            this.CardList = response.data.data
        })
        .catch(function (error){
            console.log(error)
        })
    }

}
</script>

<template>
    <div class="container flex">
        <SingleCard v-for="card in CardList" 
        :name ="card.name"
        :type="card.type"
        :image ="card.card_images[0].image_url" 
        />
    </div>
</template>

<style lang="scss" scoped>
    div.container{
        padding: 1rem;
        background-color: white;
        flex-wrap: wrap;
    }

</style>