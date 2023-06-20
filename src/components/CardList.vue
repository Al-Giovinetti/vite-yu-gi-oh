<script>
import SingleCard from "./SingleCard.vue";

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

    props:{
        mycardlist: Object,
    }

}
</script>

<template>
    <div class="container flex">
        <SingleCard v-for="card in mycardlist" 
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