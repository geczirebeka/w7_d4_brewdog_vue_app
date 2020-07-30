<template>
  <div>
    <h1>Brewdog Beers</h1>
    <div class="main-container">
      <beer-list :beers='beers'></beer-list>
      <beer-detail :beer="selectedBeer"></beer-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from "@/main.js" 
import BeerList from "./components/BeerList.vue"
import BeerDetail from "./components/BeerDetail.vue"

export default {
  name: 'app',
  data() {
    return {
      beers: [],
      selectedBeer: null,
      favouriteBeers: []
    };
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)

  eventBus.$on('selected-beer', (beer) => {this.selectedBeer = beer}) 
  },

  components: {
    "beer-list": BeerList,
    "beer-detail": BeerDetail,
    // "favourite-beer-list": FavouriteBeerList
  }

}
</script>

<style>

</style>