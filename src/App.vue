<template>
  <div>
    <h1>Brewdog Beers</h1>
    <div class="main-container">
      <beer-list :beers='beers' :favourites="favourites"></beer-list>
      <beer-detail :beer="selectedBeer"></beer-detail>
      <favourite-beer-list :favourites="favourites"></favourite-beer-list>
    </div>
  </div>
</template>

<script>
import { eventBus } from "@/main.js" 
import BeerList from "./components/BeerList.vue"
import BeerDetail from "./components/BeerDetail.vue"
import FavouriteBeerList from "./components/FavouriteBeerList.vue"

export default {
  name: 'app',
  data() {
    return {
      beers: [],
      selectedBeer: null,
      favourites: []
    };
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)

  eventBus.$on('selected-beer', (beer) => {this.selectedBeer = beer})

  eventBus.$on('favourites', (beer) => {this.favourites.push(beer)})
  },

  components: {
    "beer-list": BeerList,
    "beer-detail": BeerDetail,
    "favourite-beer-list": FavouriteBeerList
  }

}
</script>

<style>

</style>