<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 2</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 2</ion-title>
        </ion-toolbar>
      </ion-header>
      <div>
      
       <nav> <router-link to="/tabs/podcastEmissions" >  aller aux podcasts </router-link>    </nav> 
      
            
         
           <ion-card onload="getEmissions()" v-for="emission in emissions" :key="emission.id">
            <ion-card-header>
              <img :src="emission.banner" alt="emission.name">
              <ion-card-title>{{ emission.name }}</ion-card-title>
            </ion-card-header>

            <ion-card-content>
                
            </ion-card-content>
          </ion-card>
          
          
          
         
        </div>
      
    </ion-content>
  </ion-page>
</template>

<script>
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';

export default defineComponent({
  name: 'Tab2Page',
  components: {  IonHeader, IonToolbar, IonTitle, IonContent, IonPage } ,
  data: function () {
    return {
      emissions : null
    }
  },
methods: {
  getEmissions() {
			fetch(' https://gascognefm.net/api/emissions')
			.then(reponse => reponse.json())
			.then(data => {
        
         this.emissions = data
        console.log(data)
				console.log(data[1].banner)

			})
  },
},
mounted() {
 
  this.getEmissions() 
},


});



</script>
