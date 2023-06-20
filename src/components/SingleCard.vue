<script>

export default{
    name:"SingleCard",

    props:{
        name : String,
        type : String,
        image : String,
    }
}
</script>

<template>
    <div class="card flex">
        <div class="box-img">
            <img :src="image" :alt="name + 'image'">
        </div>
        <div class="name-card flex" >
            <h3>{{ name }}</h3>
        </div>
        <div class="type-card flex">
            <span>{{ type }}</span>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    div.card{
        flex-direction: column;
        align-items: center;
        width: calc(100% / 5 - 1.4rem);
        margin: 0.7rem;
        text-align: center;
        background-color: orange;
        

        >*{
            width: 100%;
        }

        .name-card{
            font-size: 1rem;
            height: 80px;
            border: 1px solid;
            padding: 0.2rem;
        }

        .type-card{
            height: 40px;
            font-size: 0.8rem;
            padding: 0.2rem;
            border: 1px solid;
        }

        .name-card>h3,
        .type-card>span{
            margin: auto;
        }
    }

    div.box-img{

        img{
            height: 100%;
            width: 100%;
            display: block;
            object-fit: contain;
        }
    }

</style>