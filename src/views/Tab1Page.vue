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
      
      <figure>
    <figcaption></figcaption>
    <audio id="Stream" 
        controls
        src="https://stream-ssl.radios-arra.fr:8443/gascognefm"  >
    </audio>
</figure>

<iframe src="https://www.gascognefm.com/intranet/HTMLPlaylist/playingnow.html" frameborder="0"  width="1000" height="250" scrolling="no"   ></iframe>

      
    </ion-content>
  </ion-page>
</template>

<script>
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';


export default  defineComponent({
  name: 'Tab1Page',
  components: {  IonHeader, IonToolbar, IonTitle, IonContent, IonPage }
});
</script>
