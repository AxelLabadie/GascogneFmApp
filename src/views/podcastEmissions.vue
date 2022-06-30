<template>
    <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>podcasts</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">podcast</ion-title>
        </ion-toolbar>
      </ion-header>
      
      
    {{$route.params.id }}

    </ion-content>
  </ion-page>
    
</template>

<script>
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';



export default defineComponent({
  name: 'podcastEmissions',
  components: {  IonHeader, IonToolbar, IonTitle, IonContent, IonPage } ,
  data: function () {
    return {
      emission : null
    }
  },
methods: {
  getPodcast() {
			
      const IdPodcast = this.$route.params.id
      
      fetch(' https://gascognefm.net/api/emissions/'+IdPodcast)
			.then(reponse => reponse.json())
			.then(data => {
        this.emission = data
         
				

			})
  },
},
mounted() {
 
  this.getPodcast() 
},


});



</script>
