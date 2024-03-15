<template>
  <div class="home">
    <img width=200 alt="Vue logo" src="../assets/feature-gallery.svg">
    <h1>
      Welcome to FeatureGallery
    </h1>
    <p>
      A Vue learning tool.
    </p>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/LinksView.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
