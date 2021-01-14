<template>
  <h1>sdfsfksjflsf</h1>
</template>

<script>
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

  }

}
</script>

<style>

</style>