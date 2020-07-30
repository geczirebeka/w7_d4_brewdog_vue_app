<template>
  <div v-if="beer">
      <h2>{{beer.name}}</h2>
      <ul>
          <li>Name: {{beer.name}}</li>
          <li>Tagline: {{beer.tagline}}</li>
          <li>Description: {{beer.description}}</li>
          <li>ABV: {{beer.abv}}%</li>
          <li>Ingredients: {{ingredients}}</li>
          <img :src="beer.image_url" alt="Beer Image">
      </ul>
  </div>
</template>

<script>
export default {
    name: 'beer-detail',
    props: ['beer'],
    computed: {
        ingredients () {
            const ingredientsObject = this.beer.ingredients

            const malts = ingredientsObject.malt.map((malt) => {
                return malt.name
            })
            const hops = ingredientsObject.hops.map((hop) => {
                return hop.name
            })

            const uniqueMalts = malts.filter((malt, index) => malts.indexOf(malt) === index)
            const uniqueHops = hops.filter((hop, index) => hops.indexOf(hop) === index)

            const yeast = ingredientsObject.yeast

            let result = uniqueMalts.join(", ") + ", " + uniqueHops.join(", ") + ", " + yeast

            return result
        }
    }
}
</script>

<style>

</style>