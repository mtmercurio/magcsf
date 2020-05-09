<template>
  <div class="container">
    <div class="columns is-multiline">
      <div v-for="item in items" :key="item.title" class="column">
        <figure class="image is-square">
          <img src="~assets/studios/kairi/main.jpg">
        </figure>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Studio',
  data () {
    return {
      items: [
        {
          title: 'Kairi1',
          main: '~assets/studios/kairi/main.jpg',
          pics: [
            '~assets/studios/kairi/main.jpg',
            '~assets/studios/kairi/rtrr.jpg',
            '~assets/studios/kairi/panels.jpg',
            '~assets/studios/kairi/back.jpg',
            '~assets/studios/kairi/frontceiling.jpg',
            '~assets/studios/kairi/frnt.jpg',
            '~assets/studios/kairi/boothcloud.jpg',
            '~assets/studios/kairi/framing2.jpg'
          ]
        },
        {
          title: 'Troy Taylor1',
          main: '~assets/studios/troy_taylor/crfront.jpg',
          pics: [
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/ceiling2.jpg',
            '~assets/studios/troy_taylor/crback.jpg',
            '~assets/studios/troy_taylor/crfrnt2.jpg',
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/studioside.jpg',
            '~assets/studios/troy_taylor/unfnshdkthn1.jpg'
          ]
        },
        {
          title: 'Kairi2',
          main: '~assets/studios/kairi/main.jpg',
          pics: [
            '~assets/studios/kairi/main.jpg',
            '~assets/studios/kairi/rtrr.jpg',
            '~assets/studios/kairi/panels.jpg',
            '~assets/studios/kairi/back.jpg',
            '~assets/studios/kairi/frontceiling.jpg',
            '~assets/studios/kairi/frnt.jpg',
            '~assets/studios/kairi/boothcloud.jpg',
            '~assets/studios/kairi/framing2.jpg'
          ]
        },
        {
          title: 'Troy Taylor2',
          main: '~assets/studios/troy_taylor/crfront.jpg',
          pics: [
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/ceiling2.jpg',
            '~assets/studios/troy_taylor/crback.jpg',
            '~assets/studios/troy_taylor/crfrnt2.jpg',
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/studioside.jpg',
            '~assets/studios/troy_taylor/unfnshdkthn1.jpg'
          ]
        },
        {
          title: 'Kairi3',
          main: '~assets/studios/kairi/main.jpg',
          pics: [
            '~assets/studios/kairi/main.jpg',
            '~assets/studios/kairi/rtrr.jpg',
            '~assets/studios/kairi/panels.jpg',
            '~assets/studios/kairi/back.jpg',
            '~assets/studios/kairi/frontceiling.jpg',
            '~assets/studios/kairi/frnt.jpg',
            '~assets/studios/kairi/boothcloud.jpg',
            '~assets/studios/kairi/framing2.jpg'
          ]
        },
        {
          title: 'Troy Taylor3',
          main: '~assets/studios/troy_taylor/crfront.jpg',
          pics: [
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/ceiling2.jpg',
            '~assets/studios/troy_taylor/crback.jpg',
            '~assets/studios/troy_taylor/crfrnt2.jpg',
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/studioside.jpg',
            '~assets/studios/troy_taylor/unfnshdkthn1.jpg'
          ]
        },
        {
          title: 'Kairi4',
          main: '~assets/studios/kairi/main.jpg',
          pics: [
            '~assets/studios/kairi/main.jpg',
            '~assets/studios/kairi/rtrr.jpg',
            '~assets/studios/kairi/panels.jpg',
            '~assets/studios/kairi/back.jpg',
            '~assets/studios/kairi/frontceiling.jpg',
            '~assets/studios/kairi/frnt.jpg',
            '~assets/studios/kairi/boothcloud.jpg',
            '~assets/studios/kairi/framing2.jpg'
          ]
        },
        {
          title: 'Troy Taylor4',
          main: '~assets/studios/troy_taylor/crfront.jpg',
          pics: [
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/ceiling2.jpg',
            '~assets/studios/troy_taylor/crback.jpg',
            '~assets/studios/troy_taylor/crfrnt2.jpg',
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/studioside.jpg',
            '~assets/studios/troy_taylor/unfnshdkthn1.jpg'
          ]
        },
        {
          title: 'Kairi5',
          main: '~assets/studios/kairi/main.jpg',
          pics: [
            '~assets/studios/kairi/main.jpg',
            '~assets/studios/kairi/rtrr.jpg',
            '~assets/studios/kairi/panels.jpg',
            '~assets/studios/kairi/back.jpg',
            '~assets/studios/kairi/frontceiling.jpg',
            '~assets/studios/kairi/frnt.jpg',
            '~assets/studios/kairi/boothcloud.jpg',
            '~assets/studios/kairi/framing2.jpg'
          ]
        },
        {
          title: 'Troy Taylor5',
          main: '~assets/studios/troy_taylor/crfront.jpg',
          pics: [
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/ceiling2.jpg',
            '~assets/studios/troy_taylor/crback.jpg',
            '~assets/studios/troy_taylor/crfrnt2.jpg',
            '~assets/studios/troy_taylor/crfront.jpg',
            '~assets/studios/troy_taylor/studioside.jpg',
            '~assets/studios/troy_taylor/unfnshdkthn1.jpg'
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
