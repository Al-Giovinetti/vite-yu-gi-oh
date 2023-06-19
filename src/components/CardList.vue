<script>
import SingleCard from "./SingleCard.vue"

export default{
    name:"CardList",
    components:{
        SingleCard
    }
}
</script>

<template>
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