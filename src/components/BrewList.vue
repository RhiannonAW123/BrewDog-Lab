<template lang="html">
    <div>
        <ul>
            <li v-for="(beer, index) in beers" :beer="beer" :key="index" v-on:click='handleClick(beer)'>{{beer.name}}</li>
        </ul>
    </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'brew-list',
    props: ['beers'],

    methods: {
        handleClick: function(beer){
            eventBus.$emit('selected-beer', beer)
        }
    }
}

</script>

<style>

</style>