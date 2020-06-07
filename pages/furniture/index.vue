<template>
  <div class="container">
    <div class="columns is-multiline">
      <div v-for="(furniture, index) in furniture" :key="index" class="column is-one-third">
        <nuxt-link :to="'/furniture/' + furniture.sys.id">
          <figure
            class="image"
            @mouseover="hover = index"
            @mouseleave="hover = null"
          >
            <img :src="furniture.fields.mainPhoto.fields.file.url" :alt="furniture.fields.title">
            <div v-if="hover === index" class="overlay">
              {{ furniture.fields.title }}
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
  name: 'Furniture',
  // `env` is available in the context object
  asyncData () {
    return Promise.all([
      // fetch all furniture posts sorted by creation date
      client.getEntries({
        content_type: 'product',
        'fields.type[all]': 'furniture',
        order: '-sys.createdAt'
      })
    ]).then(([furniture]) => {
      // return data that should be available
      // in the template
      return {
        furniture: furniture.items
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
