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
    
      <div id="container" style="background:gray: height:300px">
          <custom-button :text-size="1.5" bg="white" :width="90" :height="10" color="orange">Text</custom-button><br><br>
          <custom-button :text-size="1.9" bg="white" :width="130" :height="50" color="green">Text</custom-button><br><br>
          <custom-button :text-size="1" bg="yellow" :width="40" :height="3" color="red">Text</custom-button>
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