<template>
  <div>
    <nuxt-link to="/furniture">
      <section class="hero is-light is-hidden-tablet">
        <div class="hero-body">
          <div class="container has-text-centered">
            <h1 class="title">
              Furniture
            </h1>
          </div>
        </div>
      </section>
      <figure class="image is-16by9">
        <img :src="frontPagePictures.main.fields.file.url" alt="main">
      </figure>
    </nuxt-link>
    <div class="columns is-gapless is-multiline">
      <div class="column is-one-third">
        <nuxt-link to="/acoustics">
          <section class="hero is-light">
            <div class="hero-body">
              <div class="container has-text-centered">
                <h1 class="title">
                  Acoustics
                </h1>
              </div>
            </div>
          </section>
          <figure class="image is-16by9">
            <img :src="frontPagePictures.acoustics.fields.file.url" alt="acoustics">
          </figure>
        </nuxt-link>
      </div>
      <div class="column is-one-third">
        <nuxt-link to="/studios">
          <section class="hero is-light">
            <div class="hero-body">
              <div class="container has-text-centered">
                <h1 class="title">
                  Studios
                </h1>
              </div>
            </div>
          </section>
          <figure class="image is-16by9">
            <img :src="frontPagePictures.studios.fields.file.url" alt="studios">
          </figure>
        </nuxt-link>
      </div>
      <div class="column is-one-third">
        <nuxt-link to="/theaters">
          <section class="hero is-light">
            <div class="hero-body">
              <div class="container has-text-centered">
                <h1 class="title">
                  Theaters
                </h1>
              </div>
            </div>
          </section>
          <figure class="image is-16by9">
            <img :src="frontPagePictures.theaters.fields.file.url" alt="theaters">
          </figure>
        </nuxt-link>
      </div>
      <div class="column is-full">
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
