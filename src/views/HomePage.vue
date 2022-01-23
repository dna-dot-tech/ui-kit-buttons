<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <div id="container">
          <custom-button>Button</custom-button><br>
          <custom-button type="primary">Button</custom-button><br>
          <custom-button type="secondary">Button</custom-button>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import customButton from './Button.vue'
import { defineComponent } from 'vue';

export default defineComponent({
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    customButton
  }
});
</script>

<style scoped>
#container {
  margin-top: 2em;
  margin-left: 2em;
}
</style>