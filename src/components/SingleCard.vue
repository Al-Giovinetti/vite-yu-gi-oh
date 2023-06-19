<script>

export default{
    name:"SingleCard",

    props:{
        name : String,
        type : String,
        image : String
    }
}
</script>

<template>
    <div class="card flex">
        <div class="box-img">
            <img :src="image" :alt="name + 'image'">
        </div>
        <h2 class="name-card">{{ name }}</h2>
        <span class="type-card">{{ type }}</span>
    </div>
</template>

<style lang="scss" scoped>
    div.card{
        flex-direction: column;
        align-items: center;
        width: calc(100% / 5);
    }

    div.box-img{
        height: 200px;
        width: 100%;

        img{
            height: 100%;
            width: 100%;
            display: block;
            object-fit: contain;
        }
    }

</style>