<template>
  <div>
    <section class="hero is-info is-fullheight is-fullheight-with-navbar">
      <div class="hero-body main-img" />
    </section>
    <div class="columns is-gapless">
      <div class="column">
        <nuxt-link to="/studios">
          <section class="hero is-light">
            <div class="hero-body">
              <div class="container has-text-centered">
                <h1 class="subtitle is-3">
                  Customize your space.
                </h1>
              </div>
            </div>
          </section>
          <section class="hero is-info is-fullheight">
            <div class="hero-body studios-img">
              <div class="container has-text-centered">
                <h1 class="title is-1">
                  Studios
                </h1>
              </div>
            </div>
          </section>
        </nuxt-link>
      </div>
      <div class="column">
        <nuxt-link to="/furniture">
          <section class="hero is-light">
            <div class="hero-body">
              <div class="container has-text-centered">
                <h1 class="title">
                  Built to your needs.
                </h1>
              </div>
            </div>
          </section>
          <section class="hero is-info is-fullheight">
            <div class="hero-body furniture-img">
              <div class="container has-text-centered">
                <h1 class="title is-1">
                  Furniture
                </h1>
              </div>
            </div>
          </section>
        </nuxt-link>
      </div>
      <div class="column">
        <nuxt-link to="/acoustics">
          <section class="hero is-light">
            <div class="hero-body">
              <div class="container has-text-centered">
                <h1 class="title">
                  Fine tune your room.
                </h1>
              </div>
            </div>
          </section>
          <section class="hero is-info is-fullheight">
            <div class="hero-body acoustics-img">
              <div class="container has-text-centered">
                <h1 class="title is-1">
                  Acoustics
                </h1>
              </div>
            </div>
          </section>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  components: {

  }
}
</script>

<style>

  .main-img {
    background-image: url('~assets/home/main.jpg');
    background-size: cover;
  }

  .acoustics-img {
    background-image: url('~assets/home/acoustics.jpg');
    background-size: cover;
  }

  .furniture-img {
    background-image: url('~assets/home/furniture.jpg');
    background-size: cover;
  }

  .studios-img {
    background-image: url('~assets/home/studios.jpg');
    background-size: cover;
  }

</style>
