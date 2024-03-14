
<script setup>
  import { defineProps } from 'vue';

  const p = defineProps("isWithColor");
  const test = "test";
</script>

<template>
  aa
  {{ p }}
  {{ p.isWithColor }}
  {{ isWithColor }}
  {{ test }}
  bb
  <v-card class="mx-5 my-2 pa-3">
    <v-row>
      <v-col v-for="n in 144" :key="n" class="d-flex child-flex" cols="4" sm="3" md="2" lg="1">
        <v-img 
          aspect-ratio="1" 
          cover class="bg-grey-lighten-2"
          :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`" 
          :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`"        
        >
          <template v-slot:placeholder>
            <v-row class="fill-height ma-0" align="center" justify="center">
              <v-progress-circular indeterminate color="grey-lighten-5"></v-progress-circular>
            </v-row>
          </template>
        </v-img>
      </v-col>
    </v-row>
  </v-card>
</template>