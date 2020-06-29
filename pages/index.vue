<template>
  <div>
    <nuxt-link to="/furniture">
      <figure class="image is-16by9">
        <img :src="frontPagePictures.main.fields.file.url" alt="main">
        <div class="level">
          <div class="level-item is-overlay">
            <h1 class="title is-1 title-color">
              Furniture
            </h1>
          </div>
        </div>
      </figure>
    </nuxt-link>
    <nuxt-link to="/acoustics">
      <figure class="image is-16by9">
        <img :src="frontPagePictures.acoustics.fields.file.url" alt="acoustics">
        <div class="level">
          <div class="level-item is-overlay">
            <h1 class="title is-1 title-color">
              Acoustics
            </h1>
          </div>
        </div>
      </figure>
    </nuxt-link>
    <nuxt-link to="/studios">
      <figure class="image is-16by9">
        <img :src="frontPagePictures.studios.fields.file.url" alt="studios">
        <div class="level">
          <div class="level-item is-overlay">
            <h1 class="title is-1 title-color">
              Studios
            </h1>
          </div>
        </div>
      </figure>
    </nuxt-link>
    <nuxt-link to="/theaters">
      <figure class="image is-16by9">
        <img :src="frontPagePictures.theaters.fields.file.url" alt="theaters">
        <div class="level">
          <div class="level-item is-overlay">
            <h1 class="title is-1 title-color">
              Theaters
            </h1>
          </div>
        </div>
      </figure>
    </nuxt-link>
    <nuxt-link to="/podcasts">
      <figure class="image is-16by9">
        <img :src="frontPagePictures.podcasts.fields.file.url" alt="podcasts">
        <div class="level">
          <div class="level-item is-overlay">
            <h1 class="title is-1 title-color">
              Podcasts
            </h1>
          </div>
        </div>
      </figure>
    </nuxt-link>
    <section class="hero is-light">
      <div class="hero-body">
        <div class="container has-text-centered">
          <h1 class="title">
            Making Audio Great Since 1998
          </h1>
        </div>
      </div>
    </section>
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

  .title-color {
    color: snow;
  }

</style>
