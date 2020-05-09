<template>
  <div>
    <b-navbar :fixed-top="true">
      <template slot="brand">
        <b-navbar-item tag="nuxt-link" :to="{ path: '/' }">
          <img
            src="~assets/MAG_logo.png"
            alt="MAG Custom Studio Furniture"
          >
        </b-navbar-item>
      </template>
      <template slot="start">
        <b-navbar-item tag="nuxt-link" :to="{ path: '/studios' }">
          Studios
        </b-navbar-item>
        <b-navbar-item tag="nuxt-link" :to="{ path: '/acoustics' }">
          Acoustics
        </b-navbar-item>
        <b-navbar-item tag="nuxt-link" :to="{ path: '/furniture' }">
          Furniture
        </b-navbar-item>
      </template>

      <template slot="end">
        <b-navbar-item tag="div">
          <div class="buttons">
            <a class="button is-primary">
              <strong>Sign up</strong>
            </a>
            <a class="button is-light">
              Log in
            </a>
          </div>
        </b-navbar-item>
      </template>
    </b-navbar>

    <section class="main-content">
      <div>
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: 'index' }
        },
        {
          title: 'Inspire',
          icon: 'lightbulb',
          to: { name: 'inspire' }
        }
      ]
    }
  }
}
</script>
