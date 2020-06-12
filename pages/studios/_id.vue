<template>
  <section class="section">
    <div v-if="studio" class="container">
      <b-carousel :autoplay="false" :indicator-inside="false">
        <b-carousel-item v-for="(photo, i) in studio.fields.photos" :key="i">
          <span class="image">
            <img :src="photo.fields.file.url">
          </span>
        </b-carousel-item>
        <template slot="indicators" slot-scope="props">
          <span>
            <img :src="getImgUrl(props.i)" :title="props.i">
          </span>
        </template>
      </b-carousel>
      <div class="content is-medium">
        <h1>
          {{ studio.fields.title }}
        </h1>
        <p>
          {{ studio.fields.description }}
        </p>
      </div>
    </div>
  </section>
</template>

<script>
import { createClient } from '~/plugins/contentful.js'

const client = createClient()

export default {
  name: 'Id',
  data () {
    return {
      loading: false,
      studio: null,
      error: null
    }
  },
  watch: {
    // call again the method if the route changes
    $route: 'fetchData'
  },
  created () {
    // fetch the data when the view is created and the data is
    // already being observed
    this.fetchData()
  },
  methods: {
    fetchData () {
      this.error = this.post = null
      this.loading = true
      // replace `getPost` with your data fetching util / API wrapper
      Promise.all([
        // fetch all studio posts sorted by creation date
        client.getEntries({
          'sys.id': this.$route.params.id
        })
      ]).then(([studio]) => {
        // return data that should be available
        // in the template
        this.studio = studio.items[0]
        // eslint-disable-next-line no-console
      }).catch(console.error)
    },
    getImgUrl (value) {
      return this.studio.fields.photos[value].fields.file.url
    }
  }
}
</script>

<style scoped>

</style>
