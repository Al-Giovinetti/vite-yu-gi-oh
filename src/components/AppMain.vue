<script>
import CardList from "./CardList.vue"
import CardSearchbar from "./CardSearchbar.vue"
import axios from "axios";


export default{
    name:"AppMain",

    data(){
        return{
            CardList: [ ],
            ArchetypeList: [ ],
            UrlApiCards: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0",
            UrlApiArchetypes:"https://db.ygoprodeck.com/api/v7/archetypes.php"
        }
    },

    components:{
        CardList,
        CardSearchbar,
    },

    methods:{
        getCards(){
            axios.get(this.UrlApiCards)
            .then((response) => {
                console.log(response)
                this.CardList = response.data.data
            })
            .catch(function (error){
                console.log(error)
            })
        },

        getCardsArchetye(){

        }

    },

    created() {
        this.getCards(),

        axios.get(this.UrlApiArchetypes)
        .then((response) => {
            console.log(response.data)
            this.ArchetypeList = response.data
            //console.log(this.ArchetypeList)

        })
        .catch(function (error){
            console.log(error)
        })
    }
}
</script>

<template>
    <main>
        <CardSearchbar @filter ="getCardArchetye()" 
         :myarchetypelist ="ArchetypeList"
        />
        <CardList
            :mycardlist = "CardList" 
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