<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-button expand="block" @click="play('sound1')">Play 1</ion-button>
      <ion-button expand="block" @click="play('sound2')">Play 2</ion-button>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonButton,
} from "@ionic/vue";
import { SoundEffect } from "capacitor-sound-effect";

export default {
  name: "Tab1",
  components: {
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonPage,
    IonButton,
  },
  setup() {
    const loadSound = (soundFile: string) => {
      SoundEffect.loadSound({
        id: soundFile,
        path: `../assets/sounds/${soundFile}.mp3`,
      })
        .then(() => true)
        .catch(() => false);
    };
    loadSound("sound1");
    loadSound("sound2");

    const play = (soundFile: string) => {
      console.log({ soundFile });
      SoundEffect.play({ id: soundFile })
        .then(() => true)
        .catch(() => false);
    };
    return { play };
  },
};
</script>