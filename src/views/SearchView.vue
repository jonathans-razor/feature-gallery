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
  { name: 'Mike Tyson', power: 9100 },
  { name: 'Jon Jones', power: 9000 },
  { name: 'Roy Jones Jr.', power: 7900 },
  { name: 'Khabib Nurmagomedov', power: 7850 },
  { name: 'Conor McGregor', power: 6900 },
  { name: 'Muhuammad Ali', power: 8600 },
  { name: 'Floyd Mayweather', power: 6800 },
  { name: 'Francis Ngannou', power: 8500 },
  { name: 'Sean OMalley', power: 6000 },
  { name: 'Dominic Reyes', power: 8100 },
  { name: 'Sergei Pavlovich', power: 6000 },
  { name: 'Lyoto Machida', power: 6150 },
  { name: 'Rampage Jackson', power: 6000 },
  { name: 'Chuck Liddell', power: 6200 },
  { name: 'Jorge Masvidal', power: 6000 },
  { name: 'Anderson Silva', power: 8500 },
  { name: 'Brock Lesnar', power: 8500 },
  { name: 'Fedor Emelianenko', power: 9000 },
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