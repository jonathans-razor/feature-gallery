<script setup>

console.log("* Script setup called.");
import { ref } from 'vue';

const latitude = ref(0);
const longitude = ref(0);
function getLocation(){
  console.log("* Geolocation function called.");
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition((position) => {
      latitude.value = position.coords.latitude;
      longitude.value = position.coords.longitude;

      console.log("Latitude: " + position.coords.latitude + "<br>Longitude: " + position.coords.longitude);
    });
  } else {
    console.log("Geolocation is not supported by this browser.");
  }

}
</script>

<template>
  <div>
    <h2>Map Page</h2>
  </div>
  <button @click="getLocation()">Get Location</button>
</template>
