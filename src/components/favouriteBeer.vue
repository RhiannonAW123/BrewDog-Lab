<template>
    <div>
        <ul>
        <p>your favourite beers are:</p>
        <li v-for='(beer, index) in favouriteBeers' :favouriteBeers='favouriteBeers' :key='index'>{{beer.name}}</li>
        <button v-if='!favouriteBeers.includes(beer)' v-on:click='deleteFavBeer(beer)'>Delete Beer</button>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'favourite-beers',
    props: ['favouriteBeers']

}
</script>

<style>

</style>