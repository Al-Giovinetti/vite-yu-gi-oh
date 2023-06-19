<script>
import SingleCard from "./SingleCard.vue";
import axios from "axios";

export default{
    name:"CardList",

    dat(){
        return{
            CardList:[ ],
        }
    },

    components:{
        SingleCard
    },

    created(){
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then((response) => {
            console.log(response.data.data)
            this.CardList = response.data.data
        })
        .catch(function (error){
            console.log(error)
        })
    }

}
</script>

<template>
    {{ CardList }}
    <div class="container">
        <SingleCard />
    </div>
</template>

<style lang="scss" scoped>
    div.container{
        padding: 1rem;
        background-color: white;
    }

</style>