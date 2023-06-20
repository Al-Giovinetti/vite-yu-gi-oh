<script>
import CardList from "./CardList.vue"
import CardSearchbar from "./CardSearchbar.vue"


export default{
    name:"AppMain",
    components:{
        CardList,
        CardSearchbar,
    }
}
</script>

<template>
    <main>
        <CardSearchbar />
        <CardList />
    </main>


</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss";

main{
    background-color: orange;
    padding: 2rem 2rem 0;
}



</style>