<template>
  <div class="contact">
    <HelloWorld msg="Welcome to your contact page Jonathan."/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/LinksView.vue'

export default {
  name: 'ContactView',
  components: {
    HelloWorld
  }
}
</script>
