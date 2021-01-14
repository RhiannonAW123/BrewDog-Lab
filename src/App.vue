<template>
  
  <div id='app'>
    <brew-list :beers='beers'></brew-list>

    <brew-detail :beer='selectedBeer' :favouriteBeers='favouriteBeers'></brew-detail>
    <favourite-beers :favouriteBeers='favouriteBeers'></favourite-beers>
  </div>

</template>

<script>
import { eventBus } from './main.js'
import BrewList from './components/BrewList.vue';
import BrewDetail from './components/BrewDetail.vue';
import favouriteBeer from './components/favouriteBeer.vue';

export default {
  name: 'app',
  data (){
    return {
      beers: null,
      selectedBeer: null,
      favouriteBeers: []
    };
  },

  mounted(){
    fetch('https://api.punkapi.com/v2/beers?per_page=80')
    .then(res => res.json())
    .then(beers => this.beers = beers)

    eventBus.$on('selected-beer', (beer) => {
      this.selectedBeer = beer;
      console.log(beer)
    })

  },
  components: {
    "brew-list" : BrewList,
    "brew-detail" : BrewDetail,
    "favourite-beers" : favouriteBeer
  }
}
</script>

<style>

</style>
