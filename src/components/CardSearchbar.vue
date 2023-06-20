<script>
    export default{
        name:"CardSearchbar"
    }

</script>

<template>
    <div>
        <span>select your archetype</span>
        <select name="archetype" id="archetype" @keyup.enter="$emit(filter)">
            <option value="1">Alien</option>
            <option value="2">Melodious</option>
            <option value="3">Archfiend</option>
            <option value="4">Elemental HERO</option>
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