<template>
  <div>
    <HelloWorld msg=""/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/LinksComponent.vue'

export default {
  name: 'LinksView',
  components: {
    HelloWorld
  }
}
</script>
