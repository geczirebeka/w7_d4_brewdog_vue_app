<template>
  <div v-if="beer">
      <h2>{{beer.name}}</h2>
      <ul>
          <li>Name: {{beer.name}}</li>
          <li>Tagline: {{beer.tagline}}</li>
          <li>Description: {{beer.description}}</li>
          <li>ABV: {{beer.abv}}%</li>
          <img :src="beer.image_url" alt="Beer Image">
      </ul>
  </div>
</template>

<script>
export default {
    name: 'beer-detail',
    props: ['beer']
}
</script>

<style>

</style>