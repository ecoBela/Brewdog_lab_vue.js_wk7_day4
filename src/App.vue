<template lang="html">
  <div>
    <h1>Brewdog Beers</h1>
    <div>
      <beers-list :beers='beers'></beers-list>
      <beer-detail :beer="selectedBeer"></beer-detail>
      <favourite-beer :favouriteBeer="favouriteBeers">This should be a list of favourites</favourite-beer>
    </div>
  </div>
</template>

<script>
import { eventBus} from './main.js'
import BeersList from './components/BeersList.vue';
import BeerDetail from './components/BeerDetail.vue';
import FavouriteBeers from './components/FavouriteBeers.vue';

export default {
  name: 'app', 
  data(){
    return {  
      beers: [],
      selectedBeer: null,
      favouriteBeers: []
      }
  },
  mounted(){
    this.getbeers()

    eventBus.$on("selected-beer", (beer) => this.selectedBeer = beer)
    eventBus.$on("favourite-beer", (beer) => this.favouriteBeers.push(beer))
  },
  methods: {
    getbeers: function(){fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)},


  }, 

  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail,
    "favourite-beer": FavouriteBeers,
  


  }

}
</script>

<style>

</style>