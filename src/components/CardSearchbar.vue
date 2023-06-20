<script>
    export default{
        name:"CardSearchbar",

        data(){
            return{
                selected : ""
            }
        },

        props: {
            myarchetypelist : Array,
        },

    }

</script>

<template>
    <div>
        <span>select your archetype</span>
        <select @click="$emit('filter',selected)" v-model="selected">
            <option v-for="(archetype) in myarchetypelist">
                {{ archetype.archetype_name }}
            </option>
        </select>
        <span>{{ selected }}</span>
    </div>

</template>

<style lang="scss" scoped>
    div:first-child{
        background-color: black;
        color: white;
        padding: 1rem;

        span{
            padding-right: 1rem;
        }
    }

</style>