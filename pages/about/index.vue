<template>
  <section class="section">
    <div class="container">
      <div class="content is-medium">
        <h1>
          About Us
        </h1>
        <p>
          {{ about }}
        </p>
      </div>
    </div>
  </section>
</template>

<script>
import { createClient } from '~/plugins/contentful.js'

const client = createClient()

export default {
  name: 'About',
  // `env` is available in the context object
  asyncData () {
    return Promise.all([
      // fetch all acoustic posts sorted by creation date
      client.getEntries({
        content_type: 'about',
        order: '-sys.createdAt'
      })
    ]).then(([about]) => {
      // return data that should be available
      // in the template
      return {
        about: about.items[0].fields.description
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

<style scoped>

</style>
