<template>
  <div class="container">
    <div class="columns is-multiline">
      <div v-for="(theater, index) in theaters" :key="index" class="column is-one-third">
        <nuxt-link :to="'/theaters/' + theater.sys.id">
          <figure
            class="image"
            @mouseover="hover = index"
            @mouseleave="hover = null"
          >
            <img :src="theater.fields.mainPhoto.fields.file.url" :alt="theater.fields.title">
            <div v-if="hover === index" class="overlay">
              {{ theater.fields.title }}
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
  name: 'Theaters',
  // `env` is available in the context object
  asyncData () {
    return Promise.all([
      // fetch all theater posts sorted by creation date
      client.getEntries({
        content_type: 'product',
        'fields.type[all]': 'theater',
        order: '-sys.createdAt'
      })
    ]).then(([theaters]) => {
      // return data that should be available
      // in the template
      return {
        theaters: theaters.items
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
