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
            UrlApiArchetypes:"https://db.ygoprodeck.com/api/v7/archetypes.php",
            UrlMyArchetype:"https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype="
        }
    },

    components:{
        CardList,
        CardSearchbar
    },

    methods:{
        getCards(x){
            if(x == undefined){
                axios.get(this.UrlApiCards).then((response) => {
                    console.log(response)
                    this.CardList = response.data.data
                })
                .catch(function (error){
                    console.log(error)
                })
            }else{
                axios.get(this.UrlMyArchetype+x).then((response) => {
                    this.CardList = response.data.data
                    console.log("ciao")
                })
                .catch(function (error){
                    console.log(error)
                })  
            }
        },
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
        <CardSearchbar @filter ="getCards" 
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