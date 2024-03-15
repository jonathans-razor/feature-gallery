<template>
  <div class="home">
    <img width=200 alt="Vue logo" src="../assets/feature-gallery.svg">
    <HelloWorld msg="Welcome to FeatureGallery"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
