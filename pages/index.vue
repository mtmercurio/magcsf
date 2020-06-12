<template>
  <div>
    <nuxt-link to="/furniture">
      <figure class="image is-16by9">
        <img :src="frontPagePictures.main.fields.file.url" alt="main">
      </figure>
      <section class="hero is-light">
        <div class="hero-body">
          <div class="container has-text-centered">
            <h1 class="title">
              Making Audio Great Since 1998
            </h1>
          </div>
        </div>
      </section>
    </nuxt-link>
    <div class="columns">
      <div class="column is-one-third">
        <nuxt-link to="/acoustics">
          <figure class="image is-16by9">
            <img :src="frontPagePictures.acoustics.fields.file.url" alt="acoustics">
          </figure>
        </nuxt-link>
      </div>
      <div class="column is-one-third">
        <nuxt-link to="/studios">
          <figure class="image is-16by9">
            <img :src="frontPagePictures.studios.fields.file.url" alt="studios">
          </figure>
        </nuxt-link>
      </div>
      <div class="column is-one-third">
        <nuxt-link to="/theaters">
          <figure class="image is-16by9">
            <img :src="frontPagePictures.theaters.fields.file.url" alt="theaters">
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
  name: 'HomePage',
  // `env` is available in the context object
  asyncData () {
    return Promise.all([
      // fetch all acoustic posts sorted by creation date
      client.getEntries({
        content_type: 'frontPage',
        order: '-sys.createdAt'
      })
    ]).then(([frontPage]) => {
      // return data that should be available
      // in the template
      return {
        frontPagePictures: frontPage.items[0].fields
      }
      // eslint-disable-next-line no-console
    }).catch(console.error)
  },
  data () {
    return {
    }
  }
}
</script>

<style>
</style>
