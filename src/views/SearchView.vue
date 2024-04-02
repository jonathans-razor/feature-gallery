<!--
An example of creating a reusable grid component and using it with external data.
-->

<script setup>
import DemoGrid from './GridView.vue'
import { ref } from 'vue'

const searchQuery = ref('')
const gridColumns = ['name', 'power']
const gridData = [
  { name: 'Chuck Norris', power: Infinity },
  { name: 'Bruce Lee', power: 2000 },
  { name: 'Jackie Chan', power: 1000 },
  { name: 'Jet Li', power: 1500 }
]
</script>

<template>
  <form id="search">
    Search <input name="query" v-model="searchQuery">
  </form>
  <br>
  <br>
  <div align="center">
    <DemoGrid
      :data="gridData"
      :columns="gridColumns"
      :filter-key="searchQuery">
    </DemoGrid>
  </div>
</template>