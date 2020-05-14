<template>
  <div class="container">
    <div class="columns is-multiline">
      <div v-for="(studio, index) in studios" :key="index" class="column is-one-quarter">
        <nuxt-link :to="'/studios/' + studio.sys.id">
          <figure
            class="image"
            @mouseover="hover = index"
            @mouseleave="hover = null"
          >
            <img :src="studio.fields.mainPhoto.fields.file.url" :alt="studio.fields.title">
            <div v-if="hover === index" class="overlay">
              {{ studio.fields.title }}
            </div>
          </figure>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import { createClient } from '~/plugins/contentful.js'

const client = createClient()

export default {
  name: 'Studios',
  // `env` is available in the context object
  asyncData () {
    return Promise.all([
      // fetch all studio posts sorted by creation date
      client.getEntries({
        content_type: 'product',
        'fields.type[all]': 'studio',
        order: '-sys.createdAt'
      })
    ]).then(([studios]) => {
      // return data that should be available
      // in the template
      return {
        studios: studios.items
      }
      // eslint-disable-next-line no-console
    }).catch(console.error)
  },
  data () {
    return {
      hover: null
    }
  }
}
</script>

<style>

  /* The overlay effect - lays on top of the container and over the image */
  .overlay {
    position: absolute;
    bottom: 0;
    background: rgb(0, 0, 0);
    background: rgba(0, 0, 0, 0.5); /* Black see-through */
    width: 100%;
    transition: .5s ease;
    opacity: 1;
    color: white;
    font-size: 20px;
    padding: 20px;
    text-align: center;
  }

</style>
