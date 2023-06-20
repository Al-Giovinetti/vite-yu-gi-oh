<script>
import CardList from "./CardList.vue"
import CardSearchbar from "./CardSearchbar.vue"
import axios from "axios";


export default{
    name:"AppMain",

    data(){
        return{
            CardList:[ ]
        }
    },

    components:{
        CardList,
        CardSearchbar,
    },

    created() {
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
    <main>
        <CardSearchbar />
        <CardList
            :list = "CardList" 
        />
    </main>


</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss";

main{
    background-color: orange;
    padding: 2rem 2rem 0;
}
</style>