<template>
  <div>
    <b-navbar :fixed-top="true" :wrapper-class="'container'">
      <template slot="brand">
        <b-navbar-item tag="nuxt-link" :to="{ path: '/' }">
          <img
            src="~assets/MAG.png"
            alt="MAG Custom Studio Furniture"
          >
          <h1 class="MAG-font title is-4">
            MAG CUSTOM
          </h1>
        </b-navbar-item>
      </template>
      <template slot="start">
        <b-navbar-item tag="nuxt-link" :to="{ path: '/furniture' }" class="MAG-font">
          Furniture
        </b-navbar-item>
        <b-navbar-item tag="nuxt-link" :to="{ path: '/acoustics' }" class="MAG-font">
          Acoustics
        </b-navbar-item>
        <b-navbar-item tag="nuxt-link" :to="{ path: '/studios' }" class="MAG-font">
          Studios
        </b-navbar-item>
        <b-navbar-item tag="nuxt-link" :to="{ path: '/theaters' }" class="MAG-font">
          Theaters
        </b-navbar-item>
        <b-navbar-item tag="nuxt-link" :to="{ path: '/about' }" class="MAG-font">
          About Us
        </b-navbar-item>
      </template>

      <template slot="end">
        <b-navbar-item tag="div">
          <div class="buttons">
            <nuxt-link :to="{ path: '/contact-us' }" class="button is-primary MAG-font">
              <strong>Contact Us</strong>
            </nuxt-link>
          </div>
        </b-navbar-item>
      </template>
    </b-navbar>

    <section class="main-content">
      <div>
        <nuxt />
      </div>
    </section>
    <footer class="footer">
      <div class="container">
        <div class="columns is-vcentered is-hidden-mobile">
          <div class="column is-narrow">
            <figure class="image is-128x128">
              <img src="~assets/MAG.png">
            </figure>
          </div>
          <div class="column">
            <p class="content is-large">
              <a href="tel:7703782866">
                (770) 378-2866
              </a>
            </p>
            <p class="content is-large">
              <a href="mailto:mike@magcsf.com">
                sales@magcsf.com
              </a>
            </p>
          </div>
        </div>
        <div class="container has-text-centered is-hidden-tablet">
          <div class="content is-flex is-horizontal-center">
            <figure class="image is-128x128">
              <img src="~assets/MAG.png">
            </figure>
          </div>
          <p class="content is-large">
            <a href="tel:7703782866">
              (770) 378-2866
            </a>
          </p>
          <p class="content is-large">
            <a href="mailto:mike@magcsf.com">
              sales@magcsf.com
            </a>
          </p>
        </div>
      </div>
    </footer>
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
        }
      ]
    }
  }
}
</script>

<style>
  .is-horizontal-center {
    justify-content: center;
  }

  a {
    color: #47494e;
    text-decoration: none;
  }

  a:hover
  {
    color:#7F828B;
    text-decoration:none;
    cursor:pointer;
  }
</style>
