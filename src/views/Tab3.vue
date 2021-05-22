<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 3</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 3</ion-title>
        </ion-toolbar>
      </ion-header>
      
      <ion-button expand="block" @click="goToTab1()">Go to tab 1</ion-button>
      
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton } from '@ionic/vue';
import { useRouter } from 'vue-router';

export default  {
  name: 'Tab3',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonButton },
  setup() {
    const router = useRouter();
    const goToTab1 = () => {
      router.replace('/tabs/tab1');
    };
    return { goToTab1 };
  }
}
</script>