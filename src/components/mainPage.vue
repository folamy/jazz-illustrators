<template lang="html">
  <v-layout row>
    <!-- <v-flex> -->
      <v-carousel>
        <v-carousel>
          <v-carousel-item v-for="(item,i) in items" :src="item.src" :key="i"></v-carousel-item>
        </v-carousel>
      </v-carousel>
    <!-- </v-flex> -->
  </v-layout>
</template>

<script>
import pic from '../assets/logo_black.jpg'
export default {
  data () {
    return {
      items: [
        {
          src: 'https://vuetifyjs.com/static/doc-images/carousel/squirrel.jpg'
        },
        {
          src: 'https://vuetifyjs.com/static/doc-images/carousel/sky.jpg'
        },
        {
          src: 'https://vuetifyjs.com/static/doc-images/carousel/bird.jpg'
        },
        {
          src: pic
        }
      ]
    }
  }
}
</script>

<style lang="css">
</style>
