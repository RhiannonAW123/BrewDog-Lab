<template lang='html'>
    <div v-if='beer'>
    
    <h2>{{beer.name}}</h2>
    <p><i>{{beer.tagline}}</i></p>
    <p>{{beer.abv}}</p>
    <p>{{beer.description}}</p>
    <p>{{beer.food_pairing}}</p>

    <button v-if='!favouriteBeers.includes(beer)' done here v-on:click='saveFavBeer(beer)'><b>Save this beer to your favourites</b></button>
    <p v-if='favouriteBeers.includes(beer)'> This beer has been saved to your favourites!</p>

    </div>

</template>

<script>
import {eventBus} from '../main.js'

export default {
    name: 'brew-detail',
    props: ['beer', 'favouriteBeers'],
    methods: {
        saveFavBeer: function(beer){
            this.favouriteBeers.push(beer)},

        deleteFavBeer: function(beer){
            const index = favouriteBeers(beer);
            if (index = favouriteBeers)
            this.favouriteBeers.remove(beer)}


// const array = [2, 5, 9];

// console.log(array);

// const index = array.indexOf(5);
// if (index > -1) {
//   array.splice(index, 1);
// }

        
    }
}


</script>

<style>

</style>