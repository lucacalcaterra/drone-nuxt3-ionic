<template>
  <ion-content ref="content">
    <ion-button @click="geoPosition">Get Location</ion-button>
    <ion-input ref="currentLocation" type="text" placeholder="Title"></ion-input>

  </ion-content>
</template>

<script setup lang="ts">
import { IonButton, IonContent } from "@ionic/vue";
import { Geolocation } from "@capacitor/geolocation";

import { ref } from "vue";

const content = ref();
const currentLocation = ref('');
const geoPosition = async () => {
  const coordinates = await Geolocation.getCurrentPosition();
  currentLocation= "ciao";

  console.log("Current position:", coordinates.timestamp);
};
</script>
