<template lang="html">
  <div>
    <h1>Brewdog Beers</h1>
    <div>
      <beer-list :beers='beers'></beer-list>
    </div>
  </div>
</template>

<script>
import BeersList from './components/BeersList.vue';

export default {
  name: 'app', 
  data(){
    return {  
      beers: []
      }
  },
  mounted(){
    this.getbeers();
  },
  methods: {
    getbeers: function(){fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)}

  }, 
  components: {
    "beers-list": BeersList,


  }

}
</script>

<style>

</style>