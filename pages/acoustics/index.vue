<template>
  <div class="container">
    <div class="columns is-multiline">
      <div v-for="(acoustic, index) in acoustics" :key="index" class="column is-one-third">
        <nuxt-link :to="'/acoustics/' + acoustic.sys.id">
          <figure
            class="image"
            @mouseover="hover = index"
            @mouseleave="hover = null"
          >
            <img :src="acoustic.fields.mainPhoto.fields.file.url" :alt="acoustic.fields.title">
            <div v-if="hover === index" class="overlay">
              {{ acoustic.fields.title }}
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
  name: 'Acoustics',
  // `env` is available in the context object
  asyncData () {
    return Promise.all([
      // fetch all acoustic posts sorted by creation date
      client.getEntries({
        content_type: 'product',
        'fields.type[all]': 'acoustic',
        order: '-sys.createdAt'
      })
    ]).then(([acoustics]) => {
      // return data that should be available
      // in the template
      return {
        acoustics: acoustics.items
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
