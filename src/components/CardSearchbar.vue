<script>
    export default{
        name:"CardSearchbar",

        data(){
            return{
            }
        },

        props: {
            myarchetypelist : Array,
        }
    }

</script>

<template>
    <div>
        <span>select your archetype</span>
        <select @keyup.enter="$emit(filter)">
            <option :value="index" v-for="(archetype, index) in myarchetypelist">
                {{ archetype.archetype_name }}
            </option>
        </select>
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