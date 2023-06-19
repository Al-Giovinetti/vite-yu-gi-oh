<script>
import CardList from "./CardList.vue"

export default{
    name:"AppMain",
    components:{
        CardList
    }
}
</script>

<template>
    <main>
        <CardList />
    </main>


</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss";

main{
    background-color: orange;
    padding: 2rem 2rem 0;
    height: 500px;
}



</style>