<template>
  <ion-app>
    <ion-router-outlet />

    
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { defineComponent } from 'vue';



export default defineComponent({
  name: 'App',
   data() {
    return {
      currentAudioName: '',
      audioList: [
        {
          name: 'audio1',
          url: 'https://stream-ssl.radios-arra.fr:8443/gascognefm'
        }
      ]
    }
  },
  components: {
    IonApp,
    IonRouterOutlet,
    AudioPlayer
  },
   methods: {
    // Something to do before playing
    handleBeforePlay(next) {
      // There are a few things you can do here...
      this.currentAudioName = this.audioList[this.$refs.audioPlayer.currentPlayIndex].name

      next() // Start playing
    }
  }

});
</script>